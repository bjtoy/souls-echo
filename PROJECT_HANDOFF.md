# Soul's Echo — Project Handoff
**Project:** Soul's Echo
**Repository:** `bjtoy/souls-echo`
**Document purpose:** Development handoff for Codex and future contributors
**Status:** Pre-development / concept foundation
**Primary product:** Soul's Echo Band
**Platform:** Soul's Echo Companion App

---

## 1. Project Purpose
Soul's Echo is a premium connected-product ecosystem designed to make meaningful human connection feel present, tangible and private across physical distance.

The project combines physical connected devices with a secure digital platform.

Rather than relying solely on messages, notifications or conventional social communication, Soul's Echo is intended to translate deliberate digital interactions into subtle physical experiences.

The system must place privacy, consent, safety and user control ahead of engagement or convenience.

Soul's Echo is intended to become an ecosystem rather than a single-product application.

---

## 2. Mission
Create technology that allows people to intentionally communicate presence and connection through physical experiences while protecting individual choice, consent, security and privacy.

---

## 3. Product Principles
All Soul's Echo products and software must follow these principles.

### Privacy by Design
Collect and retain the minimum information required for the system to operate.

Do not introduce unnecessary tracking, analytics or personal-data collection.

### Explicit Consent
Connections between people and devices must be deliberate and authorised.

Consent must be understandable, granular and revocable.

### User Control
A user must always be capable of stopping, disabling or revoking a remote interaction.

Remote interaction must never override a user's local control of their device.

The Band must provide a phone-independent local means of inhibiting incoming
remote physical interactions. Its physical implementation remains unresolved.

### Safety and Reliability
Physical and digital safety take priority over additional features.

Security, reliability and predictable device behaviour are product requirements rather than optional enhancements.

### Premium and Discreet Design
Soul's Echo products should resemble desirable personal objects rather than conspicuous pieces of technology.

### Accessibility
Accessibility should be considered throughout hardware and software development rather than added after the product is completed.

### Expandable Architecture
The Band MVP should avoid obvious architectural dead ends where practical, but
future products must not introduce speculative MVP complexity.

---

## 4. Product Ecosystem
The long-term Soul's Echo ecosystem may include:

- Soul's Echo Band
- Soul's Echo Ring
- Soul's Echo Pendant
- Soul's Echo Dock
- Soul's Echo Companion App
- Wellness Collection
- Accessories
- Future compatible devices and experiences
The first physical product is the **Soul's Echo Band**.

The **Soul's Echo Companion App** is intended to become the common software platform across the ecosystem.

---

## 5. Soul's Echo Band — MVP
The Band is the flagship minimum viable product.

The initial Band must support:

- Secure pairing between two authorised users.
- Bluetooth Low Energy communication with the user's phone.
- Secure communication through the Soul's Echo internet service.
- Deliberate touch-triggered remote interactions.
- Remote haptic feedback.
- Remote light feedback.
- Immediate disconnect and revoke controls.
- Distinct pause, block, disconnect and permission-revocation controls.
- Phone-independent Band-local inhibition of incoming remote interactions.
- Battery-level reporting.
- Secure firmware updates.
- Firmware integrity verification.
- Appropriate durability and ingress protection targets.
- Validated battery-performance targets.
- Interchangeable or customisable aesthetic elements where practical.
- Architecture that avoids obvious future dead ends without speculative future-product implementation.
A user must not be capable of secretly or permanently controlling another person's Band.

Remote interactions require an authorised relationship between users.

Recipient authority and current recipient authorisation take precedence. No
interaction has a guaranteed right to eventual physical delivery.

---

## 6. Companion App
The Companion App will provide the digital interface between users, devices and Soul's Echo services.

Its responsibilities are expected to include:

- Account management.
- Device registration.
- Device pairing.
- User-to-user connection management.
- Consent management.
- Permission management.
- Device status.
- Battery information.
- Connection status.
- Interaction controls.
- Security settings.
- Firmware-update management.
- Disconnect and revoke functions.
- Future multi-device ecosystem management.
The application architecture must not assume the Band will remain the only Soul's Echo product.

---

## 7. Security and Privacy
Security and privacy are foundational product requirements.

Development must consider:

- Encryption in transit.
- Secure authentication.
- Device authentication.
- Secure pairing.
- Authorisation of remote interactions.
- Minimal data collection.
- Appropriate data retention.
- Secure credential storage.
- Signed or integrity-protected firmware.
- Revocation mechanisms.
- Local device safety controls.
- Protection against unwanted remote control.
- Protection against replay or impersonation attacks.
- Secure backend APIs.
- Australian privacy obligations.
- Future international privacy requirements.
Convenience must not be used as justification for weakening consent or security.

---

## 8. Consent Model
Consent is a core architectural requirement.

Users must knowingly establish connections.

Users must be capable of:

- Accepting a connection.
- Rejecting a connection.
- Controlling permitted interactions.
- Temporarily disabling interactions.
- Disconnecting another user.
- Revoking permissions.
- Removing a paired relationship.
Revocation should take effect promptly.

Pause, block, disconnect, permission revocation, local inhibit and factory reset
are distinct operations. Blocking invalidates undelivered interactions from the
blocked party. Revocation or permission reduction invalidates affected
interactions that have not produced physical output.

Protective actions should not unnecessarily disclose sensitive recipient status
to another user.

No future feature should assume that previous consent represents permanent consent.

---

## 9. Current Development Status
Soul's Echo is currently in **pre-development**.

### Gate 0 — Concept Foundation
Status: **In progress**

The project has established:

- Core product vision.
- Ecosystem strategy.
- Band-first development strategy.
- Companion App concept.
- Initial security principles.
- Initial consent principles.
- Initial risk identification.
- Development-gate approach.
- Documentation and version-control requirements.

All planned foundation documents exist. Gate 0 remains open until the consistency
and recipient-control exit checklist passes.

### Gate 1 — Validation
This is the next major stage.

Development should not jump directly to manufacturing or production software before the underlying product assumptions have been validated.

---

## 10. Development Gates
The planned development sequence is:

1. Concept foundation.
2. Market and customer validation.
3. Product definition.
4. Technical architecture.
5. Prototype development.
6. Alpha testing.
7. Beta testing.
8. Manufacturing preparation.
9. Compliance and pilot.
10. Commercial launch.
11. Ecosystem expansion.
Movement between major stages should be supported by evidence rather than assumption.

---

## 11. Immediate Work
The next work should include:

### Brand and Intellectual Property

- Preliminary Soul's Echo trademark screening.
- Business-name screening.
- Domain availability research.
- Social-handle availability research.
- Competitor research.
- Prior-art research.

### Customer Validation

- Define target customers.
- Develop Jobs-to-be-Done hypotheses.
- Conduct customer/problem validation.
- Test willingness to use and purchase the product.
- Validate the emotional value proposition.

### Industrial Design
Develop at least three initial Band design directions.

Document the reasoning behind the selected direction.

### Product Requirements
Develop the Band Product Requirements Document to the next level of detail.

Requirements must distinguish between:

- Mandatory MVP requirements.
- Desirable features.
- Future features.
- Explicitly excluded features.

### Technical Architecture
Define the preliminary architecture covering:

- Band electronics.
- Firmware.
- Bluetooth communication.
- Mobile application.
- Backend.
- Authentication.
- Device identity.
- Pairing.
- Event delivery.
- Security.
- Firmware updates.

Technology selection remains deferred until the relevant product, security,
failure and feasibility questions are defined. Lost, stolen, compromised,
replacement and transferred devices require logical revocation and recovery
workflows.

### Regulation and Compliance
Prepare an initial Australian regulatory map covering relevant areas including:

- Consumer product safety.
- Electrical/electronic requirements.
- Radio communications.
- Battery requirements.
- Privacy.
- Data protection.
- Cybersecurity.
- Product claims.

### Commercial Validation
Develop:

- Preliminary unit economics.
- Prototype budget.
- Manufacturing assumptions.
- Indicative retail pricing.
- Commercialisation assumptions.

---

## 12. Known Risks
Important project risks currently include:

### Intellectual Property
The Soul's Echo name or product concepts may conflict with existing intellectual property.

### Privacy and Security
A security compromise involving an intimate connected device could cause significant harm to users and the brand.

### Unwanted Remote Interaction
The platform could be misused if consent and permission systems are poorly designed.

### Unsupported Claims
Battery life, durability, wellness or performance claims must not be published without adequate validation.

### Manufacturing
Hardware quality, component availability and supplier reliability may affect the product.

### Regulation
Requirements may differ across markets and product categories.

### Scope Expansion
Attempting to develop the entire ecosystem before validating the Band could significantly increase cost and project risk.

---

## 13. Risk Controls
Current controls include:

- Explicit pairing.
- Granular permissions.
- Disconnect controls.
- Revocation controls.
- Local safety overrides.
- Authentication.
- Encryption.
- Secure firmware.
- Staged MVP development.
- Evidence gates.
- Supplier quality assurance.
- No unvalidated product claims.
- Documentation of important technical and commercial decisions.

---

## 14. Future Product Areas
Future concepts include the Ring, Pendant, Dock and Wellness Collection.

These are **not part of the initial MVP**.

Adult wellness or intimacy-related products must not simply inherit assumptions from the Band.

Any such product requires its own:

- Safety assessment.
- Consent model.
- Risk analysis.
- Regulatory assessment.
- User research.
- Product validation.

---

## 15. Development Rules
Before making substantial implementation decisions:

1. Read this document.
2. Read `CODEX.md`.
3. Read the relevant files in `/docs`.
4. Inspect the existing repository.
5. Do not assume missing requirements.
6. Prefer simple, secure and maintainable architecture.
7. Do not weaken privacy or consent requirements to simplify implementation.
8. Do not introduce unnecessary third-party services.
9. Do not make unsupported health, wellness, battery, durability or security claims.
10. Document significant architectural decisions.

---

## 16. Source of Truth
The Git repository should become the technical source of truth for Soul's Echo.

Important decisions must not exist only in ChatGPT conversations.

Product decisions, requirements, architecture and significant changes should be documented within the repository.

ChatGPT may continue to be used for product planning and decision-making.

Codex may be used for repository analysis and implementation.

The repository documentation connects these two workflows.

---

## 17. Initial Codex Instruction
When Codex first opens this project, use the following instruction:

> Read `PROJECT_HANDOFF.md`, `CODEX.md`, `README.md` and all documents under `/docs` before modifying anything.
> 
> Inspect the complete repository and establish the actual current state of the project.
> 
> Do not begin implementing speculative features.
> 
> Identify missing requirements, contradictions, security concerns and architectural decisions that require resolution.
> 
> Then recommend the next development task based on the documented roadmap and current project state.
