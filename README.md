# Web Security Learning Roadmap

My journey learning web security and ethical penetration testing alongside React and Spring Boot.

## Goal

Learn web application security and ethical web penetration testing while continuing to develop my React and Spring Boot skills.

**Duration:** 6 months (24 weeks)  
**Study time:** Up to 5 hours per day  
**Budget:** Free resources whenever possible  
**Primary focus:** Web application security, API security, and penetration testing

## Phase 1: Web Fundamentals (Weeks 1–4)

### Week 1 — HTTP and Browser Fundamentals
- [ ] Understand HTTP requests and responses.
- [ ] Learn GET, POST, PUT, PATCH, and DELETE.
- [ ] Understand headers, status codes, cookies, and sessions.
- [ ] Inspect API requests using Chrome DevTools.
- [ ] Identify requests sent from React to Spring Boot.

Resource: https://developer.mozilla.org/en-US/docs/Web/HTTP

### Week 2 — Networking and Linux Basics
- [ ] Understand IP addresses, ports, DNS, TCP, and TLS.
- [ ] Learn basic Linux terminal commands.
- [ ] Understand client-server communication.
- [ ] Explore localhost connections.

Resource: https://missing.csail.mit.edu/

### Week 3 — SQL and Databases
- [ ] Review SELECT, INSERT, UPDATE, and DELETE.
- [ ] Understand how Spring Data JPA communicates with PostgreSQL.
- [ ] Learn parameterized queries and prepared statements.
- [ ] Understand the basics of SQL injection.

### Week 4 — Authentication and Authorization
- [ ] Understand authentication versus authorization.
- [ ] Learn password hashing.
- [ ] Understand JWTs and authorization headers.
- [ ] Review Spring Security and role-based access control.
- [ ] Trace the login flow from React to Spring Boot.

## Phase 2: Common Web Vulnerabilities (Weeks 5–8)

### Week 5 — SQL Injection
- [ ] Understand how SQL injection occurs.
- [ ] Study unsafe query construction.
- [ ] Complete beginner SQL injection labs.
- [ ] Document prevention techniques.

### Week 6 — Broken Access Control and IDOR
- [ ] Understand object-level authorization.
- [ ] Learn Insecure Direct Object Reference (IDOR).
- [ ] Test access controls in authorized labs.
- [ ] Learn how to enforce permissions on the backend.

### Week 7 — Cross-Site Scripting (XSS)
- [ ] Understand reflected XSS.
- [ ] Understand stored XSS.
- [ ] Understand DOM-based XSS.
- [ ] Learn output encoding and safe handling of untrusted input.
- [ ] Complete beginner labs.

### Week 8 — Authentication Vulnerabilities
- [ ] Study session management.
- [ ] Understand common login security flaws.
- [ ] Review password storage and account security.
- [ ] Learn secure authentication practices.

Primary resource: https://portswigger.net/web-security

## Phase 3: Security Testing Tools (Weeks 9–12)

### Week 9 — Burp Suite Basics
- [ ] Install Burp Suite Community Edition.
- [ ] Learn the Proxy feature.
- [ ] Inspect HTTP history.
- [ ] Understand request and response structures.

### Week 10 — Repeater and Request Analysis
- [ ] Learn to resend requests with Repeater.
- [ ] Modify parameters in authorized training labs.
- [ ] Compare server responses.
- [ ] Record test observations.

### Week 11 — Guided Penetration Testing Labs
- [ ] Complete beginner SQL injection labs.
- [ ] Complete beginner access-control labs.
- [ ] Complete beginner XSS labs.
- [ ] Write a report for each completed lab.

### Week 12 — First Security Assessment
- [ ] Define the testing scope.
- [ ] Select an authorized training application.
- [ ] Document at least three investigated vulnerabilities.
- [ ] Record evidence, impact, and remediation.
- [ ] Review what I learned.

Resource: https://portswigger.net/burp/documentation/desktop/getting-started

## Phase 4: API Security (Weeks 13–16)

### Week 13 — Object-Level Authorization
- [ ] Understand Broken Object Level Authorization (BOLA).
- [ ] Test ownership checks using separate test accounts.
- [ ] Prevent unauthorized access to orders and profiles.

### Week 14 — JWT Security
- [ ] Understand JWT structure and validation.
- [ ] Learn common token validation mistakes.
- [ ] Review expiration, signing, and key management.
- [ ] Implement secure validation with Spring Security.

### Week 15 — Browser and API Security
- [ ] Understand CORS.
- [ ] Understand Cross-Site Request Forgery (CSRF).
- [ ] Learn the differences between these security mechanisms.
- [ ] Review appropriate security configurations.

### Week 16 — API Protection
- [ ] Understand rate limiting.
- [ ] Review account security.
- [ ] Learn safe error handling.
- [ ] Write automated authorization tests.

Resource: https://owasp.org/www-project-api-security/

## Phase 5: Advanced Beginner Topics (Weeks 17–20)

### Week 17 — File Uploads and Path Traversal
- [ ] Learn secure file-upload handling.
- [ ] Understand file type and size restrictions.
- [ ] Study path traversal.
- [ ] Review file storage and access controls.

### Week 18 — Security Misconfiguration
- [ ] Review HTTP security headers.
- [ ] Identify unsafe debug settings.
- [ ] Understand information leakage through errors.
- [ ] Review production configuration practices.

### Week 19 — Business Logic Vulnerabilities
- [ ] Understand how flawed workflows create vulnerabilities.
- [ ] Review discount and checkout logic.
- [ ] Test order ownership and state transitions.
- [ ] Document prevention strategies.

### Week 20 — Dependency Security
- [ ] Understand vulnerable dependencies.
- [ ] Review Maven and npm dependencies.
- [ ] Learn how to read security advisories.
- [ ] Practice identifying and updating vulnerable packages.

Resources:
- https://owasp.org/www-project-top-ten/
- https://owasp.org/www-project-dependency-check/
- https://github.com/juice-shop/juice-shop

## Phase 6: Portfolio Project (Weeks 21–24)

### Project: Secure E-commerce API

Use a personal React and Spring Boot application as the target for a defensive security assessment.

- [ ] Create multiple test users and roles.
- [ ] Test order and profile authorization.
- [ ] Review JWT validation.
- [ ] Review password storage.
- [ ] Test input handling and SQL injection defenses.
- [ ] Review file-upload security.
- [ ] Review errors and security configuration.
- [ ] Write automated security tests.
- [ ] Document findings and fixes.
- [ ] Create a clear GitHub README.

The project must document the scope, test methodology, evidence, impact, remediation, and verification results.

## Learning Rules

1. Practice only on applications I own or have explicit permission to test.
2. Understand each vulnerability instead of copying payloads.
3. Document every important lab.
4. Prioritize secure coding alongside penetration testing.
5. Keep credentials, tokens, and private data out of GitHub.
6. Progress at a sustainable pace and adjust deadlines when necessary.

## Main Learning Resources

- PortSwigger Web Security Academy: https://portswigger.net/web-security
- MDN HTTP Documentation: https://developer.mozilla.org/en-US/docs/Web/HTTP
- OWASP Top 10: https://owasp.org/www-project-top-ten/
- OWASP API Security: https://owasp.org/www-project-api-security/
- Burp Suite Documentation: https://portswigger.net/burp/documentation
- The Missing Semester: https://missing.csail.mit.edu/

