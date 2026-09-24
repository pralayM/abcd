# Data & API Architecture
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Data architecture

The system should use PostgreSQL for application-side transactional and analytical metadata.

A conceptual data boundary is:

```text
                     Application
                         │
                         ↓
                   API / Services
                    /     |      \
                   ↓      ↓       ↓
             PostgreSQL   AI   Blockchain
                   │      │       │
                   └──────┼───────┘
                          ↓
                     Risk Engine
                          ↓
                    Decision/Audit
```

## 2. Candidate data domains

- Transactions.
- Customers/accounts where approved.
- Fraud signals.
- Model results.
- Rule results.
- Blockchain verification results.
- Risk scores.
- Alerts/cases.
- Audit records.
- Model/ruleset versions.
- System configuration.

## 3. Data principles

- Minimize collection.
- Encrypt sensitive data in transit and at rest.
- Apply retention rules.
- Separate operational and audit concerns where appropriate.
- Use stable IDs and timestamps.
- Do not store secrets in application tables.
- Avoid duplicating sensitive blockchain data unnecessarily.

## 4. API design

The company should propose:
- REST/JSON baseline;
- versioned endpoints;
- OpenAPI documentation;
- authentication;
- authorization;
- request validation;
- consistent error model;
- correlation IDs;
- pagination;
- rate limiting;
- idempotency where required.

## 5. Example endpoint families

```text
POST   /api/v1/transactions
GET    /api/v1/transactions/<built-in function id>
POST   /api/v1/transactions/<built-in function id>/evaluate
GET    /api/v1/risk/<built-in function id>
GET    /api/v1/alerts
GET    /api/v1/blockchain/transactions/<built-in function hash>
GET    /api/v1/audit/<built-in function id>
```

These are illustrative; final API design is part of the partner's technical proposal.

## 6. Audit record concept

A decision audit record should identify:
- decision ID;
- transaction ID;
- score;
- classification;
- contributing signals;
- model version;
- ruleset version;
- blockchain verification reference;
- timestamps;
- analyst action, if applicable.
