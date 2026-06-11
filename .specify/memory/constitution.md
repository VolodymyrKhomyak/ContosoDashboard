<!-- Sync Impact Report: Version 1.0.0 (initial) | Added 3 core principles, technical constraints, security governance, stakeholder-driven amendment process. Templates requiring updates: plan-template.md ✅, spec-template.md ✅, tasks-template.md ✅. -->

# Contoso Dashboard Constitution

## Core Principles

### I. User-Centric Design
Every feature must prioritize user experience, accessibility, and simplicity. Teams MUST validate designs with stakeholders before implementation. Features MUST be intuitive and minimize cognitive load. Rationale: Contoso Dashboard serves diverse users across teams; poor UX reduces adoption and productivity.

### II. Data Security First
Security is non-negotiable and embedded in every layer. All sensitive data MUST be encrypted at rest and in transit. Authentication and authorization MUST use role-based access control (RBAC). PII handling MUST comply with data protection standards. Audit logging MUST capture all data access and modifications. Rationale: Dashboard manages sensitive project and team data; compliance and trust are critical.

### III. Maintainability & Clean Code
Code MUST be readable, well-documented, and follow SOLID principles. Architectural decisions MUST be justified and documented. Technical debt MUST be tracked and addressed proactively. Rationale: Long-term team productivity and onboarding efficiency depend on code clarity.

## Technical & Architectural Constraints

- **Runtime**: .NET 10 / C# only
- **Frontend**: Single-page Razor Components (Blazor WASM/Server-side as appropriate)
- **Data Access**: Entity Framework Core with SQL Server
- **Authentication**: Azure AD integration mandatory
- **API Communication**: Structured JSON for client-server messaging
- **Database**: SQL Server; schema migrations MUST be version-controlled

## Quality & Testing Requirements

**Testing Strategy**: Balanced approach—core business logic and data operations MUST use Test-Driven Development (TDD); supportive features (UI utilities, helpers) use standard post-development testing.

**Core Features Requiring TDD**:
- Data models and business logic (Projects, Tasks, Users, Notifications)
- Authentication and authorization workflows
- Critical workflows (project creation, task assignment, team management)
- Data access layer (EF Core queries and migrations)

**Standard Testing**:
- UI component interactions (Razor Components)
- Notification service edge cases
- Localization and internationalization features

## Security & Data Governance

**Data Protection**:
- Encryption MUST be enforced for data in transit (TLS 1.2+) and at rest (SQL Server Transparent Data Encryption)
- API endpoints MUST validate and sanitize all inputs
- No sensitive data (passwords, PII) MUST be logged or cached unencrypted

**Access Control**:
- RBAC MUST be implemented for all features (Admin, Manager, Team Member, Viewer roles minimum)
- MUST enforce principle of least privilege
- Session timeouts MUST be configured based on risk level

**Audit & Compliance**:
- All data modifications MUST be logged with timestamp, user ID, and change details
- PII access MUST be tracked separately and reviewed quarterly
- Compliance violations MUST trigger alerts

## Governance & Amendment Process

**Decision-Making Authority**: Stakeholder-Driven
- Business stakeholders (Product Owner, Team Leads) and Technical Lead guide all constitution amendments
- Technical decisions affecting architecture require consensus
- Security and compliance decisions are final and non-negotiable

**Amendment Procedure**:
- All constitution amendments MUST be proposed in writing with rationale
- Changes requiring stakeholder review MUST be documented in a GitHub issue
- Amendments take effect immediately upon merge; version bumped per semantic versioning
- MAJOR: Principle removal or redefinition
- MINOR: New principle or expanded guidance
- PATCH: Clarifications, wording, non-semantic refinements

**Compliance Review**: Quarterly review of all PRs/specs against constitution. Violations MUST be addressed before merge.

---

**Version**: 1.0.0 | **Ratified**: 2026-06-11 | **Last Amended**: 2026-06-11
