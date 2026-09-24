# Business Requirements & Use Cases
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Business problem

Fraud teams need a way to evaluate suspicious activity using more than one evidence source. The platform is intended to reduce fragmented analysis and make risk decisions faster, more consistent and more auditable.

## 2. Primary business outcomes

1. Reduce time required to assess suspicious transactions.
2. Improve consistency of fraud triage.
3. Increase visibility into blockchain-related risk.
4. Preserve evidence supporting decisions.
5. Provide an extensible foundation for future fraud models and integrations.

## 3. Core use cases

### UC-01 — Evaluate a transaction
A transaction is submitted. The platform validates it, evaluates applicable AI/rules/blockchain signals and returns a risk result.

### UC-02 — Verify blockchain evidence
A supported transaction hash, wallet or contract interaction is checked against the configured blockchain infrastructure. The system records the verification outcome.

### UC-03 — Generate a fraud alert
When the score or a configured rule crosses an alert threshold, the platform creates an alert containing the relevant evidence and reason codes.

### UC-04 — Investigate an alert
An authorized analyst views the transaction, risk score, contributing signals and blockchain evidence and records an investigation outcome.

### UC-05 — Audit a decision
An authorized user can determine which version of the model/rules and which evidence contributed to a decision.

### UC-06 — Handle blockchain outage
If an RPC provider, node or indexing service fails, the platform marks the blockchain signal as unavailable and follows the defined fallback behavior rather than treating the transaction as automatically fraudulent.

## 4. Example business scenario

```text
Customer Transaction
        ↓
Fraud Platform
        ↓
AI detects unusual behavior
        +
Rules detect abnormal velocity
        +
Blockchain shows unusual wallet/contract activity
        ↓
Risk Engine
        ↓
Score = 87 / Critical
        ↓
Fraud Alert
        ↓
Analyst Investigation
        ↓
Final Decision + Audit Record
```

## 5. Future expansion opportunities

The architecture should allow future additions such as:
- additional blockchain networks;
- graph-based wallet analytics;
- additional ML models;
- external intelligence providers;
- case-management integrations;
- advanced analyst dashboards;
- automated model monitoring;
- additional financial products.

These are future possibilities, not automatic MVP commitments.
