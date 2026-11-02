# PostgreSQL + Spring Boot Setup (Ubuntu)

Short guide to set up PostgreSQL for a Spring Boot project.

## 1. Create the database and user

PostgreSQL runs as a background service. Spring Boot can create tables, but not the database itself, so create it first.

```bash
sudo -u postgres psql
```

```sql
CREATE DATABASE vendora;
CREATE USER myuser WITH PASSWORD 'your_password';
GRANT ALL PRIVILEGES ON DATABASE vendora TO myuser;
\c vendora
GRANT ALL ON SCHEMA public TO myuser;
\q
```

- `CREATE DATABASE` makes an empty database.
- `CREATE USER` makes a login just for the app, so it doesn't use the superuser.
- `GRANT ALL PRIVILEGES` lets the user use that database.
- `\c vendora` switches into the database. Do this before the last `GRANT`.
- `GRANT ALL ON SCHEMA public` lets the user create tables. Without it you get `permission denied for schema public`.
- `\q` leaves psql.

Every SQL line ends with `;`. Lines starting with `\` don't need one.

## 2. Add the driver (`pom.xml`)

```xml
<dependency>
    <groupId>org.postgresql</groupId>
    <artifactId>postgresql</artifactId>
    <scope>runtime</scope>
</dependency>
```

The JDBC driver lets Java talk to PostgreSQL. You also need `spring-boot-starter-data-jpa`.

## 3. Configure `application.properties`

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/vendora
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
jwt.secret.key=${JWT_SECRET_KEY}
```

- `url` is where the server is and which database to use.
- `${...}` reads a value from an environment variable, so secrets stay out of GitHub.
- `ddl-auto=update` creates or alters tables to match your `@Entity` classes and keeps your data.
- `show-sql=true` prints the SQL in the console.

## 4. Environment variables

Generate a JWT secret:

```bash
openssl rand -base64 32
```

Set the variables in the terminal:

```bash
export DB_USERNAME=myuser
export DB_PASSWORD=your_password
export JWT_SECRET_KEY=your_generated_secret
```

- `export` creates a variable that only lives in that terminal window.
- Run the app from the same terminal: `./mvnw spring-boot:run`
- If you get `Permission denied`, run `chmod +x mvnw` once.
- To make them permanent, add the `export` lines to `~/.bashrc`, then run `source ~/.bashrc`.
- Check them with `env | grep -E "DB_|JWT_"`.
- Remove one with `unset DB_PASSWORD`.

## 5. Run from IntelliJ

IntelliJ doesn't see terminal variables. Add them in the run configuration:

1. Run > Edit Configurations > add an **Application** (or Spring Boot) config.
2. Set the main class to your `...Application` class.
3. Modify options > tick **Environment variables**.
4. Add `DB_USERNAME`, `DB_PASSWORD`, `JWT_SECRET_KEY`.

The names must match `application.properties` exactly. If they don't, Spring sends the literal text `${DB_USERNAME}` to PostgreSQL and login fails.

## 6. Look at your tables

Log in to the database:

```bash
psql -U myuser -d vendora -h localhost
```

`-h localhost` makes it ask for the password instead of checking the Linux user.

| Command | Meaning |
|---|---|
| `\l` | List databases |
| `\c dbname` | Connect to a database |
| `\dt` | List tables |
| `\d tablename` | Show a table's columns |
| `\du` | List users (roles) |
| `\r` | Clear a half-typed statement |
| `\q` | Quit psql |

```sql
SELECT * FROM users;
SELECT * FROM users LIMIT 10;
```

- `SELECT *` means all columns.
- A table named `user` is a reserved word, so quote it: `SELECT * FROM "user";`

## 7. Service commands

```bash
sudo systemctl status postgresql
sudo systemctl start postgresql
sudo systemctl stop postgresql
```

Your data stays on disk when the app or the service stops.

## 8. Common errors

| Error | Cause | Fix |
|---|---|---|
| `database "x" does not exist` | Database was never created, or a statement had no `;` | Run `CREATE DATABASE x;` |
| Prompt shows `postgres-#` | psql is waiting for a `;` | Add `;` or type `\r` |
| `role "postgres" already exists` | That user is built in | Create a different user |
| `permission denied for schema public` | Schema grant was skipped or run in the wrong database | `sudo -u postgres psql -d vendora`, then `GRANT ALL ON SCHEMA public TO myuser;` |
| `password authentication failed for user "${DB_USERNAME}"` | The variable isn't set or its name doesn't match | Fix the variable name and run from the right place |
| `Could not resolve placeholder` | Environment variable is missing | Set it in the terminal or the IntelliJ run config |
| `bash: ./mvnw: Permission denied` | Script isn't executable | `chmod +x mvnw` |
| `syntax error at or near "psql"` | Typed a terminal command inside psql | Leave psql with `\q` first |

## 9. ddl-auto options

| Value | What it does |
|---|---|
| `update` | Adds or changes tables, keeps data (good for dev) |
| `validate` | Only checks tables match, changes nothing |
| `create` | Drops and recreates tables on every start (deletes data) |
| `create-drop` | Same as `create`, and drops them on shutdown |

Use `validate` or Flyway migrations for anything beyond development.

## 10. Delete and start over

```sql
DROP DATABASE vendora;
DROP USER myuser;
```

This permanently deletes the data. Drop the database first, then the user.
