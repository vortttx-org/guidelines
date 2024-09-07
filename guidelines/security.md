# Security

At Vortx, ensuring the security of our codebase and the data we handle is a top priority, even when working in an open-source environment. This guide outlines best practices and necessary steps to safeguard sensitive information and protect the integrity of our projects.

## Handling Sensitive Information

**1. Avoid Hardcoding Sensitive Data:**

- Never hardcode sensitive information such as passwords, API keys, or database credentials directly into the source code;

- Use environment variables instead, and store these securely in configuration files that are not exposed, such as `.gitignore` files;

**2. Use .env Files for Local Development:**

- Store sensitive information in a `.env` file. This file should never be committed to the repository. Add it to the `.gitignore` file to ensure it stays out of version control;

- Follow this example of a `.env` file:

```bash
DB_PASSWORD=supersecretpassword
API_KEY=yourapikeyhere
```

- Adding it to the `.gitignore` file:

```bash
echo ".env" >> .gitignore
```

**3. Accessing Environment Variables in Code:**

- Use appropriate libraries to access environment variables in your code. For example, in Node.js:

```javascript
const apiKey = process.env.API_KEY;
```

## Encrypting Sensitive Data

**1. Always Encrypt Sensitive Data:**

- Use encryption to store sensitive data securely. For example, for password storage, use strong hashing algorithms like `bcrypt`;

- For any stored data that requires encryption (e.g., databases), follow best practices for encryption both at rest and in transit (e.g., using HTTPS for all external communication);

## Secure Communication

**1. Use HTTPS for External Communications:**

- Always use HTTPS to communicte with external services or APIs. This ensures that data in transit is encrypted and protected from interception;

**2. SSH Over HTTPS:**

- When cloning repositories or making remote connections, prefer using SSH instead of HTTPS for added security in authentication;

## Protecting API Keys and Access Tokens:

**1. Store API Keys Securely:**

- Avoid exposing API keys and tokens in our source code. Store them in environment variables or a secure secrets manager;

- If deploying to plataforms like Vercel, make sure to use their built-in environment variable management tools to securely store these keys;

**2. Rotating API Keys:**

- Remember to regularly rotate API keys and credentials to reduce the risk of unauthorized access;

## Securing Dependencies

**1. Regularly Update Dependencies:**

- Open-Source projects like ours rely heavily on external dependencies. Regularly update dependencies to patch security vulnerabilites. Use tools like `npm audit` or `Snyk` to monitor for vulnerabilities in our packages;

**2. Use Dependency Pinning:**

- Pin the versions of our dependencies to specific, stable releases to avoid introducing breaking changes or vulnerabilities;

```json
"dependencies": {
    "express": "4.17.1"
}
```

## Access Control and Permissions

**1. Limit of Access to Sensitive Operations:**

- We use the principle of least privilege for accessing sensitive operations, both within the codebase and in our deployment environments;

- Only trusted team members have admin-level access to repositories and deployment tools;

## Regular Security Audits

**1. Regular Security Audits:**

- We periodically audit our codebase for security risks using automated tools like SonarQube and Trivy to scan for vulnerabilities in our code. These tools can help detect common issues like SQL injection, XSS (cross-site scripting), and insecure use of libraries;

## Secure GitHub and Repository Settings

**1. Enable 2FA on GitHub Accounts:**

- All members must enable two-factor authentication (2FA) on their GitHub accounts for an extra layer of security. GitHub provides instructions to set up 2FA [here](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication);

**2. Branch Protection Rules:**

- Every important branch (like `master` and `dev`) is protected by enabling branch protection rules. They all require PR reviews, successful CI checks, and force-push prevention;

## Secrets Management for Deployments

**1. Secrets Management Tools:**

- When deploying our applications, we use secrets management tools offered by platforms like Vercel and AWS to securely store and access sensitive information like API keys or database credentials;

## Handling Security Incidents

**1. A Plan for Security Incidents:**

- In the event of a security breach or exposure of sensitive data, immediately revoke the compromised credentials and rotate keys;

- When the incident is taken care of, we always conduct a post-incident review to identify the root cause and prevent similar incidents in the future;
