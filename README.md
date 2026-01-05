# SatFinder Portal
![Logo](/docs/images/logo.png)

SatFinder is an education-oriented satellite and radio-communication initiative that brings hands-on telecom and space-technology learning into schools and field labs. This repository (**satfinder-portal**) serves as the **central index** to all SatFinder GitHub repositories, including build guides, simulators, and calibration/tracking laboratories.

## Scope and Purpose

This portal is designed to:
1. Provide a **single entry point** for instructors, students, and technical teams to locate SatFinder components.
2. Clarify the **roles and boundaries** of each repository to avoid duplication and confusion.
3. Offer a **recommended learning/deployment path** (from basic node setup → pass simulation → beam tracking and calibration).
4. Maintain lightweight **governance, roadmap, and documentation standards** for the SatFinder ecosystem.

> This repository contains minimal code by design. For implementations, please refer to the linked repositories below.

---

## Repository Index (Core Components)

### 1) SatFinder Pass Simulator
**Repository:** https://github.com/awatchar/satfinder-pass-simulator  
**Primary role:** Satellite pass visualization/simulation and operator training  
**Typical users:** Teachers, students, station operators  
**What you get:**
- A practical pass simulation workflow for classroom demonstrations
- Tools supporting operator understanding of pass dynamics, azimuth/elevation changes, and time-on-target

**Recommended when:**
- You are teaching the fundamentals of satellite passes
- You want a software-first approach before building hardware rigs

---

### 2) SatFinder Beam Tracker Lab
**Repository:** https://github.com/awatchar/satfinder-beam-tracker-lab  
**Primary role:** Tracking/calibration lab for beam pointing and motion control (e.g., rotators, lab calibration workflow)  
**Typical users:** Engineering teams, advanced student labs, integrators  
**What you get:**
- Beam/pointing workflow suitable for controlled experiments
- Calibration concepts (e.g., 90/180/270/360 alignment), and practical integration patterns

**Recommended when:**
- You have motion hardware and need a structured calibration/tracking workflow
- You are validating pointing accuracy and repeatability

---

### 3) SatFinder Node Build Guide
**Repository:** https://github.com/awatchar/satfinder-node-build-guide  
**Primary role:** Hardware build and deployment guide for SatFinder school nodes  
**Typical users:** School deployment teams, instructors, field technicians  
**What you get:**
- Step-by-step build guidance
- Practical deployment considerations and checklists for school environments

**Recommended when:**
- You are building or deploying a SatFinder node in the real world
- You need reliable, repeatable installation guidance

---

## Recommended Learning / Deployment Path

The SatFinder ecosystem is easiest to adopt using a staged approach:

1. **Start with the Node Build Guide**  
   Build the baseline node and ensure your station can operate reliably in a school network environment.

2. **Use the Pass Simulator for instruction and pre-ops training**  
   Teach and validate operator understanding of passes before attempting physical tracking.

3. **Advance to the Beam Tracker Lab**  
   Apply calibration and tracking workflows for more advanced station capability (e.g., beam pointing accuracy).

This path supports both:
- **Pedagogical progression** (concepts → simulation → hardware control), and
- **Operational maturation** (build stability → predictability → precision).

---

## Documentation Standards (Portal Policy)

To keep the ecosystem coherent:
- Each component repository should maintain its own:
  - Installation (from source and from Releases)
  - Hardware/assembly notes (if applicable)
  - Troubleshooting section
- This portal maintains:
  - Cross-repo index
  - Roadmap and governance notes
  - High-level integration guidance

If you propose changes that affect multiple repositories, open an issue in this portal first, describing:
- The motivation
- Impacted repositories
- Expected outcomes and acceptance criteria

---

## Roadmap and Governance

- Roadmap: see `docs/ROADMAP.md` (recommended to create)
- Governance: see `docs/GOVERNANCE.md` (recommended to create)

---

## How to Contribute

Contributions are welcome in the form of:
- Portal improvements (better indexing, clearer learning paths)
- Cross-repo documentation alignment proposals
- Issues reporting broken links or outdated references

Please open an Issue with:
- A short, specific title
- Steps to reproduce (for problems)
- The repository affected
- Suggested resolution (if known)

---

## License

This portal repository is intended primarily for documentation and indexing.  
Choose a license consistent with your ecosystem policy (commonly MIT or Apache-2.0).

---

## Contact / Maintainers

Maintainer: @awatchar

If you are deploying SatFinder in a school, please include:
- Location (city/province)
- Node type and major hardware components
- Any constraints (network authentication, power stability, mounting limitations)

This helps align support and documentation improvements.
