# Project Overview
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Executive summary

The AI Fraud Detection Platform is a financial technology system designed to detect potentially fraudulent transactions by combining AI/ML models, deterministic rules, transaction context and blockchain-derived evidence.

The platform should produce a consistent risk assessment while preserving enough evidence and explanation for analysts and downstream systems to understand the decision.

## 2. High-level architecture

```text
                         AI FRAUD DETECTION PLATFORM
                                      │
                                      ↓
                              ┌───────────────┐
                              │   Transaction │
                              │     Input     │
                              └───────┬───────┘
                                      ↓
                              ┌───────────────┐
                              │ Data Validation│
                              │ & Normalization│
                              └───────┬───────┘
                                      ↓
                              ┌───────────────┐
                              │    Feature    │
                              │   Engineering │
                              └───────┬───────┘
                                      │
                    ┌─────────────────┼─────────────────┐
                    ↓                 ↓                 ↓
              ┌───────────┐    ┌────────────┐    ┌──────────────┐
              │ AI / ML   │    │ Fraud      │    │ Blockchain   │
              │ Model     │    │ Rules      │    │ Verification │
              └─────┬─────┘    └──────┬─────┘    └──────┬───────┘
                    └─────────────────┼─────────────────┘
                                      ↓
                              ┌───────────────┐
                              │   Risk Engine │
                              └───────┬───────┘
                                      ↓
                              ┌───────────────┐
                              │  Risk Score   │
                              │    0 – 100    │
                              └───────┬───────┘
                                      ↓
                       ┌──────────────┼──────────────┐
                       ↓              ↓              ↓
                     LOW           MEDIUM          HIGH/
                                                  CRITICAL
                                      │              │
                                      └──────┬───────┘
                                             ↓
                              ┌─────────────────────┐
                              │ Fraud Alert /       │
                              │ Investigation       │
                              └──────────┬──────────┘
                                         ↓
                              ┌─────────────────────┐
                              │ Analyst Final       │
                              │ Decision            │
                              └─────────────────────┘
```

## 3. AI + blockchain relationship

```text
                         Transaction
                              │
                 ┌────────────┴────────────┐
                 ↓                         ↓
          AI Fraud Analysis        Blockchain Analysis
                 │                         │
                 │                  TX / Wallet /
                 │                  Events / Status
                 │                         │
                 └────────────┬────────────┘
                              ↓
                       ┌─────────────┐
                       │ Risk Engine │
                       └──────┬──────┘
                              ↓
                         Risk Score
                              ↓
                        Fraud Alert
```

## 4. Typical transaction flow

```text
Transaction
    ↓
Validation
    ↓
Enrichment
    ↓
Feature Generation
    ↓
AI Model ──────────────┐
                       │
Fraud Rules ───────────┼──→ Risk Engine
                       │
Blockchain Signals ────┘
                            ↓
                       Risk Score
                            ↓
                 ┌──────────┴──────────┐
                 ↓                     ↓
              Low/Normal          High/Critical
                 ↓                     ↓
             Continue              Alert
                                       ↓
                                 Investigation
```

## 5. Product goals

- Detect suspicious activity earlier.
- Combine multiple evidence sources.
- Produce explainable risk signals.
- Provide consistent risk scoring.
- Preserve an auditable decision trail.
- Integrate blockchain evidence safely.
- Support analyst investigation and operational workflows.
- Build a foundation that can scale to additional fraud models and data sources.

## 6. Core user groups

- Fraud analysts/investigators.
- Risk/compliance teams.
- Operations teams.
- Engineering/administration teams.
- Authorized business/API consumers.

## 7. MVP boundary

The first implementation should focus on the core transaction-to-risk workflow, blockchain verification/integration, risk scoring, alert generation, API/backend services, security, testing and operational readiness.

The following are not assumed to be MVP requirements unless separately approved:
- unrestricted multi-chain support;
- automatic irreversible financial blocking;
- storing sensitive personal/financial data on a public blockchain;
- consumer mobile applications;
- every possible fraud typology;
- fully autonomous AI decisions without human/operational controls.

## 8. Technology baseline

The implementation baseline is Node.js + TypeScript + Express.js, PostgreSQL, Python + PyTorch/scikit-learn, and Ethereum Sepolia for development/staging with Ethereum Mainnet as the intended production network subject to approval.

## 9. Data boundary

Sensitive transaction/customer information should remain off-chain unless explicitly approved. Public-chain records should generally contain only information appropriate for public visibility, such as hashes, references, attestations or other approved proofs.

## 10. Success definition

The MVP is successful when the platform can reliably ingest a supported transaction, generate AI/rule/blockchain signals, calculate a risk score, create an actionable result, retain evidence, and operate through documented deployment and security controls.
