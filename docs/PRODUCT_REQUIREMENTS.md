# Soul's Echo — Product Requirements
**Document:** Product Requirements
**Project:** Soul's Echo
**Product:** Soul's Echo Band and Supporting Platform
**Status:** Draft Requirements Baseline
**Phase:** Pre-development
**Version:** 0.1

---

## 1. Purpose
This document defines the preliminary product requirements for the first Soul's Echo minimum viable product.

The MVP consists of:

1. Soul's Echo Band.
2. Soul's Echo Companion App.
3. Supporting backend services.
4. Device firmware.
5. Security, consent and account-management capabilities required to operate the system safely.
These requirements convert the product vision into capabilities that can progressively become measurable, testable and traceable.

This document remains subject to customer validation, technical feasibility assessment, prototyping, safety assessment and regulatory review.

---

## 2. Requirement Language
The following terminology is used:

**MUST** — mandatory requirement.

**SHOULD** — desirable requirement unless evidence demonstrates that it should become mandatory.

**MAY** — optional capability.

Requirements marked as targets must not be represented as validated capabilities until testing confirms them.

---

## 3. Priority Classification
Each requirement is assigned one of the following classifications.

### MVP Mandatory
Required for the first viable Soul's Echo Band system.

### MVP Desirable
Valuable for the MVP but may be deferred if cost, risk or schedule requires.

### Post-MVP
Not required for the first commercially viable version.

### Future Research
Concept requiring additional validation before inclusion in the product roadmap.

---

# PART A — SYSTEM REQUIREMENTS

## 4. Core System

### SYS-001 — End-to-End System
**Priority:** MVP Mandatory

The system MUST provide an end-to-end interaction path consisting of:

Band → Companion App → Soul's Echo Service → Recipient Companion App → Recipient Band.

The final architecture may optimise this pathway where security and reliability permit.

---

### SYS-002 — Authorised Relationships
**Priority:** MVP Mandatory

Remote interactions MUST only occur between users with an active, mutually authorised Soul's Echo relationship.

---

### SYS-003 — Local Control
**Priority:** MVP Mandatory

The owner or authorised local user of a Band MUST retain ultimate control over whether remote interactions are accepted by their device.

---

### SYS-004 — Revocation
**Priority:** MVP Mandatory

The system MUST support revocation of an established user relationship.

Revocation MUST prevent subsequent remote interaction once the updated authorisation state has propagated through the system.

---

### SYS-005 — Safe Failure
**Priority:** MVP Mandatory

Loss of connectivity, backend failure, application failure or malformed communication MUST NOT cause uncontrolled physical output from the Band.

---

### SYS-006 — Ecosystem Extensibility
**Priority:** MVP Mandatory

The core identity, device, consent and event architecture SHOULD support future Soul's Echo device types without requiring replacement of the fundamental account model.

---

# PART B — BAND REQUIREMENTS

## 5. Physical Band

### BAND-FR-001 — Wearable Form
**Priority:** MVP Mandatory

The Band MUST be designed as a wearable personal device suitable for routine use.

Final dimensions, weight and materials remain subject to industrial-design validation.

---

### BAND-FR-002 — Haptic Output
**Priority:** MVP Mandatory

The Band MUST be capable of producing controlled haptic feedback.

Haptic duration and intensity MUST remain within validated safe operating limits.

---

### BAND-FR-003 — Light Output
**Priority:** MVP Mandatory

The Band MUST be capable of producing subtle visual feedback through one or more light-emitting components.

---

### BAND-FR-004 — Local Input
**Priority:** MVP Mandatory

The Band MUST provide at least one deliberate local interaction mechanism capable of initiating an authorised Soul's Echo event.

The final input mechanism may include capacitive touch, pressure, button input or another validated approach.

---

### BAND-FR-005 — Accidental Activation
**Priority:** MVP Mandatory

The Band SHOULD minimise unintended activation during ordinary wear.

The final interaction design MUST be validated through prototype testing.

---

### BAND-FR-006 — Battery Operation
**Priority:** MVP Mandatory

The Band MUST operate from an internal rechargeable power source.

---

### BAND-FR-007 — Battery Reporting
**Priority:** MVP Mandatory

The Band MUST make battery status available to the Companion App.

---

### BAND-FR-008 — Low-Battery Behaviour
**Priority:** MVP Mandatory

The Band MUST enter predictable and safe behaviour when battery capacity becomes critically low.

---

### BAND-FR-009 — Charging
**Priority:** MVP Mandatory

The Band MUST provide a safe charging mechanism appropriate to the final battery and industrial design.

The charging method remains to be determined.

---

### BAND-FR-010 — Battery-Life Target
**Priority:** MVP Desirable

A commercial battery-life target MUST be established during engineering validation.

No specific battery-duration claim is considered approved at this stage.

---

### BAND-FR-011 — Water and Ingress Resistance
**Priority:** MVP Mandatory

An appropriate ingress-protection target MUST be established before final hardware design.

No water-resistance rating may be claimed until appropriately validated.

---

### BAND-FR-012 — Comfort
**Priority:** MVP Mandatory

The Band MUST be suitable for the intended duration of wear without unreasonable discomfort.

This requirement requires physical user testing.

---

### BAND-FR-013 — Aesthetic Customisation
**Priority:** MVP Desirable

The design SHOULD permit reasonable aesthetic personalisation through interchangeable components, finishes or related mechanisms where technically and commercially feasible.

---

### BAND-FR-014 — No Mandatory Display
**Priority:** MVP Mandatory

The MVP Band MUST NOT require a conventional smartwatch-style screen to deliver its core experience.

---

# PART C — BLUETOOTH AND LOCAL COMMUNICATION

## 6. Bluetooth Low Energy

### BLE-001 — BLE Communication
**Priority:** MVP Mandatory

The Band MUST communicate with the Companion App using Bluetooth Low Energy or another explicitly approved low-power communication technology.

---

### BLE-002 — Secure Pairing
**Priority:** MVP Mandatory

Device pairing MUST use an authenticated and appropriately secure process.

---

### BLE-003 — Device Identity
**Priority:** MVP Mandatory

Each Band MUST have a unique device identity suitable for secure registration and authorisation.

---

### BLE-004 — Device Names
**Priority:** MVP Mandatory

Human-readable Bluetooth device names MUST NOT be treated as secure device identifiers.

---

### BLE-005 — Reconnection
**Priority:** MVP Mandatory

The Band and Companion App SHOULD automatically re-establish an authorised local connection after temporary BLE loss where safe and appropriate.

---

### BLE-006 — Unauthorised Nearby Devices
**Priority:** MVP Mandatory

A nearby unauthorised device MUST NOT be capable of issuing valid Soul's Echo interaction commands to the Band.

---

### BLE-007 — Factory Reset
**Priority:** MVP Mandatory

The Band MUST provide a secure factory-reset mechanism.

Reset behaviour MUST invalidate or remove relevant previous pairing state.

---

### BLE-008 — Ownership Transfer
**Priority:** MVP Mandatory

A defined process MUST exist for legitimately transferring a Band to another user.

Previous ownership MUST NOT provide continuing remote access after transfer is completed.

---

# PART D — FIRMWARE

## 7. Firmware Requirements

### FW-001 — Device Control
**Priority:** MVP Mandatory

Firmware MUST control local input, haptic output, light output, BLE communication, battery reporting and relevant device-state behaviour.

---

### FW-002 — Secure Update
**Priority:** MVP Mandatory

The system MUST provide a secure firmware-update mechanism.

---

### FW-003 — Firmware Integrity
**Priority:** MVP Mandatory

The Band MUST reject firmware that fails the approved authenticity or integrity-verification process.

---

### FW-004 — Interrupted Update
**Priority:** MVP Mandatory

An interrupted firmware update MUST NOT unnecessarily render the device permanently unusable.

A recovery strategy MUST be defined.

---

### FW-005 — Firmware Version
**Priority:** MVP Mandatory

The Companion App MUST be capable of determining the installed Band firmware version.

---

### FW-006 — Unsupported Firmware
**Priority:** MVP Mandatory

The platform MUST be capable of identifying firmware versions that are no longer supported.

---

### FW-007 — Event Validation
**Priority:** MVP Mandatory

Firmware MUST validate incoming interaction instructions before activating physical outputs.

---

### FW-008 — Output Bounds
**Priority:** MVP Mandatory

Firmware MUST enforce local limits on physical output duration, intensity and repetition.

Remote services MUST NOT be capable of bypassing these local safety bounds.

---

# PART E — COMPANION APP

## 8. Application Requirements

### APP-FR-001 — Account Access
**Priority:** MVP Mandatory

The Companion App MUST provide secure user authentication.

---

### APP-FR-002 — Device Registration
**Priority:** MVP Mandatory

Users MUST be able to register an eligible Band to their account through an authorised setup process.

---

### APP-FR-003 — Device Setup
**Priority:** MVP Mandatory

The application MUST guide users through initial Band setup and pairing.

---

### APP-FR-004 — Device Status
**Priority:** MVP Mandatory

The application MUST display sufficient status information to understand whether the registered Band is available.

---

### APP-FR-005 — Battery Status
**Priority:** MVP Mandatory

The application MUST display available Band battery information.

---

### APP-FR-006 — Connection Requests
**Priority:** MVP Mandatory

Users MUST be able to send, receive, accept and reject Soul's Echo connection requests.

---

### APP-FR-007 — Relationship Status
**Priority:** MVP Mandatory

The application MUST make the current connection relationship understandable to the user.

---

### APP-FR-008 — Permission Management
**Priority:** MVP Mandatory

Users MUST be able to review and modify the permissions granted to connected users.

---

### APP-FR-009 — Pause
**Priority:** MVP Mandatory

Users MUST be able to temporarily prevent remote interactions without necessarily terminating the relationship.

---

### APP-FR-010 — Disconnect
**Priority:** MVP Mandatory

Users MUST be able to terminate an established Soul's Echo relationship.

---

### APP-FR-011 — Firmware Update
**Priority:** MVP Mandatory

The application MUST support the approved firmware-update workflow.

---

### APP-FR-012 — Accessibility
**Priority:** MVP Mandatory

Core application functionality MUST be designed with accessibility requirements in mind.

---

### APP-FR-013 — Multi-Device Architecture
**Priority:** MVP Mandatory

The application architecture SHOULD support future ownership of multiple Soul's Echo devices.

The initial interface MAY expose only functionality required by the Band.

---

### APP-FR-014 — Interaction History
**Priority:** Future Research

Detailed historical interaction records MUST NOT be assumed to be an MVP requirement.

Privacy value, emotional value and user demand must be evaluated before introducing persistent interaction histories.

---

# PART F — CONSENT

## 9. Consent Requirements

### CONSENT-001 — Mutual Establishment
**Priority:** MVP Mandatory

A user-to-user Soul's Echo relationship MUST require deliberate participation from both users.

---

### CONSENT-002 — No Automatic Consent
**Priority:** MVP Mandatory

Purchasing, gifting or physically possessing another person's device MUST NOT automatically grant access to that person's Soul's Echo interactions.

---

### CONSENT-003 — Understandable Permissions
**Priority:** MVP Mandatory

Permission requests MUST be presented in language understandable to an ordinary user.

---

### CONSENT-004 — Granular Control
**Priority:** MVP Mandatory

The architecture MUST support permissions at sufficient granularity to prevent unnecessary all-or-nothing remote access.

The final permission model requires UX validation.

---

### CONSENT-005 — Revocable Consent
**Priority:** MVP Mandatory

A user MUST be capable of withdrawing previously granted consent.

---

### CONSENT-006 — Independent Revocation
**Priority:** MVP Mandatory

Revoking a connection MUST NOT require approval from the other connected user.

---

### CONSENT-007 — Pause
**Priority:** MVP Mandatory

A user MUST be capable of temporarily suspending incoming remote interactions.

---

### CONSENT-008 — Local Override
**Priority:** MVP Mandatory

Local device safety controls MUST take precedence over remote permissions.

---

### CONSENT-009 — Relationship Change
**Priority:** MVP Mandatory

The system MUST NOT assume that consent granted during an existing personal relationship remains valid indefinitely.

---

# PART G — REMOTE INTERACTION

## 10. Event Requirements

### EVENT-001 — Intentional Initiation
**Priority:** MVP Mandatory

A remote interaction MUST originate from an intentional authorised action.

---

### EVENT-002 — Authorisation Check
**Priority:** MVP Mandatory

The system MUST verify that the sender is authorised to initiate the requested interaction.

---

### EVENT-003 — Recipient Permission
**Priority:** MVP Mandatory

The system MUST verify that the recipient's current permission state allows the interaction.

---

### EVENT-004 — Bounded Output
**Priority:** MVP Mandatory

Physical outputs MUST have defined maximum duration and intensity limits.

---

### EVENT-005 — Rate Limiting
**Priority:** MVP Mandatory

The system MUST provide appropriate mechanisms to prevent excessive or abusive repeated interaction events.

---

### EVENT-006 — Duplicate Events
**Priority:** MVP Mandatory

Duplicate delivery MUST NOT result in uncontrolled repeated physical output.

---

### EVENT-007 — Delayed Events
**Priority:** MVP Mandatory

The system MUST define an expiry policy for delayed interaction events.

An old interaction SHOULD NOT unexpectedly activate a Band long after its intended context has passed.

---

### EVENT-008 — Replay Protection
**Priority:** MVP Mandatory

The system MUST protect against replay of previously valid interaction messages.

---

### EVENT-009 — Offline Recipient
**Priority:** MVP Mandatory

The product MUST define predictable behaviour when the recipient or recipient Band is offline.

The final delivery policy requires product and technical validation.

---

### EVENT-010 — Delivery Feedback
**Priority:** MVP Desirable

The sender SHOULD receive appropriately privacy-preserving feedback about whether an interaction was successfully delivered.

The system MUST NOT expose unnecessary recipient behavioural information merely to provide delivery status.

---

# PART H — BACKEND

## 11. Backend Requirements

### BACKEND-001 — Authentication
**Priority:** MVP Mandatory

Backend APIs MUST authenticate protected requests.

---

### BACKEND-002 — Authorisation
**Priority:** MVP Mandatory

Backend APIs MUST enforce server-side authorisation.

Client-side interface restrictions MUST NOT be treated as sufficient access control.

---

### BACKEND-003 — User Records
**Priority:** MVP Mandatory

The backend MUST maintain the minimum user records necessary to operate the service.

---

### BACKEND-004 — Device Records
**Priority:** MVP Mandatory

The backend MUST maintain sufficient information to identify registered devices and authorised ownership.

---

### BACKEND-005 — Relationship Records
**Priority:** MVP Mandatory

The backend MUST maintain sufficient state to determine whether a valid Soul's Echo relationship exists.

---

### BACKEND-006 — Permission State
**Priority:** MVP Mandatory

Current permission and revocation state MUST be enforceable by backend services.

---

### BACKEND-007 — Event Routing
**Priority:** MVP Mandatory

The backend MUST securely route authorised interaction events between appropriate users and devices.

---

### BACKEND-008 — Idempotency
**Priority:** MVP Mandatory

Operations capable of causing duplicated physical effects SHOULD use appropriate idempotency or duplicate-prevention mechanisms.

---

### BACKEND-009 — Service Failure
**Priority:** MVP Mandatory

Backend failure MUST fail safely and MUST NOT implicitly grant access or bypass permission checks.

---

### BACKEND-010 — Modular Architecture
**Priority:** MVP Mandatory

The initial backend SHOULD favour a maintainable modular architecture rather than unnecessary distributed microservices.

---

# PART I — SECURITY

## 12. Security Requirements

### SEC-001 — Encryption in Transit
**Priority:** MVP Mandatory

Sensitive communications MUST use current, appropriately secure transport encryption.

---

### SEC-002 — Password Handling
**Priority:** MVP Mandatory

If passwords are used, they MUST be processed using an appropriate modern password-hashing mechanism.

Plain-text passwords MUST never be stored.

---

### SEC-003 — Secret Management
**Priority:** MVP Mandatory

Production secrets MUST NOT be hard-coded or committed to version control.

---

### SEC-004 — Authentication Sessions
**Priority:** MVP Mandatory

Authentication sessions or tokens MUST use appropriately secure lifecycle and storage practices.

---

### SEC-005 — Device Authentication
**Priority:** MVP Mandatory

The architecture MUST provide a method of distinguishing legitimate registered Soul's Echo devices from unauthorised devices.

---

### SEC-006 — Least Privilege
**Priority:** MVP Mandatory

Components and users SHOULD receive only the access required for their intended functions.

---

### SEC-007 — Input Validation
**Priority:** MVP Mandatory

Externally supplied data MUST be validated at appropriate trust boundaries.

---

### SEC-008 — Rate Limiting
**Priority:** MVP Mandatory

Security-sensitive and abuse-prone endpoints MUST implement appropriate rate controls.

---

### SEC-009 — Account Recovery
**Priority:** MVP Mandatory

A secure account-recovery process MUST be defined before commercial deployment.

---

### SEC-010 — Vulnerability Management
**Priority:** MVP Mandatory

A process MUST exist for identifying, assessing and responding to significant vulnerabilities in application, backend, firmware and dependencies.

---

### SEC-011 — Security Logging
**Priority:** MVP Mandatory

Security-relevant events SHOULD be logged where necessary for security and incident response.

Logs MUST avoid unnecessary sensitive personal information.

---

### SEC-012 — Security Review
**Priority:** MVP Mandatory

Authentication, authorisation, pairing, consent, firmware updates and remote-event handling MUST receive dedicated security review before commercial release.

---

# PART J — PRIVACY

## 13. Privacy Requirements

### PRIV-001 — Data Minimisation
**Priority:** MVP Mandatory

Soul's Echo MUST collect only personal information reasonably required for legitimate product, security, support or legal purposes.

---

### PRIV-002 — No Advertising Profiling
**Priority:** MVP Mandatory

The MVP MUST NOT require behavioural advertising profiles.

---

### PRIV-003 — No Mandatory Location Tracking
**Priority:** MVP Mandatory

The core Soul's Echo experience MUST NOT require continuous user location tracking.

---

### PRIV-004 — Interaction Data
**Priority:** MVP Mandatory

The platform SHOULD minimise storage of detailed historical interaction data.

Any required event metadata MUST have a documented purpose.

---

### PRIV-005 — Retention
**Priority:** MVP Mandatory

Personal-data categories MUST have defined retention policies before commercial launch.

---

### PRIV-006 — Deletion
**Priority:** MVP Mandatory

The platform MUST provide an appropriate mechanism for account and personal-data deletion subject to legitimate legal and security requirements.

---

### PRIV-007 — Transparency
**Priority:** MVP Mandatory

Users MUST receive understandable information about what personal information is collected and why.

---

### PRIV-008 — Third Parties
**Priority:** MVP Mandatory

Third-party services MUST be assessed for privacy, security and data-processing implications before adoption.

---

### PRIV-009 — Relationship Privacy
**Priority:** MVP Mandatory

Information about private Soul's Echo relationships MUST NOT be made publicly discoverable by default.

---

# PART K — RELIABILITY

## 14. Reliability Requirements

### REL-001 — Connectivity Loss
**Priority:** MVP Mandatory

Temporary loss of internet connectivity MUST result in predictable behaviour.

---

### REL-002 — BLE Loss
**Priority:** MVP Mandatory

Temporary BLE disconnection MUST NOT corrupt device ownership or permission state.

---

### REL-003 — Backend Outage
**Priority:** MVP Mandatory

A backend outage MUST NOT cause unauthorised remote interaction.

---

### REL-004 — Application Closure
**Priority:** MVP Mandatory

The system MUST define expected behaviour when the Companion App is suspended or closed by the mobile operating system.

---

### REL-005 — Duplicate Processing
**Priority:** MVP Mandatory

The architecture MUST account for duplicate messages and retries.

---

### REL-006 — Clock Differences
**Priority:** MVP Mandatory

Security or expiry mechanisms that depend on time MUST appropriately account for realistic clock differences between system components.

---

# PART L — ACCESSIBILITY

## 15. Accessibility Requirements

### ACC-001 — Screen Reader Support
**Priority:** MVP Mandatory

Core Companion App workflows SHOULD support the accessibility APIs provided by supported mobile platforms.

---

### ACC-002 — Colour Independence
**Priority:** MVP Mandatory

Critical status information MUST NOT depend exclusively on colour.

---

### ACC-003 — Scalable Text
**Priority:** MVP Mandatory

The Companion App SHOULD appropriately support user text-size preferences.

---

### ACC-004 — Touch Targets
**Priority:** MVP Mandatory

Interactive application controls MUST use appropriately accessible touch-target dimensions.

---

### ACC-005 — Physical Accessibility Research
**Priority:** MVP Desirable

Band fastening, charging and interaction mechanisms SHOULD be evaluated with users who have varying levels of dexterity.

---

# PART M — REGULATORY AND COMMERCIAL REQUIREMENTS

## 16. Regulatory Requirements

### REG-001 — Australian Market
**Priority:** MVP Mandatory

Applicable Australian regulatory obligations MUST be identified before commercial sale.

---

### REG-002 — Radio Compliance
**Priority:** MVP Mandatory

Wireless hardware MUST satisfy applicable radio communications requirements for intended markets.

---

### REG-003 — Battery Compliance
**Priority:** MVP Mandatory

Battery selection, integration, charging, transport and commercial distribution MUST comply with applicable requirements.

---

### REG-004 — Consumer Law
**Priority:** MVP Mandatory

Product representations, warranties and customer processes MUST account for applicable Australian Consumer Law obligations.

---

### REG-005 — Privacy
**Priority:** MVP Mandatory

The project's privacy practices MUST be assessed against applicable Australian privacy obligations before commercial launch.

---

### REG-006 — International Expansion
**Priority:** Post-MVP

International markets MUST receive market-specific compliance assessment before launch.

Australian compliance MUST NOT be assumed to satisfy other jurisdictions.

---

# PART N — EXCLUDED MVP FEATURES

## 17. Explicit MVP Exclusions
Unless subsequently approved through the project decision process, the following are excluded from the initial MVP:

### EXCL-001 — General Messaging
Soul's Echo will not initially attempt to replace conventional text messaging.

### EXCL-002 — Voice Calling
Voice calling is not part of the Band MVP.

### EXCL-003 — Video Calling
Video communication is not part of the Band MVP.

### EXCL-004 — Social Feed
No public or private social-media-style feed is required.

### EXCL-005 — Followers
Follower/following mechanics are excluded.

### EXCL-006 — Advertising
Advertising is excluded from the MVP business model.

### EXCL-007 — Continuous Location Sharing
Continuous location sharing is excluded.

### EXCL-008 — Medical Monitoring
The Band is not currently specified as a medical device.

Medical diagnosis or monitoring functionality is excluded.

### EXCL-009 — Emergency Service
The Band MUST NOT be marketed as a replacement for emergency communications or emergency-response devices.

### EXCL-010 — Ring
Soul's Echo Ring implementation is excluded from the Band MVP.

### EXCL-011 — Pendant
Soul's Echo Pendant implementation is excluded from the Band MVP.

### EXCL-012 — Dock
Soul's Echo Dock implementation is excluded unless later required for Band charging or another essential MVP function.

### EXCL-013 — Wellness Collection
Wellness Collection implementation is outside the Band MVP and requires separate validation.

---

# PART O — FUTURE RESEARCH

## 18. Research Candidates
The following concepts may be investigated without being treated as approved requirements.

### RESEARCH-001 — Custom Interaction Patterns
Investigate whether users value creating private haptic or light patterns.

---

### RESEARCH-002 — Shared Rituals
Investigate recurring connection rituals and whether technology can support them without becoming intrusive.

---

### RESEARCH-003 — Multiple Connections
Investigate whether users require multiple simultaneous Soul's Echo relationships and how consent should operate.

---

### RESEARCH-004 — Gifting
Investigate gifting flows while ensuring the recipient independently controls connection consent.

---

### RESEARCH-005 — Premium Personalisation
Investigate materials, finishes, bands and personalisation as potential commercial differentiators.

---

### RESEARCH-006 — Charging Experience
Evaluate wired, magnetic, dock-based and other practical charging approaches.

---

### RESEARCH-007 — Interaction Confirmation
Research how much delivery confirmation users require without creating surveillance-like behavioural information.

---

# PART P — MVP ACCEPTANCE

## 19. Preliminary MVP Acceptance Criteria
The first complete MVP should not be considered ready for controlled testing until it can demonstrate the following end-to-end scenario:

1. User A creates or accesses an authorised Soul's Echo account.
2. User B independently creates or accesses another authorised account.
3. Each user securely registers a Band.
4. Both Bands securely pair with their respective Companion Apps.
5. User A requests a Soul's Echo connection with User B.
6. User B deliberately accepts.
7. Current permissions permit a defined remote interaction.
8. User A deliberately initiates that interaction.
9. The system validates User A.
10. The system validates the relationship.
11. The system validates User B's current permission.
12. The event is securely routed.
13. User B's Band validates the received event.
14. User B's Band produces a bounded physical response.
15. User B pauses or revokes the connection.
16. A subsequent attempt by User A is prevented.
17. The system remains safe during simulated network, application and Bluetooth failures.
Passing this scenario does not itself establish commercial readiness.

---

## 20. Commercial Readiness Is Separate
A technically functioning MVP MUST NOT automatically be considered ready for public sale.

Commercial readiness will additionally require appropriate:

- Customer validation
- Industrial-design validation
- Reliability testing
- Battery testing
- Safety assessment
- Security assessment
- Privacy assessment
- Accessibility review
- Regulatory compliance
- Manufacturing validation
- Quality assurance
- Support processes
- Legal review
- Product documentation

---

# PART Q — OPEN REQUIREMENTS

## 21. Decisions Still Required
The following remain deliberately unresolved:

- Final Band dimensions
- Final Band weight
- Materials
- Strap or attachment system
- Battery chemistry and capacity
- Battery-life target
- Charging architecture
- Haptic actuator
- Light architecture
- Local input mechanism
- Microcontroller
- BLE chipset
- Secure element requirement
- Firmware platform
- Mobile framework
- Backend language/framework
- Database
- Cloud provider
- Authentication provider
- Push/event-delivery architecture
- Detailed permission model
- Event-expiry duration
- Rate limits
- Offline-event policy
- Account-recovery implementation
- Supported mobile operating-system versions
- Manufacturing partner
- Target retail price
These are not omissions to be silently filled by implementation.

Each should be resolved through research, engineering analysis or explicit project decisions.

---

# PART R — REQUIREMENTS GOVERNANCE

## 22. Requirement Changes
Significant additions, removals or changes to mandatory requirements should be documented.

Where a requirement changes because of a major product or architectural decision, the decision should also be recorded in:

`docs/DECISIONS.md`

---

## 23. Traceability
Future implementation and testing should reference requirement identifiers where practical.

Examples:

`SEC-005`

`CONSENT-006`

`EVENT-008`

`FW-003`

This will allow product requirements, implementation, testing and risk controls to remain connected as the project grows.

---

## 24. Validation Status
Unless specifically documented otherwise, the requirements in version 0.1 represent the **proposed product baseline**, not evidence that the associated technology, customer demand, regulatory position or commercial assumptions have been validated.

---

## 25. Governing Principle
When requirements conflict with convenience, speed or feature expansion, the following order applies:

1. Safety
2. Consent
3. Privacy
4. Security
5. Reliability
6. Accessibility
7. User experience
8. Performance
9. Development convenience
Soul's Echo should only create remote physical connection when that connection remains deliberate, respectful and under the control of the person receiving it.
