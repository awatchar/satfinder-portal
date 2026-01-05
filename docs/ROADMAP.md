# SatFinder Ecosystem Roadmap

SatFinder is a school-oriented satellite and telecommunications learning ecosystem. It is designed to be deployable in real school environments with practical constraints (network policies, limited technical staff, inconsistent power conditions), while still enabling advanced labs (tracking, calibration, data collection) for engineering education.

This roadmap defines a coordinated direction across the SatFinder repositories:

- SatFinder Node Build Guide: https://github.com/awatchar/satfinder-node-build-guide  
- SatFinder Pass Simulator: https://github.com/awatchar/satfinder-pass-simulator  
- SatFinder Beam Tracker Lab: https://github.com/awatchar/satfinder-beam-tracker-lab  
- SatFinder Portal (this repository): https://github.com/awatchar/satfinder-portal  

The roadmap is organized around: (1) school deployment reliability, (2) educational outcomes, and (3) technical extensibility.

---

## 1. Vision and Core Principles

### 1.1 Vision
Enable schools to operate a consistent, safe, and reproducible “satellite/telecom learning station” that supports:
- classroom learning (concepts, simulation, observation),
- technical labs (tracking, calibration, measurements),
- and scalable multi-school deployment (standardized configuration and documentation).

### 1.2 Core Principles
1. **Deployability first**: Every component must work under typical school constraints.
2. **Repeatability and maintenance**: A school node must be installable, maintainable, and recoverable by local staff.
3. **Progressive complexity**: The ecosystem supports learning from beginner to advanced levels.
4. **Documentation as a product**: Build guides and runbooks are treated as first-class deliverables.
5. **Open and modular**: Encourage independent improvement and optional integrations without breaking baselines.

---

## 2. User Personas and Target Outcomes

### 2.1 Personas
- **Teachers / Facilitators**: need reliable instructions and classroom activities.
- **Students**: need clear learning steps and visible outcomes (simulation, tracking, logs).
- **School Technicians**: need stable deployment procedures, troubleshooting, and recovery steps.
- **Engineering Teams / Advanced Labs**: need calibration workflows, measurement repeatability, and tooling.

### 2.2 Target Outcomes
- Consistent baseline station deployment (node build guide)
- Operator understanding of satellite passes (pass simulator)
- Advanced tracking & pointing calibration capability (beam tracker lab)
- Clear cross-repo pathway and governance (portal)

---

## 3. Workstreams

### Workstream A: School Node Deployment Reliability
Goal: make the baseline station robust in school environments.

Key topics:
- Network constraints (2.4 GHz Wi-Fi, captive portal avoidance, authentication limitations)
- Power stability, safe cabling, physical mounting, and reproducible wiring
- “Known good” component lists and version pinning
- Troubleshooting flowcharts and checklists

Deliverables (portal-level):
- Standardized “School Deployment Checklist”
- Cross-repo Troubleshooting Index
- Known constraints and mitigation patterns (e.g., network authentication avoidance)

---

### Workstream B: Classroom Experience and Learning Path
Goal: define a teaching-forward path from concept to practice.

Key topics:
- Lesson flow: simulation → observation → measurement → interpretation
- Packaged activities that produce take-home artifacts (plots, logs, reports)
- Clear entry-level “first success” tasks within 30–60 minutes

Deliverables:
- A recommended curriculum outline (lightweight)
- Teacher quick-start guide referencing each repo step-by-step
- Assessment rubrics (optional but recommended)

---

### Workstream C: Tracking and Calibration Lab Maturity
Goal: make tracking/calibration workflows reliable and credible for engineering labs.

Key topics:
- Calibration workflows (e.g., alignment at 90/180/270/360)
- Error characterization (systematic vs random errors, backlash, mechanical tolerances)
- Measurement outputs (e.g., radiation pattern visualization, smoothing and averaging choices)
- Integration patterns (rotators, motion controllers, interfaces)

Deliverables:
- Calibration runbook
- Data artifact standard (CSV schema, metadata, time sync)
- Visualization and reporting guidance (credible plots and uncertainty notes)

---

### Workstream D: Ecosystem Consistency and Release Engineering
Goal: keep multiple repos coherent and easy to consume.

Key topics:
- Versioning approach and compatibility notes across repos
- Release packaging consistency (Windows zips, checksums, changelogs)
- Documentation structure standardization

Deliverables:
- Cross-repo “Compatibility Matrix” (by version)
- Release template standard and verification checklist
- Portal as the canonical index of current stable links

---

## 4. Milestones and Timeline (Indicative)

The timeline is intentionally flexible. It is expressed in phases aligned to typical education deployment cycles.

### Phase 1: Baseline Portal and Onboarding (0–2 months)
Objectives:
- Make it trivial for a new school/team to find the correct repo and path.

Portal deliverables:
- Stable repository index and recommended path
- Governance and roadmap documents
- Cross-repo links validated

Component repo deliverables:
- Ensure each repo has: Overview, Install (Source/Releases), Troubleshooting (minimum)

Acceptance criteria:
- A new user can identify which repo to use in under 5 minutes
- Onboarding path is unambiguous and tested from scratch

---

### Phase 2: Deployment Reliability Standard (2–5 months)
Objectives:
- Standardize school deployment steps and troubleshooting.

Portal deliverables:
- “School Deployment Checklist” (power/network/mounting)
- Troubleshooting index linking to exact sections in each repo

Component repo deliverables:
- Network and connectivity constraints documented with mitigations
- “Known good” configurations listed

Acceptance criteria:
- Field deployments show reduced setup time and fewer repeated support questions
- Common failure modes and fixes are documented and reproducible

---

### Phase 3: Classroom Packaging and Artifacts (5–9 months)
Objectives:
- Translate the ecosystem into classroom activities with measurable outcomes.

Portal deliverables:
- Teacher quick-start and lesson flow references
- Template for student take-home artifacts (reports/plots/logs)

Component repo deliverables:
- Pass simulator: exportable artifacts and simple guided exercises
- Node build guide: verification steps aligned to lessons

Acceptance criteria:
- A teacher can run a complete activity with minimal external support
- Students can produce artifacts suitable for sharing/evaluation

---

### Phase 4: Advanced Lab Maturity and Research Readiness (9–15 months)
Objectives:
- Improve beam tracker lab credibility for measurement and engineering research.

Portal deliverables:
- Data artifact standard and metadata requirements
- Quality guidance for plots (smoothing, averaging, uncertainty explanation)

Component repo deliverables:
- Beam tracker lab: calibration runbook, error modeling notes, reproducible workflows

Acceptance criteria:
- Labs can replicate calibration results across sessions
- Outputs are defensible in academic presentations and reports

---

## 5. Cross-Repository Technical Strategy

### 5.1 Interface and Data Contracts
To avoid tight coupling, SatFinder components should communicate through:
- documented file formats (CSV/JSON),
- stable configuration templates,
- and explicit versioned outputs.

Examples:
- Pass simulator exports: timestamped az/el predictions with metadata
- Beam tracker lab logs: device identifiers, calibration parameters, sampling rates

### 5.2 Compatibility Management
Each repo should declare:
- Supported OS (e.g., Windows 11)
- Hardware assumptions (controllers, rotators)
- Known incompatibilities and constraints

Portal maintains a Compatibility Matrix (planned deliverable).

---

## 6. Quality Assurance and Field Validation

### 6.1 Definition of “Field Ready”
A component is “field ready” when:
- installation from Releases is reliable,
- core workflow is documented with step-by-step verification,
- and major failure modes are addressed.

### 6.2 Validation Practices
- Maintain test runs with real school network and power conditions
- Use checklists and logs to reproduce outcomes
- Track issues with environment metadata (OS, device versions, network constraints)

---

## 7. Risks and Mitigations

### Risk: School network authentication and captive portals
Mitigation:
- Explicit requirement: deployments must avoid authentication barriers unless supported
- Provide known patterns (dedicated router/AP, non-auth Ethernet, 2.4 GHz configuration)

### Risk: Hardware variability and supply changes
Mitigation:
- “Known good” BOMs and alternatives
- Version pinning and compatibility notes

### Risk: Over-complexity for schools
Mitigation:
- Maintain a baseline tier with minimal steps
- Keep advanced lab features optional and modular

---

## 8. How This Roadmap Is Maintained

- The portal repository is the canonical location for cross-repo roadmap updates.
- Major cross-repo changes should be proposed via an issue in this portal.
- The roadmap is updated when:
  - a new repo is added,
  - a major workflow changes,
  - or a major deployment finding requires new guidance.

