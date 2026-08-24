# Soul's Echo — System Architecture
**Document:** System Architecture
**Project:** Soul's Echo
**Status:** Preliminary Architecture
**Phase:** Pre-development
**Version:** 0.1

---

## 1. Purpose
This document defines the preliminary logical architecture for the Soul's Echo platform.

It deliberately separates **architectural requirements** from **technology selections**.

At this stage, specific frameworks, cloud providers, microcontrollers, databases and other major technologies remain subject to evaluation.

The objective is to determine what the system must do before deciding exactly which technologies should implement it.

---

## 2. Architecture Principles
The Soul's Echo architecture must prioritise:

1. Safety
2. Consent
3. Privacy
4. Security
5. Reliability
6. Maintainability
7. Accessibility
8. Battery efficiency
9. Extensibility
10. Cost effectiveness
No technology should be selected solely because it enables the fastest prototype.

Prototype decisions that could influence production architecture must be documented.

Recipient authority takes precedence over sender authority. Current recipient
authorisation takes precedence over authorisation that existed when an event was
created. No remote interaction has a guaranteed right to eventual physical
delivery.

---

## 3. High-Level Architecture
The initial logical architecture consists of five principal layers:

```
┌──────────────────────────────┐
│      Soul's Echo Band        │
│                              │
│ Input • Haptic • Light       │
│ BLE • Battery • Firmware     │
└──────────────┬───────────────┘
               │
               │ Secure BLE
               │
┌──────────────▼───────────────┐
│       Companion App          │
│                              │
│ Device • Consent • Account   │
│ Permissions • Connectivity   │
└──────────────┬───────────────┘
               │
               │ Secure Internet
               │
┌──────────────▼───────────────┐
│      Soul's Echo Backend     │
│                              │
│ Identity • Devices           │
│ Relationships • Permissions  │
│ Event Routing • Security     │
└──────────────┬───────────────┘
               │
               │ Secure Internet
               │
┌──────────────▼───────────────┐
│  Recipient Companion App     │
│                              │
│ Authorisation • Delivery     │
│ Device Communication         │
└──────────────┬───────────────┘
               │
               │ Secure BLE
               │
┌──────────────▼───────────────┐
│     Recipient Band           │
│                              │
│ Validation • Haptic • Light  │
└──────────────────────────────┘
```
This is a logical model.

Implementation may optimise communication paths where doing so does not compromise safety, security, privacy or consent.

---

# PART A — BAND ARCHITECTURE

## 4. Band Responsibilities
The Band is responsible for:

- Local user input
- Haptic output
- Light output
- BLE communication
- Device identity
- Battery monitoring
- Power management
- Firmware execution
- Firmware-update support
- Local safety limits
- Validation of received commands
- Device reset behaviour
The Band must not operate merely as an unprotected remote actuator.

---

## 5. Preliminary Band Components
The Band is expected to require some combination of:

- Low-power microcontroller
- BLE radio
- Haptic actuator
- Light-emitting component
- User-input sensor
- Rechargeable battery
- Battery-management circuitry
- Charging circuitry
- Power regulation
- Non-volatile storage
- Security capability
- Debug/programming interface
- Appropriate antenna
- Supporting passive components
Exact components remain undecided.

---

## 6. Microcontroller Requirements
The selected MCU or SoC should be evaluated against:

- BLE capability
- Security features
- Power consumption
- Processing requirements
- Memory
- Firmware-update capability
- Cryptographic acceleration
- Secure boot support
- Development tooling
- Supply-chain availability
- Cost
- Physical size
- Regulatory ecosystem
- Long-term manufacturer support
No MCU has yet been approved.

---

## 7. Candidate MCU Research
Potential technology families may include devices from manufacturers such as:

- Nordic Semiconductor
- Espressif
- Silicon Labs
- Texas Instruments
- STMicroelectronics
- Other appropriate suppliers
Mentioning a supplier does not constitute a technology decision.

A documented comparison must precede final selection.

---

## 8. Local Safety Boundary
The Band firmware represents the final local control boundary.

Regardless of instructions received from the application or backend, firmware must enforce validated limits for:

- Haptic duration
- Haptic intensity
- Repetition
- Light behaviour
- Event validity
- Event expiry
- Device state
A remote service must not be capable of instructing the Band to bypass its local safety rules.

The Band must provide a phone-independent local means of inhibiting incoming
remote physical interactions. The physical input, indication and accessibility
implementation remain unresolved pending research and prototyping.

---

# PART B — BAND FIRMWARE

## 9. Firmware Modules
A preliminary firmware architecture may include:

```
Firmware
│
├── Device State
├── BLE Communication
├── Security
├── Input Handling
├── Haptic Control
├── Light Control
├── Power Management
├── Battery Monitoring
├── Event Validation
├── Persistent Configuration
├── Firmware Update
└── Diagnostics
```
Module boundaries may change during implementation.

---

## 10. Firmware State
Firmware should maintain only the local state required for safe device operation.

Sensitive long-term relationship state should not unnecessarily reside on the Band where authoritative backend or application state is more appropriate.

---

## 11. Firmware Updates
The firmware-update architecture must account for:

1. Update discovery.
2. Firmware authenticity.
3. Firmware integrity.
4. Transfer.
5. Installation.
6. Restart.
7. Validation.
8. Failure recovery.
An interrupted update must not automatically render the Band permanently unusable.

---

# PART C — BLUETOOTH ARCHITECTURE

## 12. BLE Role
Bluetooth Low Energy is the preliminary communication mechanism between the Band and Companion App.

The BLE layer is responsible for:

- Device discovery
- Pairing
- Authentication
- Connection establishment
- Command transport
- Status reporting
- Battery information
- Firmware transport where appropriate

---

## 13. BLE Trust
Bluetooth proximity alone does not establish trust.

A nearby device must not automatically gain access to Band functions.

The architecture requires explicit device authentication and authorised pairing.

---

## 14. BLE Data Model
The eventual BLE service design may include logical capabilities for:

- Device information
- Device state
- Battery state
- Interaction command
- Interaction initiation
- Security state
- Firmware update
Exact GATT services and characteristics remain undecided.

---

# PART D — COMPANION APP ARCHITECTURE

## 15. Application Responsibilities
The Companion App is expected to manage:

- Authentication
- Account state
- Local device registration
- BLE pairing
- Band communication
- Soul's Echo relationships
- Consent
- Permissions
- Device settings
- Battery display
- Security controls
- Firmware-update workflow
- Backend communication
- User safety controls

---

## 16. Application Logical Modules
A preliminary structure may include:

```
Companion App
│
├── Authentication
├── Account
├── Device Management
├── BLE
├── Connections
├── Consent
├── Permissions
├── Interactions
├── Firmware
├── Security
├── Notifications
├── Accessibility
└── Settings
```
This structure describes responsibilities rather than a mandated code organisation.

---

## 17. Mobile Technology Decision
The mobile framework remains undecided.

Potential approaches include:

- Native iOS and Android
- React Native
- Flutter
- Other appropriate cross-platform frameworks
The selection should consider:

- BLE support
- Background BLE behaviour
- Platform restrictions
- Security
- Accessibility
- Performance
- Developer availability
- Long-term maintenance
- Testing
- Cost
- Native integration
- Firmware-update requirements
A framework should not be selected solely because it enables a single shared codebase.

---

# PART E — BACKEND ARCHITECTURE

## 18. Backend Responsibilities
The backend is expected to provide:

- Authentication support
- User identity
- Device registration
- Device ownership
- Relationship management
- Consent state
- Permission state
- Event authorisation
- Event routing
- Revocation
- Security controls
- Firmware metadata
- Administrative security functions
- Appropriate audit capability

---

## 19. Modular Monolith First
Unless engineering evidence demonstrates otherwise, the initial backend should favour a **modular monolith**.

This provides:

- Lower operational complexity
- Easier development
- Easier testing
- Simpler deployment
- Clear transactional boundaries
- Lower early infrastructure cost
This does not mean the system can never use distributed services.

It means microservices must solve a demonstrated problem before being introduced.

---

## 20. Preliminary Backend Modules

```
Backend
│
├── Identity
├── Users
├── Devices
├── Ownership
├── Relationships
├── Consent
├── Permissions
├── Events
├── Firmware
├── Security
├── Audit
└── Administration
```
Module boundaries should remain explicit even if initially deployed as one application.

---

# PART F — DATA ARCHITECTURE

## 21. Preliminary Data Entities
Potential core entities include:

### User
Represents a Soul's Echo account.

### Device
Represents a registered physical Soul's Echo product.

### Device Ownership
Associates a device with its authorised owner.

### Relationship
Represents an authorised connection between users.

### Permission
Defines currently permitted interaction capabilities.

### Event
Represents the minimum information necessary to route or process a Soul's Echo interaction.

### Firmware Release
Represents an approved firmware version.

### Security Event
Represents selected events required for security or incident-response purposes.

Exact database schema remains undecided.

---

## 22. Relationship Model
Relationships should not simply be represented as a permanent boolean such as:

`connected = true`

The architecture must accommodate:

- Requested
- Accepted
- Rejected
- Active
- Paused
- Revoked
- Ended
The final state model requires detailed design.

Pause, block, disconnect and permission revocation are distinct operations.
Factory reset and local inhibit are device operations rather than interpersonal
relationship states. The detailed state machines remain required work before
architecture selection.

---

## 23. Permission Model
Permissions should be independently enforceable from relationship existence.

An active relationship does not necessarily imply permission for every possible interaction.

This separation supports future expansion without granting excessive access.

---

## 24. Data Minimisation
The database should not become a historical record of users' private relationships and behaviour merely because storing data is technically easy.

Every persistent personal-data field should have a defined purpose.

---

## 25. Database Technology
Database technology remains undecided.

The evaluation should consider:

- Relational integrity
- Transaction support
- Security
- Operational complexity
- Scaling requirements
- Backup
- Recovery
- Cost
- Data residency
- Developer tooling
A relational database is a strong preliminary candidate because relationships, ownership, permissions and consent require clear integrity constraints.

This remains an architectural recommendation rather than a final technology selection.

---

# PART G — EVENT ARCHITECTURE

## 26. Remote Interaction Flow
A preliminary interaction flow is:

```
User A
  │
  ▼
Band A
  │
  ▼
App A
  │
  │ Authenticated request
  ▼
Soul's Echo Backend
  │
  ├── Validate sender
  ├── Validate device
  ├── Validate relationship
  ├── Validate permission
  ├── Apply abuse controls
  └── Create bounded event
  │
  ▼
App B
  │
  ▼
Band B
  │
  ├── Validate event
  ├── Check local state
  ├── Apply local limits
  └── Produce physical response
```
The exact transport mechanism remains undecided.

The logical lifecycle distinguishes event creation, authorisation, routing,
delivery and physical output. Backend acceptance does not guarantee eventual
physical output. Until output occurs, the event remains subject to current
recipient permission, pause, block, relationship, expiry and local safety state.

---

## 27. Event Envelope
A future event format may require fields representing:

- Event identifier
- Event type
- Sender identity reference
- Recipient device reference
- Creation time
- Expiry time
- Sequence or anti-replay information
- Authorisation information
- Payload
- Integrity information
The exact structure must undergo security design before implementation.

---

## 28. Event Expiry
Remote physical events must not remain valid indefinitely.

The architecture must support event expiry.

The final permitted delivery window requires product testing.

An expired event must not produce physical output.

---

## 29. Duplicate Protection
The recipient system must be capable of recognising or safely handling duplicate events.

Network retry behaviour must not cause uncontrolled repeated physical output.

---

## 30. Offline Delivery
Offline-event behaviour remains unresolved.

Possible models include:

- Discard when recipient unavailable
- Short bounded delivery window
- Limited queue with expiry
The selected model must consider emotional meaning, privacy, reliability and the risk of unexpected delayed physical feedback.

No offline model may allow stored earlier authorisation to override a later
pause, block, permission reduction, relationship termination, expiry or local
inhibit. Blocking invalidates undelivered events from the blocked party.

---

# PART H — REAL-TIME COMMUNICATION

## 31. Delivery Technology
Potential backend-to-application delivery mechanisms may include:

- Platform push notifications
- Persistent connections
- WebSockets
- Managed real-time messaging
- Hybrid approaches
The decision must consider mobile operating-system restrictions, reliability, battery usage, security and cost.

---

## 32. Background Operation
The architecture must account for mobile operating systems suspending or terminating applications.

The system cannot assume the Companion App remains continuously active in the foreground.

---

# PART I — AUTHENTICATION AND IDENTITY

## 33. User Authentication
The final authentication architecture remains undecided.

Potential approaches include:

- Email-based authentication
- Passkeys
- Platform identity providers
- Other secure identity mechanisms
The chosen approach should minimise account-takeover risk while remaining practical for consumers.

---

## 34. Device Identity
User identity and device identity are separate concepts.

A legitimate user account must not automatically make an arbitrary physical device trustworthy.

Each production device should possess an appropriate device identity established during manufacturing or secure provisioning.

The logical lifecycle must support credential activation, revocation, compromise
response, loss, recovery where safe, transfer and retirement. The credential and
provisioning implementation remains undecided.

---

## 35. Ownership
Device ownership must be represented independently from physical BLE pairing.

Physical possession or Bluetooth connectivity alone must not establish permanent platform ownership.

Ownership transfer must invalidate previous ownership credentials and
device-specific authority. The previous owner's interpersonal relationships and
permissions must not automatically transfer with the Band.

---

# PART J — SECURITY ARCHITECTURE

## 36. Trust Boundaries
Primary trust boundaries include:

```
Physical User
     │
     ▼
Band
     │
──── BLE Boundary ────
     │
Companion App
     │
──── Internet Boundary ────
     │
Backend
     │
──── Service/Data Boundary ────
     │
Database / Infrastructure
```
Every boundary requires appropriate authentication, validation and authorisation.

---

## 37. Defence in Depth
No single control should be assumed to provide complete security.

For example, a remote event may be protected through:

1. User authentication.
2. Server authorisation.
3. Relationship validation.
4. Permission validation.
5. Event integrity.
6. Device authentication.
7. Firmware validation.
8. Local safety bounds.
Failure of one control should not automatically create unrestricted remote access.

---

## 38. Cryptography
Specific cryptographic algorithms and protocols must be selected through security design.

Custom cryptographic algorithms MUST NOT be invented for Soul's Echo.

Use established, reviewed cryptographic standards and platform capabilities.

---

## 39. Secure Provisioning
Production architecture must define how devices receive:

- Unique identity
- Credentials
- Firmware
- Manufacturing information
- Security configuration
Provisioning must be considered before manufacturing architecture is finalised.

---

# PART K — PRIVACY ARCHITECTURE

## 40. Privacy by Architecture
Privacy controls should be structural rather than dependent solely on policy documents.

Examples include:

- Not collecting unnecessary location data
- Not storing unnecessary interaction histories
- Separating operational data from analytics
- Limiting employee access
- Applying retention controls
- Encrypting sensitive information
- Minimising third-party data exposure

---

## 41. Analytics
Analytics technology must not automatically be embedded throughout the product.

Any analytics proposal must identify:

- Purpose
- Data collected
- Retention
- User impact
- Third-party access
- Privacy implications
Privacy-invasive analytics should not be introduced merely because a software development kit makes them convenient.

---

# PART L — INFRASTRUCTURE

## 42. Cloud Provider
No cloud provider has been selected.

Potential providers or managed platforms must be compared against:

- Security
- Australian availability
- Data residency
- Reliability
- Cost
- Developer experience
- Scaling
- Monitoring
- Backup
- Compliance capabilities
- Vendor lock-in

---

## 43. Environments
The software architecture should eventually support separated environments such as:

```
Development
Testing
Staging
Production
```
Production credentials and data must not be routinely used in development.

---

## 44. Configuration
Environment-specific configuration should be externalised appropriately.

Secrets must not be committed to Git.

---

# PART M — OBSERVABILITY

## 45. Operational Monitoring
Production services will require appropriate monitoring for:

- Availability
- Error rates
- Performance
- Security events
- Event-delivery failures
- Firmware-update failures
- Infrastructure health
Monitoring must respect privacy requirements.

---

## 46. Logging
Logs should contain sufficient technical information for diagnosis without unnecessarily recording intimate user behaviour.

Sensitive values must not be casually written to logs.

---

# PART N — FAILURE ARCHITECTURE

## 47. Required Failure States
The architecture must explicitly handle:

- Internet loss
- BLE loss
- Backend outage
- Database outage
- Expired authentication
- Revoked permission
- Recipient offline
- Band offline
- Low battery
- Duplicate event
- Delayed event
- Invalid event
- Firmware-update interruption
- Mobile application termination
- Push-delivery failure
- Out-of-order event
- Lost or duplicated acknowledgement
- Phone loss, compromise or replacement
- Band loss, compromise or transfer
- Revocation, blocking or permission reduction during event transit
- Partial backend failure
- Disaster recovery restoring older authorisation data

---

## 48. Default Failure Principle
Where the system cannot establish that a remote physical interaction is currently authorised and valid, the interaction should fail closed.

In practical terms:

**uncertainty must not become permission.**

Where current authorisation and event validity cannot safely be established, the
Band must not produce remote physical output. Restoration, retry and recovery
processes must not revive obsolete consent or permission state.

---

# PART O — FUTURE ECOSYSTEM

## 49. Device Abstraction
Backend and application models should avoid unnecessary assumptions such as:

`device = band`

Prefer concepts capable of representing:

```
Device
├── Band
├── Ring
├── Pendant
└── Future Device
```
This does not mean future devices should be implemented now.

It means the fundamental data model should avoid obvious dead ends.

Avoiding an obvious dead end is not an MVP requirement to build generic device
capability systems. A future-product abstraction that adds present complexity
requires a concrete Band requirement or a later explicit decision.

---

## 50. Capability Model
Future devices may have different capabilities.

The architecture may eventually represent capabilities such as:

- Haptic output
- Light output
- Touch input
- Other approved output types
Permissions should eventually relate to capabilities rather than assuming every device behaves identically.

---

# PART P — TECHNOLOGY DECISION PROCESS

## 51. Major Technology Decisions
The following must receive explicit evaluation before final selection:

### Hardware

- MCU/SoC
- BLE architecture
- Battery
- Charging
- Haptic actuator
- Input sensor
- Security hardware

### Firmware

- SDK/framework
- RTOS or event-loop approach
- Update architecture
- Bootloader
- Security model

### Mobile

- Native versus cross-platform
- BLE library
- State management
- Secure storage
- Background-delivery architecture

### Backend

- Programming language
- Framework
- Database
- Hosting
- Authentication
- Real-time delivery

### Infrastructure

- Cloud provider
- CI/CD
- Secret management
- Monitoring
- Error reporting

---

## 52. Technology Evaluation Criteria
Each significant technology should be evaluated against:

1. Security
2. Reliability
3. Product requirements
4. Hardware compatibility
5. Battery implications
6. Developer capability
7. Maintainability
8. Ecosystem maturity
9. Vendor support
10. Cost
11. Supply-chain risk
12. Regulatory implications
13. Accessibility implications
14. Scalability
15. Lock-in

---

## 53. Decision Records
Approved architectural decisions must be recorded in:

`docs/DECISIONS.md`

A technology appearing in prototype code does not automatically make it an approved production technology.

---

# PART Q — PROTOTYPE ARCHITECTURE

## 54. Prototype Versus Production
Prototype architecture may intentionally differ from production architecture.

For example, a prototype may use:

- Development boards
- Temporary enclosures
- Simplified backend hosting
- Developer test applications
- Temporary provisioning
Such choices must be labelled clearly.

Prototype shortcuts must not silently become production assumptions.

---

## 55. First Technical Prototype Goal
The first technical prototype should prove the smallest meaningful end-to-end interaction.

Target:

```
Input Device A
      │
      ▼
Phone A
      │
      ▼
Secure Test Service
      │
      ▼
Phone B
      │
      ▼
Output Device B
      │
      ▼
Bounded Haptic Response
```
The purpose is to validate architecture and experience, not create a commercially finished product.

---

# PART R — OPEN ARCHITECTURAL DECISIONS

## 56. Unresolved Decisions
The following remain open:

- MCU
- BLE SoC
- Secure element
- Firmware framework
- RTOS
- Bootloader
- Firmware-update mechanism
- Mobile framework
- Backend language
- Backend framework
- Database
- Authentication platform
- Cloud provider
- Real-time delivery technology
- Push-notification strategy
- Event-expiry policy
- Offline-delivery policy
- Device-provisioning architecture
- Key-management architecture
- Analytics approach
- Monitoring platform
- CI/CD platform
Codex must not silently resolve these as permanent production decisions.

---

# PART S — NEXT ARCHITECTURE WORK

## 57. Required Technical Investigations
Before production stack selection, conduct structured comparisons for:

1. Band MCU/SoC.
2. Haptic technologies.
3. Battery and charging approaches.
4. Mobile development approaches.
5. BLE implementation strategies.
6. Backend stack.
7. Real-time event delivery.
8. Device identity and provisioning.
9. Firmware-update architecture.
10. Cloud infrastructure.
Results should be documented under `/research` and major decisions recorded in `DECISIONS.md`.

---

## 58. Architecture Validation
The architecture should eventually be validated through:

- Threat modelling
- Privacy review
- BLE prototype
- End-to-end prototype
- Failure testing
- Latency measurement
- Battery measurement
- Security testing
- User testing
- Cost modelling

---

## 59. Architecture Principle
Soul's Echo should not become technologically complicated simply because complexity is possible.

The preferred architecture is the **simplest architecture capable of delivering the required experience safely, securely, privately and reliably**.

---

## 60. Current Architecture Status
This document establishes a **logical architecture**, not a final implementation architecture.

Technology choices remain intentionally open until sufficient evidence exists to make them responsibly.

That distinction must be preserved throughout early development.
