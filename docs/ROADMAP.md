# Soul's Echo — Product Development Roadmap
**Document:** Product Development Roadmap
**Project:** Soul's Echo
**Status:** Working Roadmap
**Version:** 0.1
**Primary Product:** Soul's Echo Band

---

## 1. Purpose
This roadmap defines the staged development pathway for Soul's Echo from concept through commercial launch.

The roadmap is evidence-driven rather than date-driven.

A development stage is not considered complete merely because time has passed or work has begun on the next stage.

Progression requires sufficient evidence that the project is ready to accept the additional cost and risk of the following stage.

---

## 2. Roadmap Philosophy
Soul's Echo combines:

- Consumer hardware
- Embedded firmware
- Bluetooth communication
- Mobile software
- Internet services
- Personal information
- Remote physical interactions
- Manufacturing
- Regulatory obligations
This creates substantially different risks from developing a conventional application.

The project should therefore progress through controlled gates.

The objective is not to move slowly.

The objective is to avoid moving quickly in the wrong direction.

---

# GATE 0 — CONCEPT FOUNDATION

## 3. Objective
Establish what Soul's Echo is, what it is intended to achieve and the principles governing development.

---

## 4. Required Outputs
Gate 0 includes:

- Product vision
- Preliminary product requirements
- Preliminary system architecture
- Development roadmap
- Decision register
- Security and privacy foundation
- Risk register
- Repository structure
- Codex development instructions

---

## 5. Current Status
**Status: IN PROGRESS**

All planned Gate 0 foundation documents now exist:

- `PROJECT_HANDOFF.md`
- `CODEX.md`
- `README.md`
- `docs/PRODUCT_VISION.md`
- `docs/PRODUCT_REQUIREMENTS.md`
- `docs/ARCHITECTURE.md`
- `docs/ROADMAP.md`
- `docs/DECISIONS.md`
- `docs/SECURITY_PRIVACY.md`
- `docs/RISK_REGISTER.md`

Gate 0 remained open because the initial audit identified cross-document
inconsistency and an incomplete recipient-control model. Closure requires the
Gate 0 exit checklist to pass; document presence alone is insufficient.

---

## 6. Gate 0 Exit Criteria
Gate 0 may close when:

- Core product purpose is documented.
- Band MVP boundaries are documented.
- Major unresolved assumptions are visible.
- Preliminary architecture is documented.
- Security and privacy principles are documented.
- Major risks are documented.
- Development governance exists.
- Repository documentation is internally consistent.
- Recipient authority and current authorisation precedence are consistent across requirements, architecture, security and decisions.
- Phone-independent Band-local inhibition is a mandatory capability while its physical implementation remains unresolved.
- Pause, block, disconnect, permission revocation, local inhibit and factory reset are distinctly defined.
- Undelivered interactions remain subject to current recipient state and fail closed when validity cannot safely be established.
- Critical and next-gate risks have accountable roles and review gates.
- Remaining product, research and technology questions are assigned to later gates rather than silently resolved.

---

# GATE 1 — PROBLEM AND CUSTOMER VALIDATION

## 7. Objective
Determine whether the customer problem and proposed experience are sufficiently
valuable, understandable, respectful and safe to justify continued investment.

---

## 8. Key Questions
Research must investigate:

1. Do people experience meaningful emotional disconnection during physical separation?
2. Are existing communication tools insufficient in relevant situations?
3. Does a physical signal provide additional emotional value?
4. Would users wear or carry a dedicated device?
5. Which relationships are most suitable?
6. What interaction types feel meaningful?
7. What interaction types feel intrusive?
8. What privacy concerns arise?
9. What consent expectations arise?
10. What would customers reasonably pay?
11. Do users understand pause, block, disconnect and permission revocation as distinct actions?
12. How do former-partner, coercive-control, gifting and shared-device scenarios affect safety expectations?
13. What phone-independent local safety control do users expect, without prematurely selecting its mechanism?
14. What delivery feedback is useful without exposing protective or behavioural status?
15. Does the Australia-first assumption remain commercially and operationally plausible?

---

## 9. Activities
Gate 1 should include:

- Target-customer hypotheses
- Competitor research
- Jobs-to-be-Done research
- Customer interviews
- Concept testing
- Pricing research
- Willingness-to-pay research
- Gifting research
- Privacy perception research
- Consent research
- Consent-comprehension research
- Intrusiveness research
- Coercive-control and former-partner scenario research
- Gifting and shared-device research
- Local safety-control research
- Delivery-feedback and privacy-perception research
- Australia-first assumption testing
- Explicit stop and pivot criteria

---

## 10. Research Integrity
Customer interviews should test the problem rather than merely asking whether participants like the Soul's Echo idea.

Avoid leading questions such as:

> Would you buy this amazing bracelet that lets your partner know you are thinking about them?
Prefer questions examining existing behaviour, such as:

> Tell me about the last time you were away from someone important to you.
Evidence of actual behaviour should generally carry more weight than hypothetical enthusiasm.

---

## 11. Gate 1 Exit Criteria
Progression requires evidence supporting:

- A meaningful customer problem.
- A plausible initial target segment.
- Interest in the physical-interaction concept.
- Acceptable privacy expectations.
- Acceptable consent expectations.
- Plausible willingness to pay.
- No discovery that fundamentally invalidates the proposition.
- Evidence that intended users can understand and exercise the proposed protective controls.
- Evidence that delivery feedback and local-control expectations can be pursued without unacceptable interpersonal-safety or privacy compromises.
- A reviewed Australia-first planning assumption.
If evidence is weak, the project should refine, pivot or stop before expensive hardware development.

---

# GATE 2 — PRODUCT DEFINITION

## 12. Objective
Convert validated customer needs into a clearly defined first product.

---

## 13. Activities
Gate 2 should include:

- Refined Product Requirements Document
- MVP feature prioritisation
- Interaction design
- Consent flows
- Device setup flow
- Connection flow
- Disconnect flow
- Preliminary industrial design
- Accessibility requirements
- Battery target
- Durability target
- Preliminary retail-price target
- Preliminary cost target

---

## 14. Industrial Design Directions
At least three Band design directions should be explored before selecting a preferred concept.

Design evaluation should consider:

- Comfort
- Appearance
- Manufacturability
- Component volume
- Battery volume
- Antenna requirements
- Charging
- Water resistance
- Haptic transmission
- Materials
- Cost
- Customisation
- Accessibility

---

## 15. Gate 2 Exit Criteria
Progression requires:

- Defined Band MVP.
- Defined exclusions.
- Preferred industrial-design direction.
- Preliminary interaction model.
- Preliminary consent model.
- Preliminary cost target.
- Preliminary retail target.
- Defined prototype objectives.
- Defined product semantics for pause, block, disconnect, permission revocation and local inhibit.
- A preferred local-safety-control interaction direction supported by usability and accessibility evidence.

---

# GATE 3 — TECHNICAL ARCHITECTURE

## 16. Objective
Select the technologies and architecture required to build a credible prototype and establish a plausible production pathway.

---

## 17. Hardware Investigations
Compare:

- MCU/SoC candidates
- BLE capability
- Security capabilities
- Haptic actuators
- Input technologies
- LEDs/light systems
- Batteries
- Charging systems
- Antenna approaches
- Secure-element requirements

---

## 18. Software Investigations
Compare:

- Native mobile development
- Cross-platform mobile frameworks
- Backend technologies
- Database technologies
- Authentication systems
- Real-time delivery approaches
- Cloud providers
- Firmware frameworks
- CI/CD approaches

---

## 19. Security Architecture
Gate 3 should include:

- Preliminary threat model
- Trust boundaries
- Device identity
- User identity
- Pairing model
- Key-management approach
- Firmware security
- Event authentication
- Replay protection
- Revocation model
- Secure provisioning concept
- Account, device ownership, relationship, permission and event state models
- Lost, stolen, compromised, replacement and transfer workflows
- Revocation propagation and event-transit rules

---

## 20. Gate 3 Exit Criteria
Progression requires:

- Selected prototype hardware architecture.
- Selected prototype firmware approach.
- Selected mobile approach.
- Selected backend approach.
- Defined security architecture.
- Defined prototype data model.
- Defined event-delivery approach.
- Major decisions recorded in `DECISIONS.md`.
- Defined event lifecycle and failure contract.
- Defined privacy data map and preliminary retention rules.

---

# GATE 4 — PROOF OF CONCEPT

## 21. Objective
Demonstrate the smallest technically meaningful Soul's Echo experience.

---

## 22. Target Demonstration
The proof of concept should demonstrate:

```
Physical Input A
       │
       ▼
Prototype Device A
       │
       ▼
Phone A
       │
       ▼
Secure Test Backend
       │
       ▼
Phone B
       │
       ▼
Prototype Device B
       │
       ▼
Bounded Haptic Response
```

---

## 23. Proof-of-Concept Priorities
The proof of concept should validate:

- BLE communication
- Remote event delivery
- End-to-end latency
- Haptic experience
- Basic authentication
- Basic authorisation
- Event expiry
- Duplicate protection
- Local output limits
Appearance is secondary during this stage.

---

## 24. Gate 4 Exit Criteria
The proof of concept must reliably demonstrate the intended core interaction.

Major technical blockers must be understood before moving to integrated wearable prototypes.

---

# GATE 5 — ENGINEERING PROTOTYPE

## 25. Objective
Develop an integrated prototype sufficiently representative of the intended Band to test physical and technical assumptions.

---

## 26. Activities
Potential work includes:

- Custom electronics
- PCB development
- Prototype enclosure
- Battery integration
- Charging
- Haptic integration
- Input integration
- BLE firmware
- Firmware updates
- Companion App prototype
- Backend prototype
- Device provisioning
- Security implementation

---

## 27. Prototype Testing
Test:

- Comfort
- Haptic perception
- Input reliability
- Accidental activation
- BLE reliability
- Battery consumption
- Charging
- Event latency
- Event reliability
- Thermal behaviour
- Firmware updates
- Failure recovery

---

## 28. Gate 5 Exit Criteria
Progression requires evidence that the integrated system can plausibly satisfy the MVP requirements.

---

# GATE 6 — ALPHA

## 29. Objective
Create a controlled internal or closely supervised system suitable for structured end-to-end testing.

---

## 30. Alpha Scope
Alpha should include:

- Functional Band prototypes
- Functional Companion App
- Functional backend
- Account system
- Device registration
- Pairing
- Relationship creation
- Consent
- Permissions
- Remote interaction
- Pause
- Revocation
- Firmware updates

---

## 31. Alpha Testing
Alpha testing should emphasise:

- Functional defects
- Security defects
- Consent defects
- Device failures
- BLE failures
- Backend failures
- Battery behaviour
- Firmware-update failures
- Usability
- Accessibility

---

## 32. Gate 6 Exit Criteria
Critical safety, consent and security failures must be resolved before external beta testing.

---

# GATE 7 — BETA

## 33. Objective
Test the product with a limited group of appropriately informed external users.

---

## 34. Beta Research
Measure and investigate:

- Setup success
- Pairing success
- Connection success
- Interaction reliability
- Emotional value
- Unwanted interactions
- Comfort
- Battery experience
- Privacy perceptions
- Consent understanding
- Product reliability
- Support requirements

---

## 35. Beta Safety
Beta participation must not be used as an excuse to expose participants to known unacceptable risks.

Known significant security and safety defects should be addressed before expansion of testing.

---

## 36. Gate 7 Exit Criteria
Progression requires:

- Core experience validated.
- Reliability acceptable for the next stage.
- Major usability problems addressed.
- Consent model understood by users.
- No unresolved critical security defects.
- Evidence supporting continued commercialisation.

---

# GATE 8 — DESIGN FOR MANUFACTURE

## 37. Objective
Transform the validated prototype into a product that can be manufactured consistently.

---

## 38. Activities
Include:

- Final PCB development
- Design for Manufacture
- Design for Assembly
- Component sourcing
- Tooling
- Enclosure refinement
- Material selection
- Production test strategy
- Manufacturing firmware process
- Secure provisioning
- Quality-control procedures
- Packaging development

---

## 39. Supply Chain
Assess:

- Supplier reliability
- Lead times
- Minimum order quantities
- Component lifecycle
- Counterfeit risk
- Alternative components
- Manufacturing location
- Shipping
- Battery logistics
- Quality systems

---

## 40. Gate 8 Exit Criteria
The design must have a credible, repeatable and economically plausible manufacturing process.

---

# GATE 9 — COMPLIANCE AND PILOT

## 41. Objective
Complete required compliance work and validate limited production.

---

## 42. Australian Compliance
The final compliance map must be confirmed by appropriately qualified specialists.

Potential areas requiring assessment include:

- Radio communications
- Electrical/electronic compliance
- Battery safety
- Battery transport
- Consumer product safety
- Australian Consumer Law
- Privacy
- Cybersecurity
- Product labelling
- Environmental requirements
This roadmap does not substitute for professional regulatory advice.

---

## 43. Pilot Production
A pilot production run should validate:

- Assembly
- Provisioning
- Firmware installation
- Testing
- Quality control
- Packaging
- Traceability
- Failure rates
- Logistics

---

## 44. Gate 9 Exit Criteria
Commercial launch should not proceed until applicable compliance obligations are satisfied and pilot production demonstrates acceptable quality.

---

# GATE 10 — AUSTRALIAN COMMERCIAL LAUNCH

## 45. Objective
Launch Soul's Echo Band commercially in a controlled initial market.

Australia is the proposed first market unless later evidence supports another approach.

---

## 46. Launch Readiness
Before launch, establish:

- Production inventory
- E-commerce capability
- Payments
- Fulfilment
- Customer support
- Returns
- Warranty processes
- Privacy documentation
- Terms
- Security-response process
- Firmware-update capability
- Monitoring
- Incident-response procedures
- Product documentation

---

## 47. Launch Principle
A smaller reliable launch is preferable to a large launch that overwhelms manufacturing, infrastructure or customer support.

---

# GATE 11 — POST-LAUNCH VALIDATION

## 48. Objective
Determine how the product behaves outside controlled testing.

---

## 49. Monitor
Monitor appropriate indicators including:

- Activation success
- Pairing failures
- Device reliability
- Returns
- Support requests
- Firmware-update success
- Security incidents
- Unwanted-interaction reports
- Customer satisfaction
- Repeat purchases
- Gifting behaviour
Monitoring must respect privacy.

---

## 50. Product Improvement
Post-launch changes should be driven by evidence rather than uncontrolled feature expansion.

---

# GATE 12 — ECOSYSTEM EXPANSION

## 51. Objective
Consider additional Soul's Echo products only after the Band platform has demonstrated sufficient value and viability.

---

## 52. Potential Products
Future candidates include:

- Ring
- Pendant
- Dock
- Accessories
- Wellness products
- Additional connected experiences

---

## 53. Independent Validation
A successful Band does not automatically validate every future product.

Each new product requires appropriate:

- Customer research
- Safety assessment
- Security assessment
- Consent analysis
- Technical validation
- Commercial modelling
- Regulatory assessment

---

# PROJECT-WIDE WORKSTREAMS

## 54. Intellectual Property
IP work should begin early and continue throughout development.

Investigate:

- Trade marks
- Business names
- Domains
- Design protection
- Patents and prior art
- Supplier IP ownership
- Contractor IP assignment

---

## 55. Security
Security begins before implementation and continues throughout the product lifecycle.

Activities include:

- Threat modelling
- Architecture review
- Secure development
- Dependency management
- Firmware security
- Penetration testing
- Vulnerability response
- Incident response

---

## 56. Privacy
Privacy work includes:

- Data mapping
- Data minimisation
- Retention
- Deletion
- Consent
- Third-party assessment
- Privacy documentation
- International requirements

---

## 57. Commercial Model
Commercial work includes:

- Cost of goods
- Manufacturing
- Freight
- Packaging
- Payment fees
- Returns
- Warranty
- Cloud costs
- Support costs
- Retail pricing
- Gross margin
- Working capital

---

## 58. Brand
Brand development should cover:

- Name
- Identity
- Positioning
- Packaging
- Product presentation
- Digital presence
- Customer experience
Brand claims must remain consistent with validated product capabilities.

---

# CURRENT ACTION PLAN

## 59. Immediate Priority
The current priority is to complete the Gate 0 consistency and recipient-control
correction, then assess the objective Gate 0 exit checklist.

All planned foundation documents exist. Editing them does not by itself close the
gate.

---

## 60. After Gate 0
The next major activity should **not** automatically be coding.

Gate 1 requires customer and market validation.

In parallel, low-cost technical research may begin where it reduces uncertainty without prematurely committing substantial resources.

Coding is not the next project stage. Low-cost feasibility research must not be
misrepresented as production technology selection.

---

## 61. Evidence Register
As research begins, evidence should be retained under `/research`.

Suggested future structure:

```
research/
├── customers/
├── competitors/
├── hardware/
├── software/
├── regulatory/
├── intellectual-property/
└── commercial/
```
Research findings should distinguish external evidence from project assumptions.

---

## 62. Decision Discipline
Major decisions should answer:

- What did we decide?
- Why?
- What evidence supported it?
- What alternatives were considered?
- What does the decision affect?
- Can it be reversed?
Record these in `docs/DECISIONS.md`.

---

## 63. Stop Conditions
Soul's Echo should be willing to stop, reconsider or pivot if evidence demonstrates that:

- Customers do not value the core proposition.
- Users are unwilling to wear the product.
- Privacy concerns overwhelm perceived value.
- Consent cannot be implemented appropriately.
- Technical reliability is inadequate.
- Safety risks cannot be acceptably controlled.
- Manufacturing economics are unsustainable.
- Regulatory barriers make the intended model impractical.
Continuing simply because significant effort has already been invested is not a valid reason.

---

## 64. Roadmap Summary

```
Gate 0   Concept Foundation
   ↓
Gate 1   Customer Validation
   ↓
Gate 2   Product Definition
   ↓
Gate 3   Technical Architecture
   ↓
Gate 4   Proof of Concept
   ↓
Gate 5   Engineering Prototype
   ↓
Gate 6   Alpha
   ↓
Gate 7   Beta
   ↓
Gate 8   Design for Manufacture
   ↓
Gate 9   Compliance + Pilot
   ↓
Gate 10  Australian Launch
   ↓
Gate 11  Post-Launch Validation
   ↓
Gate 12  Ecosystem Expansion
```

---

## 65. Governing Principle
The purpose of the roadmap is not to predict the future perfectly.

Its purpose is to prevent Soul's Echo from spending substantial money and effort on the next stage before answering the important questions from the current one.

**Evidence earns progression.**
