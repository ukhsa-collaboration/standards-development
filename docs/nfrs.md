# Non-Functional Requirements (NFRs)

## Introduction

Non-functional requirements (NFRs) define how a system should behave rather than what it should do. They ensure that services are secure, reliable, performant, and usable. This guidance outlines key NFR categories and summarises expectations using **RFC 2119** keywords.

---

## Guidance

### Performance

Systems **MUST** meet defined response time and throughput targets under expected load. Teams **SHOULD** conduct load and stress testing in pre-production environments and **MUST** document performance baselines.

### Reliability and Availability

Services **MUST** meet agreed uptime targets and **SHOULD** implement automated recovery mechanisms. Teams **MUST** monitor availability and **SHOULD** use health checks and failover strategies.

### Usability and Accessibility

User interfaces **MUST** meet WCAG 2.1 AA standards. Teams **SHOULD** conduct usability testing and **MUST** ensure services are accessible to all users, including those with assistive technologies.

### Security

Systems **MUST** implement secure defaults, least privilege, and defence-in-depth. Teams **MUST** follow secure coding practices and **MUST** validate all inputs and outputs. Refer to the [Security Principles](./security.md) and [Secure SDLC](./secure-sdlc.md) guidance.

### Maintainability

Codebases **SHOULD** be modular, well-documented, and follow agreed standards. Teams **MUST** use version control and **SHOULD** automate testing and deployment.

### Scalability

Systems **SHOULD** scale horizontally where possible and **MUST** handle increased load without degradation. Teams **SHOULD** test scalability scenarios and document scaling strategies.

### Observability

Teams **MUST** implement logging, metrics, and alerting. Logs **MUST NOT** contain sensitive data. Dashboards **SHOULD** provide visibility into system health and performance.

### Portability

Services **SHOULD** be deployable across environments with minimal changes. Teams **MUST** avoid hardcoded environment-specific values and **SHOULD** use configuration management.

### Compliance

Systems **MUST** meet legal, regulatory, and organisational compliance requirements. This includes data protection, auditability, and retention policies.

---

## Measurement

| ID    | NFR Category  | Green                             | Amber                | Red                       |
| ----- | ------------- | --------------------------------- | -------------------- | ------------------------- |
| NFR-1 | Performance   | Meets all targets                 | Some targets unmet   | No targets or testing     |
| NFR-2 | Availability  | Meets SLA, auto-recovery in place | Manual recovery only | Frequent outages          |
| NFR-3 | Accessibility | WCAG 2.1 AA compliant             | Partial compliance   | No accessibility testing  |
| NFR-4 | Security      | All controls implemented          | Some gaps            | No controls or validation |
| NFR-5 | Observability | Logs, metrics, alerts in place    | Partial coverage     | No observability          |
