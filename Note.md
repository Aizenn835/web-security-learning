# My Linux & CORS Notes

## 1. CORS

### Access-Control-Allow-Credentials
This allows the browser to send a cookie inside the browser cookie jar. This should be turned off if I'm using a JWT since I'm not using a browser cookie jar and am storing it in `localStorage`.

### Access-Control-Allow-Origin
It's basically the allowed origin my backend will allow an API to send a response.

Example:

```java
config.setAllowedOrigins(List.of("https://my-example-website.com"));
```

So if this origin is in the list of my allowed origins, the backend will allow an API to make a response.

---

## 2. Basic Linux Commands

| Command | Description |
|---|---|
| `pwd` | Shows the current directory |
| `ls` | Shows the list of directories or files |
| `ls -l` | Shows the list in a long way or more detailed |
| `~` | Gets back you from the default directory |
| `whoami` | Shows the current username |
| `cd` | Puts you in a directory you want. For example: `cd Desktop` |
| `mkdir` | Use this command if you were to create a new folder |
| `rmdir` | Delete a folder |

---

## 3. Software Commands

| Command | Description |
|---|---|
| `sudo apt update` | Checks for updates |
| `sudo apt upgrade -y` | Downloads the newer version |

## 4. Sudo Commands

## Package Managers: Which One Should I Use?

| What You Want | Tool |
|---|---|
| Ubuntu software (programs, system tools, libraries) | `apt` |
| Apps from the Snap Store (e.g., VS Code) | `snap` |
| JavaScript libraries for a project (e.g., Express) | `npm` |
| Java libraries for a project | Maven or Gradle |
| Node.js versions | `nvm` |
| A downloaded `.deb` file | `apt install ./file.deb` |
