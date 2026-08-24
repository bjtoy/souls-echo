# Soul's Echo — Risk Register
**Document:** Risk Register
**Project:** Soul's Echo
**Status:** Active
**Version:** 0.1
**Phase:** Pre-development

---

## 1. Purpose
This document identifies and tracks significant risks associated with the development and commercialisation of Soul's Echo.

The register covers:

- Product
- Customer
- Safety
- Security
- Privacy
- Hardware
- Firmware
- Software
- Manufacturing
- Supply chain
- Regulatory
- Intellectual property
- Financial
- Commercial
- Operational
- Reputational risks
Risk management is continuous.

A risk does not disappear merely because development progresses.

---

## 2. Risk Rating
Each risk may be assessed using:

### Likelihood
**1 — Rare**
Unlikely to occur.

**2 — Unlikely**
Could occur but is not expected.

**3 — Possible**
Could reasonably occur.

**4 — Likely**
Expected to occur under plausible circumstances.

**5 — Almost Certain**
Expected to occur frequently or under normal conditions.

### Impact
**1 — Insignificant**
Minimal project consequence.

**2 — Minor**
Manageable consequence.

**3 — Moderate**
Meaningful impact requiring intervention.

**4 — Major**
Serious product, financial, legal or user impact.

**5 — Severe**
Potentially threatens users, the product or the viability of the business.

---

## 3. Risk Score
Preliminary risk score:

**Likelihood × Impact**

Indicative interpretation:

| Score | Level |
|---:|---|
| 1–4 | Low |
| 5–9 | Moderate |
| 10–16 | High |
| 17–25 | Critical |

These ratings support prioritisation but do not replace judgement.

A low-probability safety or security event may still require substantial control because of its potential consequences.

### Control Status

Unless a risk entry explicitly labels a control as an **Existing Control** and
links it to evidence, entries under the legacy heading **Controls** describe
planned or required treatment, not implemented software, hardware or operational
protection. An approved requirement or decision is a governance control only; it
does not prove that the product control exists.

Future reviews should use **Existing Controls** and **Planned Treatment**
explicitly and record evidence for implemented controls.

---

# PRODUCT AND CUSTOMER RISKS

## RISK-001 — Insufficient Customer Demand
**Category:** Customer / Commercial
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
Potential customers may like the Soul's Echo concept but may not value it enough to purchase and continue using a dedicated physical product.

### Consequences

- Poor sales
- Unsustainable manufacturing volumes
- Unsold inventory
- Loss of development investment
- Business failure

### Controls

- Customer interviews
- Problem validation
- Concept testing
- Willingness-to-pay research
- Prototype testing
- Pre-production demand validation

### Current Action
Complete Gate 1 customer validation before substantial manufacturing investment.

---

## RISK-002 — Novelty Wears Off
**Category:** Product
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Users may initially enjoy remote physical interactions but stop using the product once novelty declines.

### Controls
Research:

- Long-term emotional value
- Natural usage rituals
- Continued wear
- Repeat interactions
- Reasons for abandonment
Avoid artificially increasing engagement merely to improve usage metrics.

---

## RISK-003 — Users Prefer Existing Communication
**Category:** Product / Customer
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Customers may decide messaging, calls and existing wearable products already solve the problem sufficiently.

### Controls
Customer research must identify situations where Soul's Echo provides genuinely additional value.

---

## RISK-004 — Product Feels Intrusive
**Category:** Product / Consent
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
Remote physical interaction may feel intrusive, annoying or uncomfortable rather than meaningful.

### Controls

- Explicit consent
- Pause
- Revocation
- Rate limits
- Bounded interactions
- User testing
- Customisable permissions

---

# INTERPERSONAL SAFETY AND CONSENT

## RISK-005 — Harassment Through Repeated Interaction
**Category:** Safety / Consent
**Owner:** Product Safety Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
An authorised user may repeatedly trigger another person's Band in an unwanted manner.

### Controls

- Rate limiting
- Firmware output bounds
- Pause
- Blocking
- Revocation
- Recipient-controlled permissions
- Abuse reporting consideration

### Planned Treatment

- Validate understanding of pause, block, disconnect and permission revocation during Gate 1
- Require phone-independent local inhibit
- Invalidate undelivered events after block or applicable revocation
- Test privacy-preserving protective outcomes

---

## RISK-006 — Former Partner Retains Access
**Category:** Consent / Security
**Owner:** Product Safety Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
A relationship may end while digital permissions remain active.

### Controls

- Independent revocation
- Clear relationship management
- Immediate permission invalidation
- Secure device ownership model
- User education

### Planned Treatment

- Define revocation propagation across queues, sessions, applications and Bands
- Validate former-partner scenarios during Gate 1

---

## RISK-007 — Coercive Control
**Category:** Safety / Privacy
**Owner:** Product Safety Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
A person may pressure another user into maintaining access or permissions.

### Controls

- Recipient-controlled permissions
- Independent revocation
- Local control
- Privacy-conscious design
- Future specialist review of coercive-control scenarios

### Residual Concern
Technology cannot eliminate interpersonal coercion.

The product should nevertheless avoid making coercion easier.

The likelihood is preliminary and must be reassessed after Gate 1 research
informed by coercive-control scenarios.

---

## RISK-008 — Consent Is Misunderstood
**Category:** Consent / UX
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Users may accept permissions without understanding what remote access enables.

### Controls

- Plain-language consent
- Clear permission descriptions
- UX testing
- Granular permissions
- Easy review and revocation

### Planned Treatment

- Test comprehension of pause, block, disconnect, permission revocation and local inhibit as distinct operations

---

# SECURITY RISKS

## RISK-009 — User Account Takeover
**Category:** Security
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
An attacker gains control of a user's account.

### Potential Consequences

- Relationship information exposure
- Device manipulation attempts
- Permission changes
- Privacy breach

### Controls

- Secure authentication
- Session protection
- Account recovery security
- Rate controls
- MFA/passkey evaluation
- Security monitoring

---

## RISK-010 — Unauthorised Remote Band Control
**Category:** Security / Safety
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
An attacker triggers physical outputs without legitimate permission.

### Controls
Defence in depth:

- Authentication
- Authorisation
- Relationship validation
- Permission validation
- Event security
- Device authentication
- Firmware validation
- Local safety limits

---

## RISK-011 — BLE Attack
**Category:** Security / Hardware
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
A nearby attacker exploits BLE discovery, pairing or communication.

### Controls

- Secure pairing
- Device authentication
- Appropriate BLE security modes
- Replay protection
- Security testing
- Firmware updates

---

## RISK-012 — Replay Attack
**Category:** Security
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
An attacker captures a legitimate interaction and retransmits it later.

### Controls

- Event identifiers
- Expiry
- Nonces or sequence mechanisms
- Cryptographic integrity
- Duplicate detection
Final design remains pending.

---

## RISK-013 — Backend Compromise
**Category:** Security
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
An attacker gains unauthorised access to backend infrastructure.

### Controls

- Least privilege
- Secure deployment
- Secret management
- Monitoring
- Patch management
- Network controls
- Strong administrative authentication
- Independent security assessment

---

## RISK-014 — Production Secret Leakage
**Category:** Security
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
Production credentials or cryptographic secrets are exposed.

### Controls

- Secret management
- No secrets in Git
- Access restrictions
- Credential rotation
- Environment separation
- Key-management procedures

---

## RISK-015 — Firmware Signing Key Compromise
**Category:** Security / Firmware
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
An attacker obtains the ability to sign malicious firmware.

### Controls

- Restricted key access
- Secure key storage
- Formal signing process
- Key rotation/recovery planning
- No private keys in source control

---

# PRIVACY RISKS

## RISK-016 — Exposure of Private Relationships
**Category:** Privacy
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
A breach or poor design reveals users' private interpersonal connections.

### Controls

- Data minimisation
- Access control
- Encryption
- Privacy-conscious APIs
- No public relationship discovery by default

---

## RISK-017 — Excessive Interaction History
**Category:** Privacy
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
The platform accumulates detailed records of when and how people interact.

### Controls

- Do not assume persistent history is required
- Minimise event metadata
- Define retention
- Conduct privacy review before introducing history features

---

## RISK-018 — Third-Party Data Collection
**Category:** Privacy / Supply Chain
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Cloud services, SDKs or analytics providers collect more user information than expected.

### Controls

- Third-party assessment
- Minimise SDKs
- Review data flows
- Contract review
- Prefer privacy-preserving services

---

# HARDWARE RISKS

## RISK-019 — Battery Life Is Inadequate
**Category:** Hardware / Product
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Real-world battery life may be too short for an acceptable wearable experience.

### Controls

- Power modelling
- Low-power component selection
- Prototype measurement
- Firmware optimisation
- Real-world testing
Do not publish battery claims before validation.

---

## RISK-020 — Battery Safety Failure
**Category:** Safety / Hardware
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
Battery, charging or enclosure failure creates thermal or physical hazards.

### Controls

- Reputable cells
- Appropriate protection circuitry
- Charging controls
- Thermal testing
- Mechanical protection
- Compliance testing
- Qualified engineering review

---

## RISK-021 — Poor Wearability
**Category:** Hardware / Product
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
The Band is uncomfortable, bulky or aesthetically undesirable.

### Controls

- Industrial-design exploration
- Physical mock-ups
- Wear testing
- Multiple sizes where justified
- Customer feedback

---

## RISK-022 — Haptic Experience Is Poor
**Category:** Hardware / Product
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Haptic feedback may be too weak, too strong, noisy, unpleasant or inconsistent.

### Controls

- Actuator comparison
- Enclosure testing
- User testing
- Firmware bounds
- Pattern testing

---

## RISK-023 — Accidental Activation
**Category:** Hardware / UX
**Owner:** Product Safety Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 3
**Score:** 9 — Moderate

### Risk
Normal movement or contact triggers unintended interactions.

### Controls

- Input technology evaluation
- Gesture/input design
- Debouncing
- Intent confirmation where appropriate
- Real-world wear testing

---

## RISK-024 — Poor Water Resistance
**Category:** Hardware
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Daily exposure to sweat, rain or water damages the Band.

### Controls

- Appropriate enclosure design
- Seal design
- Charging-interface consideration
- Ingress testing
- Validated IP target

---

# FIRMWARE AND SOFTWARE RISKS

## RISK-025 — Firmware Update Bricks Device
**Category:** Firmware
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
Interrupted or defective firmware updates render Bands unusable.

### Controls

- Recovery architecture
- Image validation
- Safe bootloader
- Staged rollout
- Update testing
- Rollback strategy where appropriate

---

## RISK-026 — Mobile OS Background Restrictions
**Category:** Mobile / Reliability
**Likelihood:** 4
**Impact:** 4
**Score:** 16 — High

### Risk
iOS or Android background restrictions interfere with timely communication between backend, application and Band.

### Controls

- Early technical prototyping
- Platform-native mechanisms
- Push delivery research
- BLE background testing
- Architecture validation on physical devices

---

## RISK-027 — Remote Interaction Latency Is Too High
**Category:** Technical / Product
**Owner:** Technical Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Interactions arrive too slowly to feel immediate or emotionally connected.

### Controls

- Prototype early
- Measure end-to-end latency
- Compare delivery architectures
- Test real mobile networks
- Define acceptable latency based on user research

---

## RISK-028 — Duplicate or Delayed Events
**Category:** Reliability / Safety
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Network retries or delayed delivery cause unexpected physical responses.

### Controls

- Idempotency
- Event IDs
- Expiry
- Duplicate detection
- Firmware safeguards

### Planned Treatment

- Separately define duplicate, delayed, out-of-order and acknowledgement-loss behaviour
- Validate blocking and revocation during event transit

---

# MANUFACTURING AND SUPPLY CHAIN RISKS

## RISK-029 — Component Shortage
**Category:** Supply Chain
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Critical components become unavailable or experience long lead times.

### Controls

- Lifecycle assessment
- Alternative components
- Supplier diversification
- Early procurement planning
- Avoid obsolete components

---

## RISK-030 — Manufacturing Quality Problems
**Category:** Manufacturing
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
Production devices suffer inconsistent assembly, sealing, battery, charging or electronic defects.

### Controls

- Design for Manufacture
- Design for Assembly
- Production testing
- Supplier qualification
- Pilot production
- Quality-control processes

---

## RISK-031 — Manufacturing Cost Exceeds Target
**Category:** Commercial / Manufacturing
**Owner:** Commercial Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
The Band cannot be manufactured at a cost compatible with sustainable retail pricing.

### Controls

- Early BOM modelling
- Supplier quotations
- Design-to-cost reviews
- Margin modelling
- Alternative components
- Avoid unnecessary features

---

# REGULATORY AND LEGAL RISKS

## RISK-032 — Regulatory Requirements Are Underestimated
**Category:** Regulatory
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
Required radio, electrical, battery, privacy, product-safety or other obligations are discovered late.

### Controls

- Early regulatory mapping
- Qualified professional advice
- Compliance planning before final hardware
- Maintain evidence and technical documentation

---

## RISK-033 — Unsupported Product Claims
**Category:** Legal / Brand
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Marketing claims exceed available evidence.

Potential areas include:

- Battery life
- Waterproofing
- Durability
- Security
- Wellness
- Medical benefits

### Controls
Only publish claims supported by appropriate evidence.

---

# INTELLECTUAL PROPERTY RISKS

## RISK-034 — Soul's Echo Name Conflict
**Category:** Intellectual Property / Brand
**Owner:** Project Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
The Soul's Echo name conflicts with existing trade marks or commercial rights.

### Controls

- Preliminary searches
- Professional trade mark assessment
- Appropriate registration strategy before substantial brand investment

---

## RISK-035 — Product Infringes Existing Patent
**Category:** Intellectual Property
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
Technical or interaction mechanisms conflict with enforceable third-party patents.

### Controls

- Prior-art research
- Patent landscape review
- Professional freedom-to-operate advice at the appropriate stage

---

## RISK-036 — Contractor or Supplier IP Ownership Is Unclear
**Category:** Intellectual Property / Operational
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
External designers, developers or manufacturers retain rights required by Soul's Echo.

### Controls
Use appropriate written agreements addressing:

- IP ownership
- Confidentiality
- Deliverables
- Source files
- Tooling
- Firmware
- Design files
Obtain professional legal advice where required.

---

# FINANCIAL RISKS

## RISK-037 — Development Cost Escalation
**Category:** Financial
**Owner:** Project Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 4
**Impact:** 5
**Score:** 20 — Critical

### Risk
Hardware, firmware, tooling, testing, certification, software and manufacturing costs exceed available funding.

### Controls

- Stage-gated investment
- Budget per gate
- Prototype before tooling
- Validate demand early
- Maintain contingency
- Avoid premature ecosystem expansion

---

## RISK-038 — Working Capital Shortfall
**Category:** Financial
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
Manufacturing requires payment before customer revenue is received.

### Controls

- Cash-flow modelling
- MOQ analysis
- Controlled launch
- Financing strategy
- Inventory discipline
- Supplier payment negotiation

---

## RISK-039 — Excess Inventory
**Category:** Financial / Commercial
**Likelihood:** 3
**Impact:** 4
**Score:** 12 — High

### Risk
Demand is lower than forecast after production inventory has been purchased.

### Controls

- Validate demand
- Conservative initial production
- Pilot manufacturing
- Avoid optimistic volume commitments

---

# OPERATIONAL RISKS

## RISK-040 — Founder/Key-Person Dependency
**Category:** Operational
**Likelihood:** 4
**Impact:** 4
**Score:** 16 — High

### Risk
Critical project knowledge exists primarily with one person or within conversational tools.

### Controls

- Repository documentation
- Decision register
- Version control
- Architecture documentation
- Requirements traceability
- Supplier documentation
- Repeatable processes

---

## RISK-041 — Project Knowledge Lost Across AI Tools
**Category:** Development Process
**Likelihood:** 4
**Impact:** 3
**Score:** 12 — High

### Risk
Important context is lost when work moves between ChatGPT, Codex or other development tools.

### Controls

- `PROJECT_HANDOFF.md`
- `CODEX.md`
- Repository documentation
- Decision records
- Requirements IDs
- Git history
The repository remains the technical source of truth.

---

## RISK-042 — Software Assurance Failure
**Category:** Development / Security
**Owner:** Technical Lead
**Status:** Open
**Next Review:** Every development gate
**Likelihood:** 4
**Impact:** 5
**Score:** 20 — Critical

### Risk
Software, firmware or infrastructure changes, whether human- or AI-generated, may
appear functional while containing:

- Security vulnerabilities
- Incorrect assumptions
- Missing failure handling
- Dependency problems
- Architectural inconsistencies

### Controls

- Human review
- Automated tests
- Security testing
- Requirements traceability
- Small changes
- Independent review for high-risk components
- Never treat generated code as inherently correct
- Apply equivalent assurance to human- and AI-generated implementation

---

# REPUTATIONAL RISKS

## RISK-043 — Privacy or Security Incident Damages Trust
**Category:** Reputation / Security
**Likelihood:** 2
**Impact:** 5
**Score:** 10 — High

### Risk
A breach involving an intimate connected product may substantially damage customer trust.

### Controls

- Privacy by design
- Security by design
- Data minimisation
- Incident response
- Vulnerability management
- Transparent communication

---

## RISK-044 — Product Perceived as Surveillance Technology
**Category:** Brand / Product
**Owner:** Product Lead
**Status:** Open
**Next Review:** Gate 1
**Likelihood:** 3
**Impact:** 5
**Score:** 15 — High

### Risk
Customers or media interpret Soul's Echo as a tracking or controlling product rather than a consent-based connection product.

### Controls

- No continuous location requirement
- Strong consent model
- Clear messaging
- Recipient control
- Transparent privacy design
- Avoid surveillance-like features

---

# PROJECT GOVERNANCE RISKS

## RISK-045 — Scope Creep
**Category:** Project
**Owner:** Project Lead
**Status:** Open
**Next Review:** Every gate
**Likelihood:** 5
**Impact:** 4
**Score:** 20 — Critical

### Risk
Additional devices and features expand the project before the Band MVP is validated.

### Controls
Use classifications:

- MVP Mandatory
- MVP Desirable
- Post-MVP
- Future Research
- Rejected
Future products do not enter MVP development without an explicit decision.

Speculative generic architecture for unvalidated future products is also scope
expansion and requires a concrete Band requirement or later explicit decision.

---

## RISK-046 — Technology Selected Too Early
**Category:** Architecture
**Likelihood:** 4
**Impact:** 4
**Score:** 16 — High

### Risk
The project commits to a technology because it is familiar or convenient before understanding production requirements.

### Controls

- Logical architecture first
- Structured technology comparisons
- Prototype testing
- Decision records
- Review difficult-to-reverse choices

---

## RISK-047 — Prototype Shortcuts Become Production Architecture
**Category:** Architecture / Security
**Owner:** Technical Lead
**Status:** Open
**Next Review:** Before prototype implementation and production promotion
**Likelihood:** 4
**Impact:** 5
**Score:** 20 — Critical

### Risk
Temporary prototype choices remain in the product because replacing them later appears inconvenient.

### Controls

- Clearly label prototype architecture
- Record technical debt
- Production-readiness review
- Security review
- Explicit architecture decisions

### Planned Treatment

- Define prototype-only controls and explicit promotion criteria before implementation

---

## RISK-048 — Recipient Cannot Stop Interaction Without a Phone
**Category:** Safety / Consent / Hardware
**Owner:** Product Safety Lead
**Status:** Open
**Likelihood:** Unscored — requires Gate 1 evidence
**Impact:** Unscored — requires safety assessment
**Score:** Not yet assigned
**Next Review:** Gate 1

### Risk
The recipient cannot practically inhibit incoming physical interactions when a
phone is unavailable, compromised or unusable.

### Existing Controls
Approved requirement for a phone-independent Band-local inhibit.

### Planned Treatment
Validate user expectations during Gate 1 and evaluate accessible physical
implementations during product definition and prototyping.

---

## RISK-049 — Revocation Races with an Event in Transit
**Category:** Consent / Reliability / Security
**Owner:** Technical Lead
**Status:** Open
**Likelihood:** Unscored — requires architecture analysis
**Impact:** Unscored — requires safety assessment
**Score:** Not yet assigned
**Next Review:** Before architecture selection

### Risk
An event produces output after a block, revocation or permission reduction because
an intermediate component retains older authority.

### Existing Controls
Recipient-authority and fail-closed requirements.

### Planned Treatment
Define authoritative state, event lifecycle, propagation and race semantics.

---

## RISK-050 — Stale Authorisation Survives Storage or Recovery
**Category:** Security / Reliability / Privacy
**Owner:** Technical Lead
**Status:** Open
**Likelihood:** Unscored — requires architecture analysis
**Impact:** Unscored — requires safety assessment
**Score:** Not yet assigned
**Next Review:** Before architecture selection

### Risk
A queue, cache, application, Band, backup or restored system retains obsolete
consent or permission state.

### Planned Treatment
Define invalidation and disaster-recovery invariants before technology selection.

---

## RISK-051 — Lost, Stolen or Compromised Phone Retains Authority
**Category:** Security / Consent
**Owner:** Security Lead
**Status:** Open
**Likelihood:** Unscored — requires threat modelling
**Impact:** Unscored — requires threat modelling
**Score:** Not yet assigned
**Next Review:** Before architecture selection

### Planned Treatment
Define session revocation, replacement and recovery workflows.

---

## RISK-052 — Lost, Stolen or Compromised Band Remains Trusted
**Category:** Security / Device Ownership
**Owner:** Security Lead
**Status:** Open
**Likelihood:** Unscored — requires threat modelling
**Impact:** Unscored — requires threat modelling
**Score:** Not yet assigned
**Next Review:** Before architecture selection

### Planned Treatment
Define credential revocation, quarantine and reassignment controls.

---

## RISK-053 — Ownership Transfer Preserves Previous Access
**Category:** Security / Consent / Device Ownership
**Owner:** Security Lead
**Status:** Open
**Likelihood:** Unscored — requires lifecycle design
**Impact:** Unscored — requires safety assessment
**Score:** Not yet assigned
**Next Review:** Before architecture selection

### Planned Treatment
Define transfer invariants that invalidate previous credentials, relationships and
permissions.

---

## RISK-054 — Protective Status Disclosure Causes Harm
**Category:** Interpersonal Safety / Privacy
**Owner:** Product Safety Lead
**Status:** Open
**Likelihood:** Unscored — requires Gate 1 evidence
**Impact:** Unscored — requires specialist assessment
**Score:** Not yet assigned
**Next Review:** Gate 1

### Planned Treatment
Research sender feedback, coercion and former-partner scenarios; minimise status
disclosure by default.

---

## RISK-055 — Shared Phone or Band Creates Ambiguous Authority
**Category:** Consent / Device Ownership
**Owner:** Product Lead
**Status:** Open
**Likelihood:** Unscored — requires Gate 1 evidence
**Impact:** Unscored — requires safety assessment
**Score:** Not yet assigned
**Next Review:** Gate 1

### Planned Treatment
Research shared-device realities and define authority before architecture selection.

---

## RISK-056 — Account Recovery Bypasses Recipient Control
**Category:** Security / Interpersonal Safety
**Owner:** Security Lead
**Status:** Open
**Likelihood:** Unscored — requires threat modelling
**Impact:** Unscored — requires threat modelling
**Score:** Not yet assigned
**Next Review:** Before architecture selection

### Planned Treatment
Threat-model recovery, notifications, reauthentication and restored authority.

---

## RISK-057 — Manufacturing Provisioning Compromise
**Category:** Security / Manufacturing
**Owner:** Security Lead
**Status:** Open
**Likelihood:** Unscored — requires manufacturing architecture
**Impact:** Unscored — requires threat modelling
**Score:** Not yet assigned
**Next Review:** Before manufacturing architecture selection

### Planned Treatment
Define credential injection, custody, traceability and rejected-unit handling.

---

## RISK-058 — Security Support Ends While Devices Remain in Use
**Category:** Security / Commercial
**Owner:** Project Lead
**Status:** Open
**Likelihood:** Unscored — requires commercial planning
**Impact:** Unscored — requires security assessment
**Score:** Not yet assigned
**Next Review:** Before commercial release

### Planned Treatment
Define supported lifetime, end-of-support communication and safe retirement.

---

## RISK-059 — Disaster Recovery Restores Obsolete Consent
**Category:** Reliability / Consent / Security
**Owner:** Technical Lead
**Status:** Open
**Likelihood:** Unscored — requires deployment design
**Impact:** Unscored — requires safety assessment
**Score:** Not yet assigned
**Next Review:** Before architecture selection

### Planned Treatment
Define recovery invariants, restoration testing and stale-authorisation controls.

---

## RISK-060 — Delivery Feedback Exposes Behaviour or Presence
**Category:** Privacy / Interpersonal Safety
**Owner:** Product Safety Lead
**Status:** Open
**Likelihood:** Unscored — requires Gate 1 evidence
**Impact:** Unscored — requires privacy assessment
**Score:** Not yet assigned
**Next Review:** Gate 1

### Planned Treatment
Research user value and harmful inference; minimise feedback by default.

---

## RISK-061 — Local Safety Control Is Inaccessible
**Category:** Accessibility / Safety
**Owner:** Product Safety Lead
**Status:** Open
**Likelihood:** Unscored — requires user research
**Impact:** Unscored — requires safety assessment
**Score:** Not yet assigned
**Next Review:** Gate 1 and Gate 2

### Planned Treatment
Include varied dexterity, sensory and situational needs in research and prototype
validation.

---

## RISK-062 — Mobile Delivery Dependency Undermines Core Reliability
**Category:** Mobile / Product / Reliability
**Owner:** Technical Lead
**Status:** Open
**Likelihood:** Unscored — requires feasibility testing
**Impact:** Unscored — requires product research
**Score:** Not yet assigned
**Next Review:** Before mobile architecture selection

### Planned Treatment
Define foreground, background, suspended and terminated behaviour and test on
physical devices before framework selection.

---

# RISK GOVERNANCE

## 4. Risk Owners
Critical risks and risks requiring action in the next gate must have an accountable
role. A named individual should replace the role when responsibility is formally
assigned.

An owner is responsible for ensuring the risk is monitored and appropriate treatment occurs.

Ownership does not mean one person is solely responsible for preventing the risk.

---

## 5. Residual Risk
Controls rarely eliminate all risk.

Future versions of this register should distinguish:

- Inherent risk
- Controls
- Residual risk

---

## 6. Review Frequency
Review the risk register:

- At each development gate
- After major architectural decisions
- After significant security findings
- After customer research
- Before external testing
- Before manufacturing commitment
- Before commercial launch
- After significant incidents

---

## 7. Escalation
Critical risks require explicit consideration before the project accepts additional exposure.

A critical risk must not be ignored simply because solving it is inconvenient.

---

## 8. New Risk Template

### RISK-XXX — Risk Title
**Category:**
**Owner:**
**Status:** Open
**Likelihood:**
**Impact:**
**Score:**

#### Risk
Describe the uncertain event.

#### Cause
Describe why it may occur.

#### Consequences
Describe potential effects.

#### Existing Controls
List current protections.

#### Additional Treatment
Describe further action.

#### Residual Risk
Record remaining risk after treatment.

#### Review Trigger
State when the risk should be reassessed.

---

## 9. Current Critical Risks
Based on this preliminary assessment, the current highest-scoring risks include:

- `RISK-037` — Development cost escalation
- `RISK-042` — AI-generated implementation defects
- `RISK-042` — Software assurance failure
- `RISK-045` — Scope creep
- `RISK-047` — Prototype shortcuts becoming production architecture
These scores are preliminary and should change as evidence becomes available.

---

## 10. Immediate Risk Priorities
During the next stages, particular attention should be given to:

1. Customer demand.
2. Intellectual property.
3. Development cost.
4. Consent and interpersonal safety.
5. Technical feasibility.
6. Mobile background connectivity.
7. Security architecture.
8. Manufacturing economics.
9. Regulatory requirements.
10. Scope control.

---

## 11. Governing Principle
Risk management does not mean eliminating uncertainty before doing anything.

Innovation necessarily involves uncertainty.

The purpose of this register is to ensure Soul's Echo takes **understood and deliberate risks rather than accidental ones**.
