# Soul's Echo — Decision Register
**Document:** Decision Register
**Project:** Soul's Echo
**Status:** Active
**Version:** 0.1

---

## 1. Purpose
This document records significant product, technical, security, privacy, commercial and development decisions for Soul's Echo.

The objective is to preserve:

- What was decided
- Why it was decided
- What alternatives were considered
- What evidence supported the decision
- What consequences followed
Important decisions should not exist only in chat history, memory or source code.

---

## 2. Decision Status
Each decision should use one of the following statuses:

### Proposed
Under consideration but not yet approved.

### Accepted
Approved as the current project direction.

### Superseded
Replaced by a later decision.

### Rejected
Considered and deliberately not adopted.

### Deferred
Decision intentionally postponed pending additional evidence.

---

## 3. Decision Categories
Decision categories may include:

- Product
- Customer
- Hardware
- Firmware
- Mobile
- Backend
- Security
- Privacy
- Consent
- Infrastructure
- Manufacturing
- Regulatory
- Commercial
- Brand
- Development Process

---

# ACCEPTED DECISIONS

## DEC-001 — Soul's Echo Band Is the First Physical Product
**Status:** Accepted
**Category:** Product

### Decision
The Soul's Echo Band will be the first physical product developed within the Soul's Echo ecosystem.

### Context
The wider ecosystem may eventually include additional form factors such as a Ring, Pendant, Dock and other products.

Attempting to develop multiple products simultaneously would increase technical, commercial and manufacturing complexity before the core proposition is validated.

### Alternatives Considered

- Launch multiple device types together.
- Begin with the Ring.
- Begin with a software-only experience.
- Develop the entire ecosystem before validating any single product.

### Reason
The Band provides sufficient physical space for early hardware development while still supporting the central concept of wearable remote presence.

A single-device focus reduces early scope.

### Consequences

- Band requirements receive priority.
- Other physical products remain future concepts.
- Supporting software should remain extensible enough to accommodate future devices.

---

## DEC-002 — Soul's Echo Companion App Is the Common Software Platform
**Status:** Accepted
**Category:** Product / Mobile

### Decision
The Soul's Echo Companion App will serve as the common user-facing software platform for the ecosystem.

### Reason
A shared platform can manage:

- Accounts
- Devices
- Pairing
- Consent
- Permissions
- Firmware
- Security
- Future device types
This avoids building unrelated applications for every future device.

### Consequences
The mobile architecture should avoid unnecessary Band-only assumptions.

---

## DEC-003 — Consent Is a Core Architectural Requirement
**Status:** Accepted
**Category:** Consent / Security

### Decision
Consent will be treated as a fundamental system capability rather than a user-interface preference.

Remote interactions require an authorised relationship and current recipient permission.

### Reason
Soul's Echo enables remote physical interaction.

This creates risks of unwanted interaction if consent is implemented poorly.

### Consequences
The platform must support:

- Acceptance
- Rejection
- Permission management
- Pause
- Revocation
- Disconnection
- Local override
Consent cannot be permanently inferred from an earlier relationship state.

---

## DEC-004 — Local User Control Overrides Remote Control
**Status:** Accepted
**Category:** Safety / Consent

### Decision
The person possessing or wearing a Soul's Echo device retains ultimate control over that device.

### Reason
Remote access must never remove the recipient's ability to stop or disable interaction.

### Consequences
Firmware and application design must preserve:

- Local safety bounds
- Pause capability
- Revocation
- Reset behaviour
- Disconnect controls
Remote services may not bypass local safety controls.

---

## DEC-005 — Privacy by Design
**Status:** Accepted
**Category:** Privacy

### Decision
Soul's Echo will follow a data-minimisation approach.

The system should not collect or retain personal information merely because doing so is technically easy.

### Reason
The platform concerns private personal relationships and potentially sensitive interaction patterns.

Unnecessary collection increases risk without necessarily increasing user value.

### Consequences
Every significant persistent personal-data field should have a defensible purpose.

Detailed historical interaction storage is not assumed to be part of the MVP.

---

## DEC-006 — No Advertising-Based MVP Business Model
**Status:** Accepted
**Category:** Commercial / Privacy

### Decision
Advertising will not form part of the initial Soul's Echo business model.

### Reason
Advertising commonly encourages profiling, attention maximisation and data collection that conflict with the intended product philosophy.

### Consequences
The MVP commercial model should focus on direct customer value rather than advertising inventory.

---

## DEC-007 — Soul's Echo Will Not Be Designed as a Social Network
**Status:** Accepted
**Category:** Product

### Decision
The MVP will not include:

- Public feeds
- Followers
- Public profiles designed around popularity
- Engagement-driven content systems

### Reason
These functions are not required to deliver the core connected-presence experience.

### Consequences
Social-network mechanics remain outside the MVP unless future evidence supports a deliberate strategic change.

---

## DEC-008 — No Continuous Location Tracking for the Core Experience
**Status:** Accepted
**Category:** Privacy / Product

### Decision
Continuous user location tracking will not be required for the core Soul's Echo experience.

### Reason
Remote presence does not inherently require location surveillance.

### Consequences
Future location-related features would require separate justification and privacy assessment.

---

## DEC-009 — No Medical Positioning for the Initial Band
**Status:** Accepted
**Category:** Product / Regulatory

### Decision
The initial Soul's Echo Band is not being defined as a medical device.

Medical diagnosis and medical monitoring are excluded from the MVP.

### Reason
Medical functionality would significantly change:

- Regulatory obligations
- Validation requirements
- Risk profile
- Claims
- Product architecture

### Consequences
Medical or clinical claims must not be introduced without separate research, regulatory analysis and approval.

---

## DEC-010 — Evidence-Gated Development
**Status:** Accepted
**Category:** Development Process

### Decision
Soul's Echo will use evidence-based development gates.

### Reason
The project combines substantial hardware, software, manufacturing, regulatory and commercial risk.

Moving directly from concept to production would create unnecessary risk.

### Consequences
Major investment should follow validation rather than enthusiasm alone.

---

## DEC-011 — Customer Validation Precedes Major Hardware Investment
**Status:** Accepted
**Category:** Customer / Commercial

### Decision
Customer and problem validation should occur before substantial custom-hardware investment.

### Reason
A technically successful product can still fail if customers do not value the underlying proposition.

### Consequences
Gate 1 customer research is a major project priority after the foundation stage.

---

## DEC-012 — Logical Architecture Before Technology Selection
**Status:** Accepted
**Category:** Technical Architecture

### Decision
The project will define system responsibilities and trust boundaries before permanently selecting major technologies.

### Reason
Selecting familiar technologies too early could create avoidable limitations in:

- BLE reliability
- Power consumption
- Security
- Maintainability
- Cost
- Hardware compatibility

### Consequences
Major stack decisions remain open until structured comparison is completed.

---

## DEC-013 — Modular Monolith Preferred for the Initial Backend
**Status:** Accepted
**Category:** Backend

### Decision
The initial backend should prefer a modular monolith unless evidence demonstrates a clear need for distributed microservices.

### Reason
A modular monolith provides:

- Lower infrastructure complexity
- Easier local development
- Easier testing
- Simpler deployment
- Lower operational overhead

### Consequences
Clear internal module boundaries should still be maintained.

Future extraction into separate services remains possible.

---

## DEC-014 — Relational Database Is the Preliminary Data Architecture Preference
**Status:** Accepted with Review Required
**Category:** Data Architecture

### Decision
A relational data model is the preliminary architectural preference for core platform records.

This is not yet a final database-product selection.

### Reason
Soul's Echo contains strongly related concepts including:

- Users
- Devices
- Ownership
- Relationships
- Consent
- Permissions
These benefit from strong integrity constraints and transactional behaviour.

### Consequences
Relational database technologies should receive priority in the later technology comparison.

---

## DEC-015 — Bluetooth Low Energy Is the Preliminary Band-to-Phone Communication Method
**Status:** Accepted with Review Required
**Category:** Hardware / Firmware / Mobile

### Decision
Bluetooth Low Energy is the preliminary communication method between the Soul's Echo Band and Companion App.

### Reason
BLE is widely supported on consumer mobile devices and is designed for low-power local wireless communication.

### Consequences
BLE security, background behaviour, battery consumption and platform limitations require structured validation.

---

## DEC-016 — Remote Physical Events Must Be Bounded
**Status:** Accepted
**Category:** Safety / Security

### Decision
Remote haptic and light events must have local limits.

### Reason
Unlimited duration, intensity or repetition would introduce unnecessary safety and abuse risks.

### Consequences
Firmware must enforce approved maximum limits regardless of remote instructions.

---

## DEC-017 — Old Events Must Not Remain Valid Indefinitely
**Status:** Accepted
**Category:** Reliability / Security

### Decision
Remote interaction events require an expiry mechanism.

### Reason
A delayed physical interaction delivered long after its intended context could be confusing, unwanted or unsafe.

### Consequences
Final expiry windows remain to be determined through product and technical testing.

---

## DEC-018 — Duplicate Delivery Must Not Create Uncontrolled Repetition
**Status:** Accepted
**Category:** Reliability / Safety

### Decision
The system architecture must account for duplicate event delivery.

### Reason
Networks retry messages and distributed systems may process the same request more than once.

### Consequences
Appropriate idempotency, deduplication or local safeguards must be implemented.

---

## DEC-019 — Australia Is the Preliminary First Commercial Market
**Status:** Accepted with Review Required
**Category:** Commercial / Regulatory

### Decision
Australia is the current assumed initial market for Soul's Echo.

### Reason
Beginning with one primary jurisdiction simplifies early commercial and regulatory planning.

### Consequences
Australian legal and regulatory requirements should be mapped first.

International expansion requires separate assessment.

---

## DEC-020 — Australian English Is the Repository Documentation Standard
**Status:** Accepted
**Category:** Development Process

### Decision
Project documentation should use Australian English.

### Consequences
Documentation should use forms such as:

- authorised
- organisation
- behaviour
- licence where appropriate

---

## DEC-021 — The Repository Is the Technical Source of Truth
**Status:** Accepted
**Category:** Development Process

### Decision
Important technical and product decisions must progressively be documented within the repository.

### Reason
Critical project knowledge should not exist only in external conversations.

### Consequences
ChatGPT and Codex may support the work, but the repository documentation should remain authoritative for implementation.

---

## DEC-022 — Major Decisions Must Be Recorded Explicitly
**Status:** Accepted
**Category:** Development Process

### Decision
Significant architectural, product and security decisions must be recorded in this file.

### Consequences
Prototype code does not automatically establish a permanent production decision.

---

# DEFERRED DECISIONS

## 4. Technology Decisions Still Open
The following decisions are currently deferred:

- Microcontroller / SoC
- Secure element
- Haptic actuator
- Local input technology
- Battery chemistry
- Charging method
- Firmware framework
- RTOS
- Bootloader
- Mobile framework
- BLE application library
- Backend language
- Backend framework
- Production database
- Authentication provider
- Cloud provider
- Real-time delivery architecture
- Push-notification architecture
- Analytics platform
- Monitoring platform
- CI/CD platform
- Manufacturing partner
These must not be silently treated as settled.

---

# FUTURE DECISION TEMPLATE

## DEC-XXX — Decision Title
**Status:** Proposed / Accepted / Superseded / Rejected / Deferred
**Category:** Category
**Date:** YYYY-MM-DD

### Decision
State the decision clearly.

### Context
Explain the problem or situation requiring a decision.

### Evidence
Document relevant evidence, research, prototypes or constraints.

### Alternatives Considered
List realistic alternatives.

### Reason
Explain why this option was selected.

### Consequences
Document:

- Benefits
- Costs
- Risks
- Constraints
- Follow-up work

### Review Trigger
Identify conditions that would justify reconsidering the decision.

---

# DECISION GOVERNANCE

## 5. When a Decision Record Is Required
Create or update a decision record when a choice significantly affects:

- Architecture
- Security
- Privacy
- Consent
- Hardware
- Manufacturing
- Cost
- Customer experience
- Regulatory exposure
- Product scope
- Long-term maintainability
Minor implementation details do not necessarily require individual records.

---

## 6. Superseding Decisions
Do not delete an accepted decision merely because it changes.

Instead:

1. Mark the original decision as **Superseded**.
2. Reference the new decision.
3. Preserve the original reasoning.
This creates an auditable history.

---

## 7. Evidence Standard
Evidence may include:

- Customer interviews
- Usability testing
- Technical prototypes
- Benchmarking
- Security review
- Supplier information
- Regulatory research
- Cost analysis
- Manufacturing feedback
A personal preference may influence a decision, but it should not be misrepresented as external evidence.

---

## 8. Reversible and Irreversible Decisions
Where practical, identify whether a decision is:

### Easily Reversible
Low cost to change later.

### Moderately Reversible
Change is possible but creates meaningful rework.

### Difficult to Reverse
Embedded in:

- Hardware
- Manufacturing
- Security architecture
- Data model
- Public API
- Commercial commitments
Difficult-to-reverse decisions require stronger evidence before approval.

---

## 9. Governing Principle
The purpose of this register is not bureaucracy.

Its purpose is to stop Soul's Echo from forgetting **why** important choices were made.

A well-documented decision can be challenged intelligently later.

An undocumented decision can only be guessed at.
