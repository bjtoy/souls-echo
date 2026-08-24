# Soul's Echo — Codex Instructions
**Project:** Soul's Echo
**Repository:** `bjtoy/souls-echo`
**Purpose:** Operating instructions for Codex and repository-level implementation work

---

## 1. Read Before Making Changes
Before modifying this repository, read:

1. `PROJECT_HANDOFF.md`
2. `README.md`
3. All relevant files under `/docs`
4. Existing source code
5. Existing tests
6. Existing configuration files
7. Existing dependency manifests
8. Existing issues or TODO documentation where available
Do not assume that an undocumented requirement is approved.

Do not begin speculative implementation before understanding the current documented project state.

---

## 2. Project Priority Order
When making technical decisions, use this priority order:

1. User safety
2. Consent
3. Privacy
4. Security
5. Reliability
6. Maintainability
7. Accessibility
8. Product usability
9. Performance
10. Development convenience
Development convenience must never override consent, privacy, security or safety requirements.

---

## 3. Product Scope
The first major product is the **Soul's Echo Band**.

The Band is supported by the **Soul's Echo Companion App** and backend services.

Future products may include:

- Ring
- Pendant
- Dock
- Wellness products
- Accessories
- Other compatible devices
Do not design the architecture in a way that unnecessarily prevents future expansion.

Do not implement future product functionality unless explicitly approved.

Avoid obvious future dead ends where practical, but do not create generic device
or capability abstractions solely for unvalidated future products. The Band is
the sole physical MVP focus.

---

## 4. MVP Discipline
Keep the initial product focused.

Every proposed feature should be classified as one of:

- MVP mandatory
- MVP desirable
- Post-MVP
- Future research
- Rejected
Do not silently expand scope.

If a requested change introduces substantial additional complexity, explain the impact before implementation.

---

## 5. Coding Standards
Code should be:

- Clear
- Maintainable
- Secure
- Modular
- Testable
- Appropriately documented
- Consistent with the existing codebase
Prefer straightforward code over clever code.

Avoid unnecessary abstraction.

Avoid premature optimisation.

Avoid adding dependencies when the same result can reasonably be achieved with the existing stack.

---

## 6. File Changes
When modifying an existing file:

- Inspect the complete file first.
- Preserve unrelated working behaviour.
- Do not remove functionality without explaining why.
- Do not leave placeholder code unless specifically requested.
- Do not silently rename public interfaces.
- Keep changes focused on the task.
When creating a new file:

- Place it in the most appropriate existing directory.
- Use a clear and descriptive name.
- Follow the project's existing structure.
- Document why the file exists when that purpose is not obvious.

---

## 7. Full-File Preference
When presenting replacement code for manual use, provide complete files rather than partial snippets unless explicitly requested otherwise.

If only a small patch is appropriate inside Codex, the patch may be applied directly, but the resulting file must remain complete and valid.

---

## 8. Security Requirements
Treat security as a primary product requirement.

At minimum, consider:

- Authentication
- Authorisation
- Device identity
- Secure pairing
- Session security
- Encryption in transit
- Credential storage
- Secret management
- Replay protection
- Input validation
- API abuse prevention
- Rate limiting where appropriate
- Firmware integrity
- Secure firmware delivery
- Revocation
- Auditability of significant security events
- Dependency vulnerabilities
Do not hard-code secrets.

Do not commit credentials, tokens, keys or private certificates.

Use environment variables or secure secret-management mechanisms where appropriate.

---

## 9. Consent Requirements
Remote interaction between users and devices must be explicitly authorised.

The system must support:

- Acceptance
- Rejection
- Permission control
- Temporary suspension
- Disconnection
- Revocation
Previous consent must not be treated as permanent consent.

A user must retain local control over their own device.

Recipient authority and current recipient authorisation take precedence over the
sender and earlier authorisation. Pause, block, disconnect, permission revocation,
local inhibit and factory reset are distinct concepts.

Blocking invalidates undelivered interactions from the blocked party. Applicable
revocation or permission reduction invalidates interactions that have not produced
physical output.

Remote commands must never permanently override local safety controls.

---

## 10. Privacy Requirements
Collect the minimum data necessary for the service to function.

Avoid unnecessary:

- Location collection
- Contact harvesting
- Background tracking
- Behavioural profiling
- Sensitive analytics
- Long-term event retention
If personal or sensitive information is proposed for storage, document:

- Why it is required
- Where it is stored
- How long it is retained
- Who can access it
- How it is protected
- How it can be deleted
Prefer privacy-preserving architecture.

---

## 11. Physical Device Safety
The Band is a physical connected device.

Software and firmware must account for:

- Unexpected connectivity loss
- Duplicate messages
- Delayed messages
- Replay attempts
- Battery depletion
- Failed updates
- Partial updates
- Device reset
- Pairing failure
- Backend outage
- Mobile application outage
The device must fail safely.

A network or software fault must not create uncontrolled physical behaviour.

The Band must provide a phone-independent local means of inhibiting incoming
remote physical interactions. Do not assume its physical implementation until
hardware, usability and accessibility research approves an approach.

Where current authorisation cannot safely be established, remote physical output
must fail closed.

---

## 12. Haptic and Light Events
Remote haptic or light interactions should be:

- Intentional
- Bounded
- Rate limited where necessary
- Revocable
- Non-persistent by default
Do not create an architecture that permits an authorised remote user to continuously trigger another device without appropriate controls.

No remote event has a guaranteed right to eventual delivery. Until physical
output, an event remains subject to current recipient pause, block, permission,
relationship, expiry and local safety state.

---

## 13. Firmware
Firmware architecture should support:

- Secure boot where feasible
- Signed or integrity-verified firmware
- Safe update procedures
- Update failure recovery
- Version reporting
- Device reset
- Secure BLE communication
- Appropriate local input handling
- Battery reporting
Do not assume firmware updates will always complete successfully.

---

## 14. Bluetooth Low Energy
BLE implementation must consider:

- Secure pairing
- Bonding strategy
- Device identity
- Reconnection behaviour
- Lost-device scenarios
- Multiple nearby devices
- Replay risks
- Spoofing risks
- Permission revocation
- Factory reset behaviour
Do not rely on device names as secure identifiers.

---

## 15. Backend Architecture
Backend services should be designed to support:

- User authentication
- Device registration
- Device ownership
- Relationship management
- Consent
- Permission state
- Event routing
- Revocation
- Device status
- Firmware metadata
- Future multi-device support
Keep services as simple as practical during the MVP.

Avoid unnecessary microservices.

A modular monolith may be preferable during early development unless there is a clear reason otherwise.

This is a reversible preference, not approval of a backend framework, database,
cloud provider or production deployment architecture.

---

## 16. API Design
APIs should:

- Use clear resource naming
- Validate input
- Enforce authorisation
- Return appropriate error codes
- Avoid exposing unnecessary internal information
- Be versionable where appropriate
- Use idempotency for operations where duplicate execution could cause problems
Sensitive operations should be auditable.

---

## 17. Mobile Application
The Companion App should be designed to support:

- Secure sign-in
- Device setup
- Device pairing
- Connection management
- Consent management
- Permission settings
- Device state
- Battery state
- User safety controls
- Firmware updates
- Future Soul's Echo devices
Do not tightly couple application architecture to only one physical product.

---

## 18. Accessibility
Accessibility must be considered during development.

Where relevant, support:

- Screen readers
- Appropriate contrast
- Scalable text
- Clear touch targets
- Non-colour-only status indicators
- Haptic alternatives
- Clear confirmation states
- Accessible error messages
Accessibility defects should not automatically be treated as cosmetic defects.

---

## 19. Testing Requirements
New functionality should include appropriate testing.

Depending on the layer, tests may include:

- Unit tests
- Integration tests
- API tests
- Component tests
- End-to-end tests
- Firmware tests
- Hardware-in-the-loop tests
- Security tests
Critical consent, authentication and authorisation behaviour must be tested.

Do not rely solely on happy-path testing.

Test failure conditions.

---

## 20. Required Failure Scenarios
Where relevant, test:

- No network
- Slow network
- Backend unavailable
- Authentication expiry
- Revoked permission
- Device offline
- Bluetooth disconnected
- Duplicate event
- Delayed event
- Invalid event
- Unauthorised user
- Reset device
- Low battery
- Update failure

---

## 21. Documentation
Update documentation when implementation changes:

- Architecture
- Requirements
- Security behaviour
- Environment setup
- APIs
- Development workflow
- Important decisions
Do not allow critical project knowledge to exist only in code or chat history.

---

## 22. Architecture Decisions
Important decisions should be recorded in:

`docs/DECISIONS.md`

Record:

- Decision
- Context
- Alternatives considered
- Reason
- Consequences
- Date
Do not silently make significant architectural choices.

---

## 23. Dependencies
Before adding a new dependency, consider:

- Is it necessary?
- Is it actively maintained?
- Is the licence suitable?
- Does it introduce security risk?
- Does an existing dependency already provide the capability?
- Does the platform provide the capability natively?
Prefer fewer trusted dependencies.

---

## 24. Secrets and Environment Configuration
Secrets must never be committed to the repository.

Provide example configuration through files such as:

`.env.example`

Example files must contain placeholders only.

Real credentials must remain outside version control.

---

## 25. Git Practices
Prefer small, logical commits.

Commit messages should clearly describe the change.

Avoid combining unrelated work into one commit.

Do not commit:

- Secrets
- Generated build artefacts unless required
- Local editor files
- Temporary files
- Personal configuration
- Large binary files without a clear reason

---

## 26. Branching
For substantial development:

- Create a focused branch.
- Keep the branch limited to the relevant task.
- Test before merging.
- Document significant changes.
Do not perform large unrelated refactors while implementing a small feature.

---

## 27. Pull Requests
Where pull requests are used, include:

- What changed
- Why it changed
- How it was tested
- Security implications
- Privacy implications
- Known limitations
- Follow-up work
High-risk changes require additional review.

---

## 28. High-Risk Changes
Treat the following as high risk:

- Authentication
- Authorisation
- Consent logic
- Cryptography
- Device pairing
- Firmware update mechanisms
- Remote command handling
- Personal-data storage
- Account deletion
- Device ownership transfer
- Secret handling
Do not make high-risk changes casually.

---

## 29. No Unsupported Claims
Do not introduce product copy claiming verified:

- Battery life
- Waterproofing
- Durability
- Medical benefit
- Wellness benefit
- Security certification
- Regulatory approval
unless evidence exists in the repository.

Use clearly identified targets or provisional wording where appropriate.

---

## 30. Australian Context
The project begins from an Australian commercial and regulatory context.

Use Australian spelling in documentation.

Consider relevant Australian requirements during planning.

International expansion requirements should be treated separately where necessary.

---

## 31. Research Versus Fact
Clearly distinguish:

- Confirmed project decisions
- Technical assumptions
- Research findings
- Unvalidated hypotheses
- Future ideas
Do not convert a hypothesis into a requirement without approval.

---

## 32. If Requirements Conflict
If two project documents conflict:

1. Stop before implementing the conflicting requirement.
2. Identify the conflict.
3. Explain the implications.
4. Recommend a resolution.
5. Update the appropriate documentation after the decision is made.
Do not silently choose one interpretation.

---

## 33. If Context Is Missing
If essential context is missing:

- Inspect the repository first.
- Review all relevant documentation.
- Identify exactly what is unknown.
- Ask for the missing decision.
Do not invent business requirements.

Technical implementation details may be proposed when clearly labelled as recommendations.

---

## 34. Initial Development Behaviour
At the beginning of a new Codex session:

1. Read the project documentation.
2. Inspect repository status.
3. Inspect the directory structure.
4. Check current branch.
5. Check for uncommitted work.
6. Review dependencies.
7. Review existing tests.
8. Review open TODOs.
9. Summarise the actual current state.
10. Recommend the next logical task.
Do not immediately begin a large implementation unless specifically instructed.

---

## 35. Definition of Done
A development task is not complete merely because the code runs.

Where relevant, completion includes:

- Implementation complete
- Validation complete
- Tests passing
- Error handling considered
- Security reviewed
- Privacy reviewed
- Documentation updated
- No secrets committed
- No unrelated regressions introduced
- Outstanding limitations documented

---

## 36. Core Instruction
Soul's Echo is intended to create meaningful connected experiences between people.

Technology must remain subordinate to:

- Consent
- Safety
- Privacy
- Human control
If a proposed implementation compromises those principles, do not implement it merely because it is technically possible.
