## 🔒 Security

### 🧩 Core Web Vulnerabilities
- **XSS (Cross-Site Scripting)**
  - Injection of malicious JavaScript into web pages.
  - Types: Stored, Reflected, DOM-based.
  - Prevention:
    - HTML escape user input.
    - Use Content Security Policy (CSP).
    - Sanitize and validate user data.
    - Avoid `innerHTML` with raw user input.
  - Example:
    ```html
    <script>alert('hacked')</script>
    ```

- **CSRF (Cross-Site Request Forgery)**
  - Forces an authenticated user to perform unwanted actions.
  - Occurs when credentials (cookies) are reused automatically.
  - Prevention:
    - CSRF tokens (synchronizer token pattern).
    - SameSite cookie flag (`SameSite=Strict`).
    - Validate origin and referer headers.
    - Avoid GET for state-changing requests.

- **SQL Injection**
  - Malicious input alters SQL queries.
  - Example:
    ```sql
    SELECT * FROM users WHERE username = 'admin' OR 1=1;
    ```
  - Prevention:
    - Always use prepared statements / parameterized queries.
    - Never concatenate raw user input.
    - Use ORM safely (avoid raw SQL when possible).
    - Input validation & escaping.

---

### 🧠 Encryption vs Encoding vs Hashing
- **Encryption**
  - Reversible transformation using a key.
  - **Symmetric**: same key for encrypt/decrypt (AES, DES, ChaCha20).
  - **Asymmetric**: public/private key pair (RSA, ECC).
  - Used in TLS, SSH, JWT signature verification.
  - Example Use Case: Encrypt sensitive data (credit card numbers, secrets).

- **Encoding**
  - Converts data into a transport-safe format (not for security).
  - Example: Base64, URL encoding.
  - Used for data transmission and readability.

- **Hashing**
  - One-way transformation, cannot be reversed.
  - Used for password storage, data integrity.
  - Algorithms: SHA-256, SHA-512, bcrypt, Argon2, PBKDF2.
  - Best Practice:
    - Always use salt + slow hashing function for passwords (bcrypt, Argon2).
    - Avoid plain SHA for passwords (too fast, vulnerable to brute-force).

---

### 🔐 TLS / HTTPS
- **TLS (Transport Layer Security)**
  - Encrypts communication between client and server.
  - Prevents eavesdropping and man-in-the-middle (MITM) attacks.
  - Uses asymmetric cryptography for handshake, symmetric for data.
  - HTTPS = HTTP + TLS.
  - Ensure:
    - Strong cipher suites.
    - Certificate validation.
    - Automatic redirection to HTTPS.
    - HSTS header (`Strict-Transport-Security`).

---

### 🧾 Authentication & Authorization
- **Cookie / Session**
  - Server stores session data, client holds a cookie with session ID.
  - **Cookie Properties**:
    - `HttpOnly`: Prevent JavaScript access.
    - `Secure`: Send only over HTTPS.
    - `SameSite`: Prevent CSRF.
  - **Session Hijacking Prevention**:
    - Rotate session IDs after login.
    - Regenerate session on privilege change.
    - Use short session TTL.
    - Validate IP/User-Agent when necessary.

- **JWT (JSON Web Token)**
  - Stateless authentication (signed token stored on client).
  - Structure: `Header.Payload.Signature`
  - Pros:
    - No server-side session storage.
    - Easy to use across services (microservices / APIs).
  - Cons:
    - Harder to revoke before expiration.
    - Token size increases network overhead.
  - Security:
    - Use short expiration (`exp` claim).
    - Always verify signature (HS256, RS256).
    - Store in secure HTTP-only cookie or in-memory, not localStorage.
    - Avoid sensitive data in payload (it's only base64-encoded).

- **OAuth 2.0**
  - Authorization protocol for delegated access.
  - Roles:
    - Resource Owner, Client, Resource Server, Authorization Server.
  - Common Flows:
    - Authorization Code (web apps)
    - Client Credentials (machine-to-machine)
    - Implicit (deprecated for SPAs)
    - Password Grant (legacy, insecure)
  - Modern practice: use **PKCE** for code flow (prevents token interception).

- **OpenID Connect (OIDC)**
  - Built on top of OAuth 2.0 for authentication (identity layer).
  - Adds ID token (JWT) for user identity.

---

### 🧩 Web and API Security Best Practices
- Validate and sanitize all input.
- Apply principle of least privilege (users, API keys, DB credentials).
- Enforce HTTPS everywhere.
- Use secure headers:
  - `Content-Security-Policy`
  - `X-Frame-Options: DENY`
  - `X-Content-Type-Options: nosniff`
  - `Referrer-Policy`
- Use rate limiting and throttling (prevent brute-force / abuse).
- Implement logging and anomaly detection (auth attempts, errors).
- Keep dependencies up to date (use scanners like `safety`, `npm audit`).
- Use secret management tools (AWS Secrets Manager, Vault).
- Don’t store credentials in Git (use `.env` + `.gitignore`).
- Use WAF (Web Application Firewall) for external exposure.

---

### 🧩 Single Login Page Test Cases
- **Functional**
  - Correct login/logout flow.
  - Redirects after login.
  - “Remember me” and password reset work as expected.
- **Security**
  - Prevent SQL injection and XSS in login fields.
  - Validate HTTPS and HSTS enabled.
  - No sensitive info in cookies or URLs.
  - Lockout after multiple failed attempts.
- **User Experience**
  - Error messages don’t reveal sensitive info.
  - Proper validation feedback (e.g., “invalid password” vs “invalid username”).
- **Performance**
  - Handle concurrent logins.
  - Quick authentication under load.
- **Compatibility**
  - Works across browsers and devices.
  - Handles cookie policies correctly.

---

### 🧱 Web3 Security (Brief Overview)
- **Smart Contract Vulnerabilities**
  - Reentrancy attacks, integer overflow/underflow, timestamp dependence.
- **Wallet Security**
  - Private key leakage, phishing, malicious extensions.
- **Off-chain ↔ On-chain integration**
  - Validate signatures and payloads.
  - Avoid storing sensitive data directly on-chain.
- **Security Tools**
  - Static analyzers (Mythril, Slither)
  - Auditing (OpenZeppelin)

---

### ⚙️ Common Attack Vectors Summary
| Attack Type | Description | Mitigation |
|--------------|--------------|-------------|
| XSS | Injecting JavaScript | Input sanitization, CSP |
| CSRF | Forced user action | Tokens, SameSite cookies |
| SQL Injection | Code injection into queries | Parameterized queries |
| Session Hijacking | Stolen session cookie | HttpOnly, Secure flags |
| MITM | Intercepted traffic | HTTPS / TLS |
| Brute Force | Repeated login attempts | Rate limiting |
| Clickjacking | Invisible iframe trap | X-Frame-Options |
| Insecure Deserialization | Code execution via payloads | Validate types and signatures |

---

### ⚡ Quick Summary
> **Security is defense-in-depth.**  
> Protect data with encryption, isolate sessions, and validate all inputs.  
> Prevent XSS, CSRF, and SQL Injection through sanitization and safe patterns.  
> Use HTTPS + secure cookies + short-lived tokens.  
> In modern systems, combine OAuth2, JWT, and TLS for secure APIs and authentication.
