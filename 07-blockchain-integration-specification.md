# Blockchain Integration Specification
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Scope

This specification defines how the application communicates with blockchain infrastructure and converts blockchain information into reliable signals for the fraud engine.

## 2. Required integration functions

- Network connectivity and health checking.
- Transaction lookup.
- Receipt/status lookup.
- Block/confirmation information.
- Contract event monitoring.
- Address/wallet activity retrieval where supported.
- Transaction normalization.
- Verification result generation.
- Retry and backoff.
- Rate-limit handling.
- Event checkpointing.
- Duplicate detection.

## 3. Suggested normalized verification model

```text
BlockchainVerification
- network
- transactionHash
- blockNumber
- transactionStatus
- confirmationState
- fromAddress
- toAddress
- contractAddress
- value
- gasUsed
- eventSummary
- observedAt
- provider
- verificationStatus
- failureReason
```

Exact schema may be refined during architecture design.

## 4. Verification states

The integration should distinguish:
- VERIFIED;
- NOT_FOUND;
- PENDING;
- REVERTED;
- INVALID_INPUT;
- UNAVAILABLE;
- PROVIDER_ERROR;
- UNSUPPORTED.

## 5. Event processing

The event listener should:
- record a durable checkpoint;
- process events idempotently;
- tolerate restarts;
- detect duplicates;
- expose processing lag;
- support recovery from a known checkpoint;
- record failures for investigation.

## 6. Reliability

RPC calls should use:
- bounded timeouts;
- retry policy appropriate to error type;
- exponential backoff;
- provider health monitoring;
- optional provider failover where economically justified.

## 7. Risk-signal boundary

Blockchain integration should provide facts/signals, not independently make the final fraud decision.

Example:
```text
Blockchain fact:
Wallet interacted with contract X
        ↓
Derived signal:
Contract interaction pattern is associated with elevated risk
        ↓
Risk Engine:
Combine with AI and rules
        ↓
Final risk score
```

## 8. Security

- Credentials/API keys stored in approved secret management.
- RPC endpoints are configuration, not hard-coded secrets.
- Production write capability restricted.
- Contract addresses are environment-specific and validated.
- Network ID/chain ID must be checked.
