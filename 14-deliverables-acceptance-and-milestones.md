# Deliverables, Acceptance & Milestones
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Engagement model

Baseline planning assumption:
- Initial engagement: approximately 6 months.
- Company provides an appropriately staffed engineering team.
- Remote delivery.
- Milestone-based delivery with regular demonstrations.
- Extension possible by mutual agreement.

## 2. Detailed 24-Week Milestone Plan

### Milestone 1 — Discovery & Architecture

**Weeks 1–4**

**Week 1**

* Requirements validation
* Business and technical scope confirmation
* Stakeholder workshops
* Initial backlog

**Week 2**

* Solution architecture
* System/component boundaries
* Technology decisions
* Initial data/API design

**Week 3**

* Blockchain architecture
* Threat model
* Security requirements
* Integration dependencies

**Week 4**

* Final architecture review
* Technical risk assessment
* Delivery plan
* Implementation backlog approval

**Milestone acceptance:** Architecture approved, dependencies identified, and implementation backlog agreed.

---

### Milestone 2 — Blockchain Foundation

**Weeks 5–8**

**Week 5**

* Ethereum connectivity
* Network configuration
* Wallet/provider integration

**Week 6**

* Transaction verification
* Blockchain data retrieval
* Error/failure handling

**Week 7**

* Event listener/indexing foundation
* Smart-contract MVP where required

**Week 8**

* Automated blockchain tests
* Sepolia end-to-end validation
* Code review and documentation

**Milestone acceptance:** Supported blockchain flows work on Sepolia, failure scenarios are tested, and code review is completed.

---

### Milestone 3 — Fraud Detection Integration

**Weeks 9–13**

**Week 9**

* Transaction intake
* Validation and normalization
* Fraud data pipeline

**Week 10**

* AI/ML integration
* Fraud-rule integration
* Feature processing

**Week 11**

* Blockchain signals integrated into fraud analysis
* Risk engine implementation

**Week 12**

* Risk scoring
* Risk classification
* Decision logic
* Audit trail

**Week 13**

* End-to-end transaction evaluation
* Explainability validation
* Reproducibility testing

**Milestone acceptance:** End-to-end transaction evaluation is demonstrated and risk decisions are reproducible and explainable at the agreed level.

---

### Milestone 4 — Product, API & Investigation

**Weeks 14–17**

**Week 14**

* Production-quality APIs
* Authentication/authorization integration
* API documentation

**Week 15**

* Fraud alerts
* Alert rules
* Notification workflow

**Week 16**

* Investigation workflow
* Analyst views
* Evidence and audit views

**Week 17**

* Integration testing
* Representative end-to-end use cases
* Documentation completion

**Milestone acceptance:** Representative end-to-end use cases successfully pass.

---

### Milestone 5 — Security, Performance & Operations

**Weeks 18–21**

**Week 18**

* Security testing
* Dependency/security scanning
* Access-control validation

**Week 19**

* Performance and load testing
* Risk-engine performance validation
* API performance testing

**Week 20**

* Observability
* Logging
* Monitoring
* Alerting

**Week 21**

* Deployment automation
* Operational runbooks
* Incident procedures
* Remediation of critical findings

**Milestone acceptance:** Agreed quality gates pass and there are no unresolved critical security defects.

---

### Milestone 6 — Staging, Handover & Production Readiness

**Weeks 22–24**

**Week 22**

* Staging deployment
* Environment validation
* Final integration testing

**Week 23**

* Final documentation
* Knowledge transfer
* Operational training
* Production readiness assessment

**Week 24**

* Final QA
* Production readiness report
* Client/company sign-off
* Production deployment authorization

**Milestone acceptance:** Final sign-off is completed and production deployment is authorized explicitly.

---

## Milestone Payment / Review Structure

| Milestone | Weeks | Main Outcome                                 |
| --------- | ----: | -------------------------------------------- |
| M1        |   1–4 | Approved architecture & backlog              |
| M2        |   5–8 | Working blockchain foundation                |
| M3        |  9–13 | Integrated AI fraud/risk engine              |
| M4        | 14–17 | APIs, alerts & investigation workflow        |
| M5        | 18–21 | Security, performance & operations readiness |
| M6        | 22–24 | Staging, handover & production readiness     |

**Total planned duration: 24 weeks / approximately 6 months.**

Each milestone should be reviewed and formally accepted before moving to the next major phase. The existing document already specifies milestone-based delivery with regular demonstrations and acceptance based on functionality, testing, security, documentation and performance.


## 3. Acceptance principles

Acceptance should be based on:
- agreed requirements;
- demonstrable functionality;
- test evidence;
- security criteria;
- documentation completeness;
- agreed performance targets.

## 4. Change control

Material changes to scope, architecture, timeline or cost should use a written change request with:
- requested change;
- reason;
- scope impact;
- schedule impact;
- cost impact;
- security impact;
- approval decision.

## 5. Company deliverables

The selected company is expected to provide:
- source code and repository history;
- smart contracts;
- automated tests;
- API documentation;
- architecture/design records;
- deployment configurations/scripts;
- infrastructure documentation;
- security findings/remediation status;
- operational runbooks;
- final handover documentation.

## 6. Ownership and handover

The executed agreement/SOW should define IP ownership, licensing of pre-existing components, open-source obligations, confidentiality and handover requirements.
