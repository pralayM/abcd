# Security & Privacy Requirements
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Security objective

The platform processes potentially sensitive financial and fraud-related information. Security must be designed into the system rather than added at the end.

## 2. Identity and access

- Role-based access control.
- Least privilege.
- Unique user/service identities.
- No shared production credentials.
- MFA where supported.
- Separate development, staging and production permissions.

## 3. Secrets

Secrets must be stored using approved secret-management infrastructure.

Do not:
- commit private keys;
- commit API secrets;
- place credentials in source code;
- send production keys to developers through chat/email;
- store secrets in ordinary configuration files.

## 4. Blockchain security

- Verify chain/network identity.
- Validate contract addresses.
- Restrict write operations.
- Protect signing infrastructure.
- Monitor unusual signing activity.
- Use testnet/local environments for development.
- Require explicit production authorization.

## 5. Application security

The company should implement:
- TLS;
- secure authentication;
- authorization checks;
- input validation;
- SQL-injection prevention;
- dependency scanning;
- secure logging;
- rate limiting;
- abuse protection;
- vulnerability management.

## 6. Privacy

Sensitive data should remain off public blockchain networks. Where a blockchain proof is required, use a minimized representation such as a hash/reference when appropriate.

## 7. Production changes

Production deployment and smart-contract changes require documented approval. Emergency changes must be logged and reviewed afterward.

## 8. Incident response

The partner must help define procedures for:
- compromised credentials;
- compromised signing key;
- RPC/provider outage;
- malicious API activity;
- data exposure;
- contract vulnerability;
- incorrect deployment;
- suspicious production transactions.
