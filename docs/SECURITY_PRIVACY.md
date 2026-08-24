# Soul's Echo — Security, Privacy and Consent Framework
**Document:** Security, Privacy and Consent Framework
**Project:** Soul's Echo
**Status:** Preliminary Security and Privacy Baseline
**Version:** 0.1
**Classification:** Internal Project Documentation

---

## 1. Purpose
Soul's Echo combines connected physical devices, mobile applications, internet services and private interpersonal relationships.

This creates security and privacy responsibilities beyond those of a conventional consumer application.

A compromise could potentially expose:

- User accounts
- Private relationships
- Device information
- Interaction information
- Physical-device functionality
Security, privacy and consent must therefore be designed into the architecture from the beginning.

They must not be treated as features to add immediately before commercial launch.

---

# PART A — SECURITY PRINCIPLES

## 2. Security Objectives
The Soul's Echo security architecture should protect:

### Confidentiality
Information should only be accessible to appropriately authorised entities.

### Integrity
Commands, firmware, permissions and important data should not be modified without detection or authorisation.

### Availability
Legitimate users should have reasonable access to the service while recognising that safety takes priority over availability.

### Authenticity
The system should be capable of determining whether users, devices, firmware and commands are legitimate.

### Accountability
Important security-sensitive actions should be sufficiently traceable for incident investigation without creating unnecessary surveillance.

---

## 3. Security Priority
Where security conflicts with convenience, the project must explicitly assess the risk rather than automatically choosing convenience.

Particular caution applies to:

- Authentication
- Pairing
- Account recovery
- Remote interaction
- Device ownership
- Firmware updates
- Permission changes
- Revocation

Recipient authority takes precedence over sender authority, and current recipient
authorisation takes precedence over earlier authorisation. No remote interaction
has a guaranteed right to eventual physical delivery.

---

## 4. Fail Closed
When the system cannot establish that a remote physical interaction is currently authorised, it should fail closed.

**Uncertainty must not become permission.**

---

# PART B — THREAT MODEL

## 5. Threat-Modelling Requirement
A formal threat model must be developed before commercial deployment.

Threat modelling should be repeated after significant architectural changes.

---

## 6. Potential Adversaries
Threat analysis should consider:

- Opportunistic attackers
- Account thieves
- Malicious connected users
- Former partners or former authorised users
- Nearby Bluetooth attackers
- Internet-based attackers
- Malware on a mobile device
- Compromised third-party services
- Supply-chain attackers
- Malicious insiders
- Attackers with temporary physical access to a Band

---

## 7. Protected Assets
Important assets include:

- User accounts
- Authentication credentials
- Device credentials
- Device ownership
- Relationship state
- Permission state
- Firmware
- Firmware-signing infrastructure
- Remote interaction commands
- Personal information
- Security logs
- Production secrets
- Manufacturing credentials

---

## 8. High-Risk Scenarios
Security design must explicitly consider:

- Account takeover
- Unauthorised pairing
- Device impersonation
- User impersonation
- Replay attacks
- Command tampering
- Excessive remote interaction
- Revoked users retaining access
- Stolen Bands
- Resold Bands
- Malicious firmware
- Firmware downgrade
- Backend compromise
- Credential leakage
- Database compromise
- Mobile-device compromise
- Supply-chain compromise

---

# PART C — USER AUTHENTICATION

## 9. Authentication
Users must authenticate before accessing protected Soul's Echo account functionality.

The final authentication method remains undecided.

---

## 10. Authentication Requirements
The selected system should support:

- Secure account creation
- Secure sign-in
- Session management
- Session revocation
- Account recovery
- Appropriate protection against automated abuse

---

## 11. Passwords
If passwords are used:

- Plain-text passwords must never be stored.
- Modern password-hashing techniques must be used.
- Password-reset processes must be secure.
- Passwords must not be written to application logs.
Alternative authentication approaches should be evaluated before final selection.

---

## 12. Multi-Factor Authentication
Appropriate multi-factor or phishing-resistant authentication options should be evaluated before commercial release.

---

## 13. Account Recovery
Account recovery is a high-risk process.

Recovery mechanisms must not provide an easier route for account takeover than ordinary authentication.

---

# PART D — DEVICE IDENTITY

## 14. User Identity Is Not Device Identity
An authenticated user and an authenticated physical device are separate security concepts.

A valid user account must not automatically make any nearby BLE device trustworthy.

---

## 15. Unique Device Identity
Production Bands must have an appropriate unique identity.

The exact provisioning architecture remains undecided.

---

## 16. Device Credentials
Where device credentials are required, they should:

- Be unique where appropriate
- Be generated securely
- Be protected from unauthorised extraction
- Support revocation where feasible
- Avoid unnecessary sharing between devices
A compromise of one Band should not automatically compromise every Band.

---

# PART E — DEVICE OWNERSHIP

## 17. Ownership
Soul's Echo must distinguish:

- Physical possession
- BLE pairing
- Registered ownership
- Relationship permission
These concepts must not be treated as equivalent.

---

## 18. Stolen Device
A process must eventually exist for handling lost or stolen Bands.

Potential requirements include:

- Removing the device from an account
- Invalidating relevant credentials
- Preventing unauthorised reassignment
- Secure recovery or reset
The final process requires design.

Equivalent workflows are required for a lost, stolen, replaced or compromised
phone. Recovery must not silently restore revoked relationship, device or
permission authority.

---

## 19. Ownership Transfer
Legitimate resale, gifting or transfer must not preserve the previous owner's access.

A secure ownership-transfer process must be established before commercial launch.

Transfer must invalidate previous ownership credentials and device-specific
authority. The previous owner's relationships and permissions must not transfer
to the new owner.

---

# PART F — PAIRING

## 20. Pairing
Band-to-phone pairing must require deliberate user action.

Proximity alone must not establish trust.

---

## 21. Pairing Attack Resistance
The pairing process should consider protection against:

- Eavesdropping
- Impersonation
- Man-in-the-middle attacks
- Unauthorised nearby devices
- Pairing-state confusion
Exact controls depend on the selected BLE architecture.

---

## 22. Factory Reset
Factory reset must place the device into a defined security state.

Reset behaviour must not accidentally preserve previous remote authorisation.

Factory reset is distinct from pause, block, disconnect, permission revocation
and the Band's ordinary local incoming-interaction inhibit.

---

# PART G — RELATIONSHIPS AND CONSENT

## 23. Mutual Connection
A Soul's Echo interpersonal connection requires deliberate participation by both users.

One user cannot unilaterally establish remote access to another person's Band.

---

## 24. Consent Is Not Permanent
Previous consent must not be interpreted as permanent consent.

The system must support:

- Pause
- Permission changes
- Revocation
- Disconnection

An interaction remains subject to current recipient authority until physical
output occurs. Earlier consent does not create a right to eventual delivery.

---

## 25. Independent Revocation
Either participant must be capable of ending or restricting the connection without requiring approval from the other participant.

Pause, block, disconnect and permission revocation are distinct actions. Blocking
prevents new interactions from the blocked party and invalidates that party's
undelivered interactions.

---

## 26. Consent Interface
Consent must be understandable.

The interface should explain:

- Who is requesting access
- What they may do
- What the recipient is allowing
- How permissions can be changed
- How access can be paused
- How access can be revoked

---

## 27. Gifting
Giving someone a Soul's Echo device does not grant the giver digital access to that device.

The recipient must independently establish any relationship.

---

# PART H — PERMISSIONS

## 28. Permission Model
Relationship existence and interaction permission must be separate concepts.

A user may remain connected while restricting particular interactions.

---

## 29. Least Privilege
Permissions should grant only the capabilities required.

Future device capabilities must not automatically become available to existing relationships without appropriate consideration.

---

## 30. Server Enforcement
Permissions must be enforced by trusted backend logic where applicable.

Hiding a button in the Companion App is not sufficient authorisation.

---

## 31. Device Enforcement
The Band must independently enforce relevant local safety limits.

Backend permission does not authorise unlimited physical output.

The Band must enforce a phone-independent local incoming-interaction inhibit.
Remote systems must not bypass it. Its physical implementation remains unresolved
pending hardware, usability and accessibility research.

---

# PART I — REMOTE PHYSICAL INTERACTIONS

## 32. Remote Interaction Risk
Remote physical interaction creates a unique abuse surface.

The system must assume that even a legitimately authorised user could behave in an unwanted manner.

---

## 33. Bounded Events
Remote physical events must have limits on relevant characteristics such as:

- Duration
- Intensity
- Frequency
- Repetition
Final limits require physical testing.

---

## 34. Rate Limiting
The architecture must provide mechanisms to prevent excessive remote interaction.

Rate limits may exist at multiple levels:

- Backend
- Application
- Firmware

---

## 35. Local Override
A remote user must never be capable of disabling the recipient's local safety controls.

---

## 36. Pause
Recipients must have a simple mechanism for temporarily disabling incoming interactions.

The Band-local inhibit must remain usable without immediate phone access.

---

## 37. Block and Disconnect
The final user experience should provide clear mechanisms for permanently preventing unwanted interaction.

Block and disconnect must remain independently expressible. Protective actions
should not unnecessarily disclose whether a recipient has paused, blocked,
changed permission, lost connectivity or applied a local inhibit.

---

# PART J — EVENT SECURITY

## 38. Event Authentication
The recipient system must be capable of determining whether a remote event is legitimate.

Event creation, authorisation, routing, delivery and physical output are distinct
stages. Backend acceptance is not proof that physical delivery remains permitted.

---

## 39. Replay Protection
Previously valid events must not be reusable indefinitely.

The final architecture may use mechanisms such as:

- Nonces
- Sequence information
- Expiry
- Event identifiers
- Cryptographic integrity controls
Exact implementation remains subject to security design.

---

## 40. Event Expiry
Every remotely delivered physical-interaction event should have an appropriate validity window.

Expired events must not unexpectedly trigger a device.

Exact validity windows remain unresolved until later product and technical
research.

---

## 41. Duplicate Events
Duplicate network delivery must not cause uncontrolled repeated physical output.

---

## 42. Tampering
Modification of security-relevant event information should be detectable or prevented.

---

# PART K — FIRMWARE SECURITY

## 43. Firmware Trust
Production Bands must not blindly execute arbitrary firmware.

---

## 44. Firmware Integrity
Firmware authenticity or integrity must be verified before installation.

---

## 45. Secure Boot
Secure-boot capability should be evaluated during MCU selection.

Where technically and commercially appropriate, the production Band should verify approved firmware during startup.

---

## 46. Firmware Downgrade
The update architecture should consider downgrade attacks.

A vulnerable older firmware version should not necessarily remain installable indefinitely.

---

## 47. Update Failure
Interrupted updates must fail predictably.

Recovery must be possible where reasonably practical.

---

## 48. Signing Keys
Firmware-signing keys, if used, are high-value production secrets.

They must not:

- Be committed to Git
- Be stored casually on developer computers
- Be embedded in public documentation
A formal key-management approach must be established before production.

---

# PART L — MOBILE SECURITY

## 49. Secure Storage
Sensitive mobile credentials should use appropriate platform-provided secure-storage mechanisms.

---

## 50. Logging
Sensitive authentication information, secrets and unnecessary personal information must not be written to application logs.

---

## 51. Local Application Data
The Companion App should retain only the local data necessary for its operation.

Sensitive cached information requires appropriate protection.

---

## 52. Compromised Phone
The threat model must consider a compromised or stolen phone.

A phone's possession alone should not necessarily provide unlimited permanent access to another person's Soul's Echo relationship.

The logical security model must support phone-session revocation, replacement and
recovery without silently restoring obsolete authority.

---

# PART M — BACKEND SECURITY

## 53. API Authentication
Protected backend endpoints must authenticate requests.

---

## 54. API Authorisation
Authentication alone is insufficient.

Every protected operation must verify whether the authenticated entity is authorised to perform that specific operation.

---

## 55. Input Validation
Untrusted data must be validated at appropriate trust boundaries.

---

## 56. Rate Controls
Appropriate abuse controls should protect:

- Authentication
- Account recovery
- Connection requests
- Permission changes
- Remote events
- Device registration
- Firmware operations

---

## 57. Database Access
Database credentials must follow least-privilege principles.

Public clients must not receive unrestricted database credentials.

---

## 58. Administrative Access
Administrative functionality must be strongly protected.

Administrative interfaces should not expose private user information unnecessarily.

---

# PART N — INFRASTRUCTURE SECURITY

## 59. Environment Separation
Production systems should be appropriately separated from development and testing.

---

## 60. Secrets
Production secrets must be stored using appropriate secret-management mechanisms.

Secrets must not be committed to GitHub.

---

## 61. Dependency Security
Dependencies must be monitored for significant vulnerabilities.

Unmaintained dependencies should be avoided where practical.

---

## 62. Backups
Required production data must have appropriate backup and recovery arrangements.

Backups containing personal information require equivalent security consideration.

---

# PART O — PRIVACY

## 63. Privacy Objective
Soul's Echo should provide its core experience without constructing an unnecessary surveillance record of intimate relationships.

---

## 64. Data Minimisation
Collect only information required for:

- Product functionality
- Security
- Support
- Compliance
- Legitimate business operations
Convenience alone does not justify collecting sensitive information.

---

## 65. Potential Data Categories
Potentially required data may include:

- Account identifier
- Contact information
- Device identifiers
- Device ownership
- Relationship state
- Permission state
- Firmware version
- Security information
- Limited operational information
Every category requires further data-mapping analysis.

---

## 66. Interaction History
Persistent detailed interaction histories are not an assumed MVP feature.

If proposed later, the project must evaluate:

- Customer value
- Privacy risk
- Abuse potential
- Retention
- Visibility
- Deletion
- Legal implications

Operational metadata, logs, delivery acknowledgements and analytics can also
reveal relationship or behavioural patterns and must not be treated as harmless
merely because they are not displayed as user-facing history.

---

## 67. Location
Continuous location tracking is not required for the core product.

Location data should not be introduced without a specific documented purpose and privacy assessment.

---

## 68. Contacts
The Companion App should not automatically upload a user's complete address book merely to help locate another Soul's Echo user unless a later design establishes a justified, privacy-preserving approach.

---

## 69. Advertising
The MVP will not rely on behavioural advertising.

Personal relationship information must not be collected for advertising profiling.

---

# PART P — DATA RETENTION

## 70. Retention Principle
Data should not be retained indefinitely by default.

Possible future analytics, product development or convenience is not by itself a
sufficient reason to retain sensitive interaction metadata.

---

## 71. Retention Schedule
Before commercial launch, each significant data category must have a documented retention period or retention rule.

---

## 72. Security Retention
Some security records may require temporary retention for:

- Abuse detection
- Incident response
- Fraud prevention
- Legal obligations
Such retention must remain proportionate.

---

# PART Q — USER RIGHTS AND CONTROL

## 73. Transparency
Users should be able to understand:

- What information Soul's Echo collects
- Why it is collected
- How it is used
- Who receives it
- How long it is retained

---

## 74. Account Deletion
An appropriate account-deletion process must exist before commercial launch.

---

## 75. Relationship Deletion
Ending a relationship should remove or invalidate the associated active permissions.

The design must also address undelivered interactions and retained relationship
metadata without exposing unnecessary protective-status information to the other
party.

---

## 76. Device Removal
Users should be capable of removing devices from their account through an appropriately secure process.

---

# PART R — THIRD PARTIES

## 77. Third-Party Assessment
External providers must be evaluated before receiving sensitive Soul's Echo data.

Consider:

- Data collected
- Storage location
- Security
- Retention
- Subprocessors
- Contract terms
- Privacy practices
- Breach history
- Vendor lock-in

---

## 78. Software Development Kits
Third-party mobile SDKs should not be added casually.

SDKs may collect information beyond the functionality they provide.

---

# PART S — AUSTRALIAN PRIVACY CONTEXT

## 79. Australian Foundation
The project begins from an Australian commercial context.

Applicable privacy obligations must be professionally assessed before launch.

Relevant considerations may include the **Privacy Act 1988 (Cth)**, the **Australian Privacy Principles**, the **Notifiable Data Breaches scheme**, consumer-law obligations and other requirements applicable to the final business structure and product.

This document does not constitute legal advice.

---

## 80. Privacy Act Reform
Australian privacy requirements may change during product development.

Compliance must therefore be reassessed closer to commercial deployment rather than relying permanently on early-stage research.

---

# PART T — SECURITY INCIDENTS

## 81. Incident Response
Before commercial launch, Soul's Echo requires a documented security-incident response process.

---

## 82. Incident Categories
Potential incidents include:

- Account compromise
- Credential exposure
- Device compromise
- Backend breach
- Personal-data breach
- Malicious firmware
- Unauthorised remote interaction
- Infrastructure compromise
- Third-party compromise

---

## 83. Response Capability
The organisation should eventually be capable of:

1. Detecting significant incidents.
2. Containing them.
3. Investigating them.
4. Revoking affected credentials.
5. Protecting users.
6. Restoring services safely.
7. Meeting applicable notification obligations.
8. Correcting underlying vulnerabilities.

---

# PART U — VULNERABILITY MANAGEMENT

## 84. Vulnerability Process
Before commercial launch, establish a process for receiving and assessing vulnerability reports.

---

## 85. Security Updates
The architecture must support correcting significant security vulnerabilities after devices have been sold.

This is a major reason secure firmware updates are an MVP requirement.

---

## 86. Supported Lifetime
A security-support period for commercial hardware must eventually be defined.

Customers should not unknowingly depend on permanently unsupported connected devices.

---

# PART V — DEVELOPMENT SECURITY

## 87. Repository Security
The repository must not contain:

- Production passwords
- API secrets
- Private cryptographic keys
- Firmware-signing private keys
- Production database credentials
- Personal customer information

---

## 88. Environment Files
Real `.env` files containing secrets should be excluded from version control.

Use `.env.example` or equivalent files containing placeholders.

---

## 89. Code Review
High-risk changes should receive additional review.

Examples include:

- Authentication
- Authorisation
- Consent
- Pairing
- Cryptography
- Firmware updates
- Device ownership
- Remote-event processing

---

## 90. Automated Testing
Security-critical controls should receive automated testing where appropriate.

Tests should include attempts to perform unauthorised actions, not merely successful operations.

---

# PART W — ABUSE AND INTERPERSONAL SAFETY

## 91. Abuse Is a Product Security Concern
Soul's Echo must consider misuse by people who possess legitimate accounts.

Not every threat comes from an anonymous hacker.

---

## 92. Former Relationships
The system must account for relationships ending.

Revocation must work even if the other person does not agree.

---

## 93. Harassment
Rate limits, pause, blocking and revocation should help prevent Soul's Echo interactions from becoming a harassment mechanism.

Rate limiting alone is insufficient. The recipient must have independent local
inhibit, block and revocation controls, and undelivered events must respect those
controls.

---

## 94. Coercion
Future user research should consider coercive-control scenarios.

Security design should not assume every authorised relationship is permanently safe or healthy.

---

## 95. Privacy Leakage
The application should avoid unnecessarily revealing:

- When someone is actively using their Band
- Detailed interaction habits
- Exact location
- Behavioural patterns
- Information about other relationships
unless a justified and consented feature specifically requires it.

Delivery feedback must not unnecessarily reveal whether a recipient has paused,
blocked, changed permissions, applied a local inhibit or lost connectivity.

---

# PART X — PRE-LAUNCH SECURITY GATE

## 96. Required Security Work
Before commercial release, complete appropriate:

- Threat modelling
- Architecture review
- Authentication review
- Authorisation review
- BLE security review
- Firmware review
- API security testing
- Mobile security testing
- Infrastructure review
- Privacy assessment
- Data mapping
- Retention definition
- Incident-response planning
- Vulnerability-management planning

---

## 97. Independent Review
Appropriate independent security assessment should be strongly considered before commercial launch.

A development team should not assume that testing its own implementation is sufficient for a connected physical product.

---

# PART Y — OPEN SECURITY DECISIONS

## 98. Decisions Still Required
The following remain unresolved:

- User authentication mechanism
- Multi-factor authentication model
- Device credential architecture
- Secure-element requirement
- Manufacturing provisioning
- BLE pairing method
- Cryptographic protocols
- Key management
- Firmware-signing architecture
- Firmware anti-rollback policy
- Event authentication
- Event expiry
- Rate limits
- Account recovery
- Security-log retention
- Data retention periods
- Security-support lifetime
- Vulnerability disclosure process
- Incident-response ownership
- Detailed pause, block, disconnect and permission state models
- Lost, stolen, compromised and replacement-device workflows
- Delivery-feedback semantics
- Shared-phone and shared-Band authority model
These require deliberate decisions rather than automatic framework defaults.

---

# PART Z — SECURITY AND PRIVACY PRINCIPLE

## 99. Final Principle
Soul's Echo exists to strengthen human connection.

The technology must therefore respect the autonomy of the people using it.

The system should never treat:

**connection as ownership,**

**previous consent as permanent consent,**

**proximity as authorisation,**

**data collection as inherently valuable,**

or

**technical capability as justification for access.**

A secure Soul's Echo experience is one in which the person receiving a physical interaction remains informed, protected and in control.
