# Blockchain Architecture
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Architecture

```text
                    AI FRAUD DETECTION PLATFORM
                              │
                              ↓
                     ┌─────────────────┐
                     │ Transaction /   │
                     │ Application     │
                     └────────┬────────┘
                              ↓
                     ┌─────────────────┐
                     │   Backend/API   │
                     └────────┬────────┘
                              │
             ┌────────────────┼────────────────┐
             ↓                ↓                ↓
      ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
      │ AI / ML      │ │ Fraud Rules  │ │ Blockchain   │
      │ Engine       │ │ Engine       │ │ Integration  │
      └──────┬───────┘ └──────┬───────┘ └──────┬───────┘
                                              ↓
                                      ┌────────────────┐
                                      │ RPC Provider / │
                                      │ Blockchain Node│
                                      └───────┬────────┘
                                              ↓
                                      ┌────────────────┐
                                      │ Blockchain     │
                                      │ Network        │
                                      └───────┬────────┘
                                              │
                               ┌──────────────┴──────────────┐
                               ↓                             ↓
                         Transactions                  Contract Events
                               │                             │
                               └──────────────┬──────────────┘
                                              ↓
                                      ┌────────────────┐
                                      │ Verification / │
                                      │ Event Indexer  │
                                      └───────┬────────┘
                                              ↓
                                  Blockchain Risk Signals
                                              │
             ┌────────────────────────────────┘
             ↓
                       ┌─────────────┐
                       │ Risk Engine │
                       └──────┬──────┘
                              ↓
                         Risk Score
                              ↓
                    ┌─────────┴─────────┐
                    ↓                   ↓
                 Normal          High / Critical
                                        ↓
                                  Fraud Alert
```

## 2. Blockchain responsibilities

The blockchain subsystem is responsible for:
- connecting to approved Ethereum infrastructure;
- validating blockchain references;
- retrieving transactions and receipts;
- monitoring relevant events;
- normalizing blockchain data;
- producing verification results;
- producing risk signals;
- handling provider/network failures;
- preventing duplicate or inconsistent event processing.

## 3. Blockchain integration flow

```text
Blockchain Network
        ↓
RPC Provider
        ↓
Blockchain Listener
        ↓
Raw Blockchain Data
        ↓
Normalization
        ↓
Verification
        ↓
Blockchain Risk Signals
        ↓
Risk Engine
        ↓
Fraud Decision
```

## 4. Wallet/signing architecture

```text
Application
     ↓
Transaction Builder
     ↓
Authorization Check
     ↓
Approved Signing Service
     ↓
Signed Transaction
     ↓
Blockchain Network
```

Private keys must remain under company-controlled security boundaries.

## 5. Design principles

- Least privilege.
- Explicit network/contract configuration.
- Idempotent event processing.
- Confirmed transaction state rather than assumption.
- Clear distinction between unavailable data and negative evidence.
- Secure secret storage.
- No sensitive data written to public chain without explicit approval.
- Production changes require authorization.
- All blockchain writes should be traceable.

## 6. Environment separation

```text
Development
    ↓
Local/Test Network
    ↓
Sepolia Testnet
    ↓
Staging
    ↓
Ethereum Mainnet Production
```

## 7. Failure cases

The implementation must address:
- RPC timeout;
- rate limit;
- provider outage;
- invalid transaction hash;
- pending transaction;
- reverted transaction;
- delayed confirmation;
- duplicate events;
- missing events;
- chain reorganization where applicable;
- wrong network/contract address;
- contract execution failure;
- indexer restart/recovery.

## 8. Company design proposal

The selected company may propose an improved blockchain architecture provided that it:
1. preserves the business objective;
2. improves security/reliability/cost where possible;
3. documents trade-offs;
4. obtains approval for material architectural changes.
