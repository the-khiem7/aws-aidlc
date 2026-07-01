# Security Baseline Rules

**Extension**: Security Baseline
**Status**: Enforced when user opts in during Requirements Analysis

## Mandatory Security Rules

### Input Validation
- Validate ALL input at system boundaries
- Use parameterized queries/prepared statements for database operations
- Implement input sanitization for all user-supplied data
- Define and enforce input format schemas (JSON Schema, XML Schema, etc.)

### Authentication
- Use standard authentication frameworks (OAuth 2.0, OIDC, SAML)
- Implement MFA for admin and privileged accounts
- Store passwords using bcrypt, scrypt, or Argon2 (NEVER plaintext, MD5, SHA-1, or SHA-256 alone)
- Implement account lockout after X failed attempts

### Authorization
- Implement principle of least privilege
- Use RBAC or ABAC for access control
- Validate authorization at EVERY API endpoint (not just UI)
- Never trust client-side authorization

### Data Protection
- Encrypt sensitive data at rest (AES-256)
- Encrypt data in transit (TLS 1.2+)
- Mask/PII data in logs and error messages
- Implement secure key management (KMS, Vault, etc.)

### API Security
- Implement rate limiting on all public endpoints
- Use API keys or tokens for service-to-service communication
- Validate Content-Type and Accept headers
- Implement request size limits

### Logging and Monitoring
- Log all security-relevant events (auth attempts, access denials, data changes)
- Never log passwords, tokens, PII, or secrets
- Implement audit trails for sensitive operations
- Set up alerts for suspicious activity patterns

### Dependency Management
- Regularly scan dependencies for known vulnerabilities
- Pin dependency versions (avoid ranges)
- Maintain a software bill of materials (SBOM)
- Review and update dependencies for security patches

### Error Handling
- Never expose stack traces to end users
- Return generic error messages to clients
- Log detailed errors internally
- Implement global exception handlers
