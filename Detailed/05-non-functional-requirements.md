# Non-Functional Requirements
**Classification:** Confidential — For Recipients and Authorized Parties Only  
**Project:** AI Fraud Detection Platform with Blockchain Verification  
**Document Version:** 1.0  
**Status:** Issued for Company Review  
**Audience:** Development companies, solution partners, technical leads, product stakeholders, procurement, QA, security and operations  

*This document is a project/RFP planning document, not legal advice. Commercial and legal terms should be reviewed by qualified counsel before execution.*

## 1. Reliability

The platform should be designed for graceful degradation. Blockchain or external-provider failure should not silently corrupt risk decisions.

## 2. Performance targets

Initial planning targets:
- Read API: under 3 seconds P95 in a production-like environment.
- Write/evaluation API: under 5 seconds P95 where synchronous blockchain confirmation is required.
- Verification query: under 3 seconds P95 for supported cached/normal paths.

Final targets should be validated against the chosen architecture.

## 3. Scalability

The system should support an initial production design capable of approximately:
- 5,000 write/evaluation transactions per day;
- peak bursts of approximately 2–5 TPS;
- higher read/verification volumes.

These are planning targets, not guaranteed business volumes.

## 4. Availability

The company should propose an availability target appropriate to the final deployment architecture and identify single points of failure.

## 5. Security

TLS, access control, secrets management, audit logging and least privilege are mandatory design principles.

## 6. Observability

Logs, metrics, traces/correlation IDs and actionable alerts should be included.

## 7. Maintainability

Code must be documented, reviewed and structured for another qualified engineering team to maintain.

## 8. Disaster recovery

The partner should define backup, restoration, service recovery and blockchain event replay procedures appropriate to the architecture.
