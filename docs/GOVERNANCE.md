# SatFinder Ecosystem Governance

This document defines how the SatFinder ecosystem is managed across multiple repositories. The governance model is designed for an education-and-field-deployment context, where documentation quality and operational repeatability are as important as code.

Repositories in scope:
- SatFinder Portal (index and governance): https://github.com/awatchar/satfinder-portal
- Node Build Guide: https://github.com/awatchar/satfinder-node-build-guide
- Pass Simulator: https://github.com/awatchar/satfinder-pass-simulator
- Beam Tracker Lab: https://github.com/awatchar/satfinder-beam-tracker-lab

---

## 1. Governance Objectives

1. **Clarity**: Make it obvious where to find the correct information and tooling.
2. **Stability**: Protect school deployments from breaking changes.
3. **Repeatability**: Ensure installations and workflows can be reproduced in new schools.
4. **Quality**: Treat documentation and operational runbooks as deliverables.
5. **Modularity**: Encourage innovation without destabilizing baselines.

---

## 2. Roles and Responsibilities

### 2.1 Maintainer
The maintainer is responsible for:
- approving cross-repo direction,
- ensuring release hygiene,
- and maintaining the portal as a correct index.

### 2.2 Contributors
Contributors may:
- propose improvements via issues,
- submit pull requests (PRs),
- add new guides, diagrams, or tooling enhancements,
- and report field issues with reproduction steps.

### 2.3 Reviewers (Optional Role)
Reviewers (when designated) focus on:
- technical correctness of instructions,
- reproducibility and safety,
- and consistency with SatFinder documentation standards.

---

## 3. Repository Boundaries (Ownership Model)

### 3.1 satfinder-portal
Owns:
- The ecosystem index and canonical links
- Roadmap and governance documents
- Cross-repo standards (docs structure, release templates, compatibility matrix)

Does not own:
- Implementation code for components
- Hardware-specific deep details that belong in the build guide
- Tracker-specific calibration internals (belongs in beam tracker repo)

### 3.2 satfinder-node-build-guide
Owns:
- Full build instructions, wiring, mounting, and school deployment constraints
- Practical verification steps and troubleshooting runbooks
- “Known good” configurations for school environments

### 3.3 satfinder-pass-simulator
Owns:
- Simulation logic and user workflow
- Export formats and outputs produced by the simulator
- Installation from source and from Releases

### 3.4 satfinder-beam-tracker-lab
Owns:
- Calibration and tracking workflows
- Hardware integration guidance for motion/rotator control (within lab scope)
- Output logs, plots, and measurement methodology documentation

---

## 4. Decision-Making Process

### 4.1 Types of Changes
Changes are categorized to manage risk:

**Type A — Documentation-only, local repo scope**
- Fix typos, clarify steps, add screenshots
- Does not change workflows or outputs
Approval: normal PR review in the repo.

**Type B — Workflow changes within a repo**
- Modifies installation steps, configuration, or outputs
Approval: PR review, plus update to relevant docs in the same repo.

**Type C — Cross-repo impact**
- Affects interoperability, shared formats, or deployment assumptions
Process:
1) Open an issue in `satfinder-portal` describing the change and impact.
2) Link PRs from each affected repo to the portal issue.
3) Update portal index/roadmap/compatibility notes as needed.

**Type D — Breaking changes**
- Changes that may break existing deployments, scripts, or workflows
Process:
- Must be proposed in portal first
- Must include migration notes and fallback options
- Should use a major version bump if semantic versioning applies

### 4.2 Acceptance Criteria
A change is acceptable when:
- it is reproducible from scratch (clean environment),
- documentation is updated,
- and it does not introduce unnecessary complexity for school deployments.

---

## 5. Versioning Policy

### 5.1 Recommended Approach
- Use Semantic Versioning (SemVer) where applicable:
  - MAJOR: breaking changes
  - MINOR: backward-compatible features
  - PATCH: backward-compatible fixes

### 5.2 Documentation Versioning
Docs should reflect versions when needed:
- If instructions depend on versions, include explicit version tags.
- Keep “latest stable” instructions prominent, but preserve historical notes where necessary.

### 5.3 Compatibility Notes
The portal should maintain compatibility guidance such as:
- OS versions tested (e.g., Windows 11)
- Hardware compatibility notes (rotator/controller models)
- Network constraints assumptions for schools

---

## 6. Release Engineering and Distribution

### 6.1 Release Standards (Recommended)
For repos that publish binaries:
- Provide a clear release title and notes
- Include checksums (optional but recommended)
- Include installation steps from Releases in the README
- Include known limitations and troubleshooting pointers

### 6.2 Verification Checklist (Minimal)
Before a release is considered “stable”:
- Install from release artifact on a clean machine (or clean VM)
- Confirm core workflow works end-to-end
- Confirm README installation steps are accurate
- Update portal links if release naming changes

---

## 7. Documentation Standards (Ecosystem-Wide)

Each component repo should aim to include:

1. **Overview**
   - What the repo is for and who should use it
2. **Quick Start**
   - minimal steps to first success
3. **Installation**
   - from source
   - from Releases (if applicable)
4. **Configuration**
   - clear parameters, defaults, and examples
5. **Troubleshooting**
   - common failure modes and fixes
6. **Safety and Operational Notes**
   - power, mounting, and school constraints as relevant
7. **License and Attribution**

Portal should maintain:
- a cross-repo index,
- a recommended learning path,
- and an ecosystem troubleshooting index.

---

## 8. Issue Management Policy

### 8.1 What to Include in Issues
Issues should include:
- Environment: OS, hardware model, versions
- Steps to reproduce
- Expected vs actual behavior
- Logs/screenshots if possible (redact sensitive data)

### 8.2 Labels (Recommended)
- `bug`
- `documentation`
- `enhancement`
- `question`
- `deployment`
- `breaking-change`
- `cross-repo`

---

## 9. Security and Safety Considerations

SatFinder is commonly deployed in schools. Therefore:
- Avoid instructions that encourage bypassing institutional security controls.
- Prefer designs that do not require privileged access beyond what schools can reasonably provide.
- When network access is needed, document constraints and safe patterns (e.g., dedicated non-auth network segment).

---

## 10. Adding a New Repository to SatFinder

A new repository may be added when it:
- has a clear scope and does not duplicate an existing repo,
- includes basic README and licensing,
- and declares how it fits into the recommended learning/deployment path.

Process:
1) Open a portal issue: “Proposal: Add repo <name>”
2) Include scope, intended users, dependencies, and expected outputs
3) Once accepted, update:
   - portal README index
   - roadmap (if needed)
   - governance references (if needed)

---

## 11. Deprecation Policy

When a component or workflow becomes obsolete:
- Mark it as deprecated in its repo README
- Provide a replacement path or migration guidance
- Update portal to indicate:
  - deprecated status
  - last supported version
  - recommended alternative

---

## 12. Governance Maintenance

This governance document is maintained in `satfinder-portal` and should be updated when:
- new repos are added,
- cross-repo interfaces change,
- or deployment findings require new standards.

