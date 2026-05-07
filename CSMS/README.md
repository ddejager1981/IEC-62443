# IEC 62443-2-1 CSMS Mastery Training Programme

**Establishing a Cyber Security Management System for Industrial Automation and Control Systems**

> *A complete, self-directed learning programme — from first principles to autonomous CSMS operation — built directly from IEC 62443-2-1:2010 Edition 1.0.*

---

## Overview

This training programme covers everything needed to establish, operate, and sustain a Cyber Security Management System (CSMS) for an Industrial Automation and Control System (IACS) in accordance with **IEC 62443-2-1:2010**. It is structured as five progressive stages, each building on the last, and culminates in the learner being able to run a CSMS with little to no external oversight.

The programme is designed for practitioners — engineers, security professionals, and operations personnel — who need to move beyond awareness into actual implementation. Every stage includes practical worked examples drawn from a consistent case study: the **Sunrise Refinery**, a fictional 120,000 bbl/day refinery with a Triconex SIS, ageing DCS, unpatched HMIs, and a SCADA historian — a deliberately imperfect facility that mirrors real-world OT environments.

---

## Training Materials

| File | Description |
|---|---|
| `IEC62443_2_1_CSMS_Complete_Training.pptx` | 33-slide PowerPoint deck covering all 5 stages |
| `README.md` | This file — programme guide, learning objectives, and study notes |

The standard itself (`IEC 62443-2-1:2010`) is required reading alongside this programme. Key sections referenced throughout:

- **Clause 4** — Normative requirements (the SHALL and SHOULD obligations)
- **Annex A** — Guidance for developing each CSMS element (informative)
- **Annex B** — Process to develop a CSMS step-by-step (informative)
- **Annex C** — Mapping to ISO/IEC 27001 (informative)

---

## Programme Structure

```
Stage 1  →  Stage 2  →  Stage 3  →  Stage 4  →  Stage 5
Foundations  Risk       Policy &    Implementation  Monitoring
             Analysis   Controls                    & Mastery
Weeks 1–4   Weeks 5–10  Weeks 11–20  Weeks 21–32   Weeks 33–52+
```

Total estimated duration: **52 weeks** for a practitioner building a CSMS in parallel with their role. This can be compressed for those in a dedicated programme.

---

## Stage 1 — Foundations

**Standard references:** §0 Introduction · §1 Scope · §2 Normative references · §3 Terms and definitions · §4.1 Overview · Annex B §B.1–B.3

**Duration:** Weeks 1–4

### What You Will Learn

- Why IACS security is fundamentally different from IT security — and why the same controls can be lethal in an OT context
- What a CSMS is (a management system, not a technology product) and what it is not
- The three-category architecture that organises every element of the standard:
  - **Category 1:** Risk Analysis
  - **Category 2:** Addressing Risk with the CSMS
  - **Category 3:** Monitoring and Improving the CSMS
- The critical distinction between **SHALL** (mandatory) and **SHOULD** (strongly recommended) — the most important reading skill in this standard
- The six-step CSMS development process from Annex B, and why the sequence matters
- Core terminology: asset, risk, security zone, target security level (SL-T), conformance, HSE

### Key Concepts

**IACS vs IT Security — The Non-Negotiable Differences**

| Dimension | IT | IACS / OT |
|---|---|---|
| Primary security goal | Confidentiality | Safety & Availability |
| Patching cadence | Monthly cycles acceptable | Vendor-approved; often annual |
| Acceptable downtime | Minutes — tolerable | Unacceptable; potential HSE risk |
| Account lockout | Safe and standard | Can prevent operator response during emergency |
| System lifecycle | 3–5 years | 20–30+ years (PLCs from 1995 still in service) |
| Vendor dependency | Low | High — firmware-specific |

> **The tutor's warning:** Account lockout after failed logins is a textbook IT control. In OT, locking a valid operator out of a HMI during a process emergency can be catastrophic. Your CSMS must never create HSE risk while reducing cyber risk. (§4.3.3.6 Rationale)

**The Annex B Sequence — Honour It**

Annex B, Figure B.1 defines six activities in order:

1. Initiate CSMS Programme
2. High-Level Risk Assessment
3. Establish Policy, Organisation and Awareness
4. Detailed Risk Assessment
5. Select and Implement Countermeasures
6. Maintain the CSMS

The most common failure mode is skipping to Step 4 (detailed vulnerability assessment) before establishing the high-level risk context. Technical findings presented without a risk narrative produce apathetic management responses.

### Stage 1 Completion Gate

You are ready to proceed when you can:
- Draw the three-category CSMS architecture from memory and name all element groups
- Explain the SHALL/SHOULD distinction and give an example of each from Clause 4
- Describe what a CSMS is to a non-technical stakeholder in under two minutes
- Explain why the Annex B sequence exists and what goes wrong when it is violated

---

## Stage 2 — Risk Analysis

**Standard references:** §4.2 · Annex A §A.2 · Annex B §B.3–B.4 · Tables A.1–A.6

**Duration:** Weeks 5–10

### What You Will Learn

- How to build and present a business rationale that secures management commitment (§4.2.2)
- How to select, document, and justify a risk assessment methodology (§4.2.3.1 SHALL)
- How to construct a likelihood scale (Table A.1), consequence scale (Table A.2), and risk matrix (Table A.3)
- How to conduct a high-level system risk assessment followed by a detailed vulnerability assessment
- How to build and maintain a risk register in the format of Tables A.5 and A.6
- How to identify and document reassessment triggers (§4.2.3.10 SHALL)
- How to integrate physical, HSE, and cyber security risk results into a unified picture (§4.2.3.11)

### Practical: Sunrise Refinery Risk Register Extract

The following assets were assessed during the Sunrise Refinery high-level risk assessment:

| Asset | Threat Scenario | Likelihood | Consequence | Risk Level | Required Action |
|---|---|---|---|---|---|
| Unit 3 DCS (Triconex SIS) | LAN-connected SIS reachable from corporate network | 3 (Medium) | 4 (Catastrophic) | **CRITICAL** | Immediate network isolation — air gap |
| Control Room HMI | Unpatched Windows 7, no AV, USB ports enabled | 4 (High) | 3 (Critical) | **CRITICAL** | Patch/replace OS; disable USB ports |
| SCADA Historian | Accessible from DMZ without authentication | 3 (Medium) | 3 (Critical) | **HIGH** | Require authentication; VLAN isolation |
| Pipeline Compressor PLC | Default vendor password unchanged | 4 (High) | 2 (Marginal) | **HIGH** | Change all default passwords immediately |
| Field Instruments | No cyber interface — physical tamper risk only | 1 (Remote) | 3 (Critical) | **LOW** | Physical perimeter controls |

> **Risk Matrix:** Risk Level = Likelihood (1–4) × Consequence (1–4). Scores ≥ 9 = CRITICAL. Scores 6–8 = HIGH. Scores 3–5 = MEDIUM. Scores 1–2 = LOW.

### Reassessment Triggers (§4.2.3.10 SHALL)

Document these before you need them. Minimum triggers include:
- Major IACS change (new system, upgrade, network change)
- Security incident classified as High or Critical severity
- New ICS-CERT advisory affecting assets in your inventory (CVSS ≥ 8.0)
- Regulatory change imposing new requirements
- Elapsed time — minimum annual review of the full risk register

### Stage 2 Completion Gate

You are ready to proceed when you have produced:
- A management-signed business rationale document
- A documented risk assessment methodology selection with justification
- A completed IACS asset inventory with network diagrams
- A risk register with scored entries, prioritised risks, and assigned owners
- A documented reassessment trigger list with named responsible parties

---

## Stage 3 — Addressing Risk: Policy, Organisation and Countermeasures

**Standard references:** §4.3.1–§4.3.3 · Annex A §A.3.2–§A.3.3 · Annex B §B.5–§B.6

**Duration:** Weeks 11–20

### What You Will Learn

**Element Group 1: Security Policy, Organisation and Awareness**

- How to write a formal CSMS scope document that defines boundaries and goals (§4.3.2.2 SHALL)
- How to establish a cross-functional security governance structure (§4.3.2.3 SHALL)
- How to design and implement a role-based security training programme (§4.3.2.4 SHALL)
- How to develop business continuity plans with tested backup and restore procedures (§4.3.2.5 SHALL)
- How to build a policy hierarchy (corporate → IACS policies → procedures → records) (§4.3.2.6 SHALL)

**Element Group 2: Selected Security Countermeasures**

- **Personnel Security (§4.3.3.2):** Screening criteria, employment terms, segregation of duties
- **Physical and Environmental Security (§4.3.3.3):** Perimeters, entry controls, environmental protection
- **Network Segmentation (§4.3.3.4):** Zone design, barrier devices, traffic whitelisting
- **Access Control — Account Administration (§4.3.3.5):** Account lifecycle, default passwords, privilege review
- **Access Control — Authentication (§4.3.3.6):** Authentication strategy, remote access policy, OT-specific considerations
- **Access Control — Authorization (§4.3.3.7):** Role-based access, safety implications, multiple authorization methods

### Practical: Sunrise Refinery Zone Architecture

```
CORPORATE ZONE (Level 4)
  ERP, Email, SharePoint | Risk: Medium | SL-T: 1
          ↓
    [ FIREWALL / DMZ ]
          ↓
DMZ — SUPERVISORY ZONE (Level 3)
  Historian, Jump Server, Patch Server | Risk: High | SL-T: 2
          ↓
    [ FIREWALL — OWF rule set, whitelist only ]
          ↓
CONTROL ZONE (Level 2) — CRITICAL
  DCS, HMIs, PLC Network | Risk: CRITICAL | SL-T: 2–3
          ↓
    [ AIR GAP — NO NETWORK CONNECTION ]
          ↓
SAFETY ZONE (Level 1)
  Triconex SIS Unit 3 | Physical access only
```

**Zone design rules applied:**
- Traffic permitted downward only — no unsolicited inbound from corporate to control zone
- All barrier devices configured on whitelist principle (deny all, permit by exception)
- Vendor remote access via Jump Server in DMZ — never direct connection to control zone
- Unit 3 SIS physically air-gapped after risk assessment identified critical corporate LAN exposure
- Wireless prohibited in control zone; any exception requires documented risk assessment approval

### Policy Hierarchy

A CSMS policy suite is structured in four levels:

1. **Level 1 — Corporate Security Policy:** High-level management commitment. Sets risk tolerance. Signed by Plant Manager or equivalent. Typically 1–2 pages.
2. **Level 2 — IACS Cyber Security Policies:** Topic-specific policies covering access control, change management, incident response, patch management, etc. 5–15 pages each.
3. **Level 3 — Procedures and Work Instructions:** Step-by-step operational guidance. Written for operators and engineers to follow directly.
4. **Level 4 — Records and Evidence:** Completed forms, audit logs, training records, incident reports. These prove compliance.

> **Critical requirement (§4.3.2.6.8 SHALL):** Senior leadership SHALL demonstrate commitment to cyber security by visibly endorsing the policies. A policy without a management signature is not a CSMS policy.

### Stage 3 Completion Gate

You are ready to proceed when you have produced:
- A formal, management-approved CSMS scope document
- An organisational chart with security roles and responsibilities defined
- A training programme with completion records for all in-scope personnel
- A management-endorsed policy suite (minimum: access control, change management, incident response, patch management)
- An approved network segmentation architecture with implemented zone boundaries
- A business continuity plan with at least one documented backup restoration test

---

## Stage 4 — Implementation

**Standard references:** §4.3.4 · Annex A §A.3.4 · Annex B §B.7

**Duration:** Weeks 21–32

### What You Will Learn

- How to build a change management system with enforced separation of duties (§4.3.4.3.2 SHALL)
- How to assess the cyber security and HSE risk of every proposed IACS change (§4.3.4.3.3 SHALL)
- How to develop an OT-specific patch management procedure that evaluates risk of both applying and not applying a patch (§4.3.4.3.7 SHALL)
- How to establish an antivirus and malware management procedure appropriate for OT systems (§4.3.4.3.8 SHALL)
- How to create and test a backup and restoration procedure (§4.3.4.3.9 SHALL)
- How to classify all CSMS information assets and manage their lifecycle (§4.3.4.4 SHALL)
- How to build a three-phase incident response plan and test it through drills (§4.3.4.5 SHALL)

### Practical: OT Change Management Workflow

The standard requires separation of duties — the person who requests a change cannot be the same person who approves it, and in high-consequence environments, cannot be the same person who implements it.

```
Requester → OT Security Advisor → Change Advisory Board (CAB)
                                          ↓
                              Approve / Reject
                                          ↓
                                   OT Engineer
                              (NOT the requester)
                                          ↓
                              Test in Staging Env.
                                          ↓
                              Independent Verifier
                                          ↓
                              CAB: Approve for Production
                                          ↓
                              OT Engineer: Deploy + Record
```

> **§4.3.4.3.3 SHALL:** All proposed changes to IACS must be reviewed for HSE and cyber security risk impact by individuals technically knowledgeable about both the industrial operation and the IACS system. Include process safety engineers in your Change Advisory Board.

### Practical: OT Patch Management Decision Framework

When a new vulnerability is published, the standard (Annex A §A.3.4.3.7) requires a structured assessment:

1. **Identify** — Subscribe to ICS-CERT and vendor security advisories. Receive alert.
2. **Assess Relevance** — Is your firmware version affected? Is the asset in scope? Document findings.
3. **Risk If Applied** — Does the patch require a restart? Is there production impact? When is the next maintenance window?
4. **Risk If Not Applied** — What is the CVSS score? Is the asset network-accessible? What compensating controls can be applied in the interim?
5. **Test → Deploy** — Deploy to an identical staging system for minimum 72 hours. Test all control functions. Obtain vendor sign-off where required. Deploy during planned outage.

> **Non-negotiable baseline (Annex A §A.3.4.3.5.6):** Never deploy a patch to an OT production system without first testing in a separate staging environment. Never reuse the IT monthly patch calendar for OT systems.

### Practical: Incident Response — The Three Phases

**Phase 1 — Plan (before any incident):**
- Write the incident response plan (IRP) naming responsible personnel by role, not name
- Define incident categories with specific response procedures for each type
- Establish the reporting procedure for unusual activities
- Distribute to all appropriate teams: Operations, IT, HSE, Management, Legal
- Test with regular tabletop drills and document debrief findings

**Phase 2 — Respond (during an incident):**
- Detect, classify, and activate the IRP
- Contain: isolate affected system from non-essential network connections
- Preserve forensic evidence where possible — but note the pre-planned priority decision below
- Document everything in real time (§4.3.4.5.8 SHALL)
- Communicate to all appropriate parties promptly (§4.3.4.5.9)

**Phase 3 — Recover (after containment):**
- Restore from validated, tested backups
- Run full system tests before returning to production
- Conduct root cause analysis and document lessons learned
- Feed findings back into the risk register and CSMS policies
- Communicate incident summary to management (§4.3.4.5.10 SHALL)

> **The forensics vs. production tension:** For critical IACS systems, reformatting and restoring from backup to get production running will destroy forensic data. Decide which takes priority for each system *before* an incident occurs, and document it in the IRP. This is an explicit concern noted in Annex A §A.3.4.5.3.

### Information Classification Scheme

All CSMS information assets must be classified (§4.3.4.4.3 SHALL):

| Level | Examples | Handling |
|---|---|---|
| **RESTRICTED** | Vulnerability assessment results, detailed network diagrams, risk register, IRP with contact names | CSMS team only; encrypted storage; no unencrypted email; physical copies shredded |
| **CONFIDENTIAL** | IACS inventory, incident investigation reports, audit findings, patch schedule | Internal staff; password-protected files; access logged |
| **INTERNAL** | General security awareness materials, emergency contact lists, approved vendor lists | All employees; standard access controls |
| **PUBLIC** | General company information, public regulatory filings | No restrictions |

### Stage 4 Completion Gate

You are ready to proceed when you have:
- A change management system operating with documented separation of duties and an evidence trail for all changes
- A patch management procedure with at least one documented example of the 5-step decision framework applied
- An antivirus/malware procedure appropriate for your OT environment (vendor-coordinated)
- A backup and restoration procedure with documented successful restoration test
- An information classification scheme with all CSMS assets classified
- A written, distributed, and management-signed incident response plan
- At least one tabletop incident response drill completed with a documented debrief

---

## Stage 5 — Monitoring and Mastery

**Standard references:** §4.4 · Annex A §A.4 · Annex B §B.8

**Duration:** Weeks 33–52 (then ongoing)

### What You Will Learn

- How to design and run a conformance audit programme (§4.4.2 SHALL)
- How to define KPIs and performance metrics that make the CSMS self-monitoring (Annex A §A.4.2.3)
- How to distinguish scheduled vs. unscheduled audit activities and when each applies
- How to implement the five-step CSMS change management process (Annex A §A.4.3.5)
- How to establish review triggers and thresholds that force CSMS reviews without external prompting (§4.4.3.3 SHOULD)
- How to identify and implement corrective and preventive actions (§4.4.3.4 SHALL)
- How to monitor applicable legislation and regulatory changes (§4.4.3.7 SHALL)

### The Hardest Stage

Annex B §B.8 is explicit: organisations consistently report the "Maintain the CSMS" activity as the most difficult. Initial enthusiasm fades. Other priorities emerge. The CSMS that exists on paper but is not followed provides exactly zero risk reduction.

> **§4.4.2 Rationale:** *"Irrespective of the quality of a CSMS, if it is not used, it does not add any value to the organisation and does not help reduce risk."*

The solution is building governance structures that make the CSMS self-enforcing: triggers that create automatic review obligations, KPIs that surface problems before they become gaps, and a documented change process that updates the CSMS without requiring someone to remember to do it.

### Audit Programme Design

Four audit types are recommended:

| Audit Type | Frequency | Scope |
|---|---|---|
| Spot Check | Quarterly | Account review, default passwords, terminated user cleanup |
| Technical Audit | Bi-annual | Firewall rules vs. whitelist, patch status, AV signatures, backup test |
| Full CSMS Audit | Annual | All 19 requirement tables from Clause 4 against documented policies |
| Triggered Audit | As required | Any element affected by the triggering event (incident, change, regulatory update) |

**§4.4.2.5 SHALL:** Define what non-conformance means and document the punitive measures. A CSMS without consequences for non-conformance will not be followed.

### KPI Dashboard

The standard (Annex A §A.4.2.3) defines a seven-step metrics programme. Recommended KPIs:

| KPI | Target | Reporting |
|---|---|---|
| Patch Compliance Rate (% applied within SLA) | ≥ 95% | Quarterly |
| Open Audit Non-Conformances | < 5 | Quarterly |
| Account Review Completion Rate | 100% | Quarterly |
| Incident Drill Frequency | ≥ 4/year | Annual |
| Mean Time to Patch (Critical Vulnerabilities) | ≤ 30 days | Monthly |
| Staff Training Completion Rate (mandatory modules) | 100% | Quarterly |

> **Threshold rule:** The same KPI below target for two consecutive reporting periods indicates a systemic problem requiring root cause analysis — not a one-off response.

### CSMS Review Triggers (§4.4.3.3 SHOULD)

Document your triggers before you need them:

| Trigger | Threshold | Required Action |
|---|---|---|
| Security Incident | Any incident classified High or Critical | Full CSMS review within 30 days |
| Regulatory Change | New or amended OT cyber security regulation | Compliance gap analysis within 60 days |
| Major IACS Change | Addition, replacement, or major upgrade of any SL-T ≥ 2 asset | Zone-specific risk reassessment before commissioning |
| KPI Consecutive Failure | Same KPI below target for 2 periods | Root cause analysis + corrective action plan within 30 days |
| Industry Threat Alert | ICS-CERT advisory with CVSS ≥ 8.0 affecting inventory assets | Immediate technical review + compensating controls if patch unavailable |
| Elapsed Time | 12 months since last full CSMS review | Annual full CSMS review per audit programme |

### The Five-Step CSMS Change Management Process (Annex A §A.4.3.5)

1. **Define the current CSMS** — Document all policies, assets, and procedures. All stakeholders must understand the baseline before any change is proposed.
2. **Identify gaps and weaknesses** — Review for compliance and effectiveness. Consult audit findings, industry advisories, and the standard.
3. **Propose and evaluate changes** — Document changes concisely. Present to stakeholders. Evaluate for unforeseen side effects. Validate new technology before incorporating.
4. **Implement changes** — Follow company procedures. Obtain written approval. For technical changes: special attention to testing, validation, and vendor involvement.
5. **Monitor performance** — With the revised CSMS in place, monitor and evaluate. Review regularly and whenever further changes occur.

### Stage 5 Completion Gate — Mastery

You have achieved mastery when:
- [ ] KPIs run automatically and are reported to management quarterly
- [ ] Audit findings feed directly into the next CSMS update cycle without manual prompting
- [ ] All in-scope personnel know their CSMS roles without being reminded
- [ ] At least one full incident response drill has been completed and debriefed
- [ ] The risk assessment has been repeated at least once (triggered by change or elapsed time)
- [ ] At least one non-conformance has been identified, documented, and formally resolved
- [ ] The CSMS has been updated at least once based on audit findings, an incident, or a trigger event
- [ ] Applicable legislation is monitored and any new requirements are assessed within 60 days
- [ ] You can present an evidence package to an external auditor that demonstrates the CSMS has been actively maintained through at least one full review cycle

---

## Three Levels of CSMS Maturity

| Level | Description | Evidence |
|---|---|---|
| **Compliant** | All SHALL requirements documented, approved, and implemented. An external auditor would find no major gaps. | Policy suite exists. Risk register exists. Controls implemented. Training records. |
| **Effective** | The CSMS demonstrably reduces risk. Incidents are detected, responded to, and learned from. KPIs show improving trend. | Incident reports with lessons learned. Closing KPI gaps. Audit NCs decreasing over time. |
| **Autonomous** | The CSMS finds its own weaknesses through triggers and audits, updates itself through the five-step process, and requires no external prompting. The CSMS is institutionalised. | Self-triggered reviews. CSMS updated without prompting. Management reports generated automatically. |

---

## Quick Reference — Critical SHALL Requirements

The following are mandatory requirements from Clause 4. Non-compliance constitutes a gap against the standard.

### Risk Analysis (§4.2)
- `4.2.3.1` — Select and document a risk assessment methodology
- `4.2.3.3` — Conduct a high-level system risk assessment
- `4.2.3.4` — Identify and document all IACS in scope
- `4.2.3.5` — Develop network diagrams for each IACS
- `4.2.3.6` — Develop prioritisation criteria and assign risk priority to each IACS
- `4.2.3.7` — Perform a detailed vulnerability assessment on prioritised systems
- `4.2.3.9` — Conduct a detailed risk assessment using the selected methodology
- `4.2.3.10` — Identify and document reassessment triggers
- `4.2.3.12` — Conduct risk assessments through all lifecycle stages
- `4.2.3.13` — Document both the methodology and the results

### Security Policy, Organisation and Awareness (§4.3.2)
- `4.3.2.2.1` — Develop a formal written CSMS scope
- `4.3.2.3.1` — Obtain senior management support
- `4.3.2.3.2` — Establish a cross-functional security stakeholder network
- `4.3.2.3.3` — Define all organisational responsibilities for cyber security
- `4.3.2.4.1` — Design and implement a cyber security training programme
- `4.3.2.4.2` — All personnel SHALL receive procedure and security training
- `4.3.2.4.5` — Revise the training programme as required
- `4.3.2.5.3` — Develop and implement continuity plans
- `4.3.2.5.6` — Create backup and restore procedures
- `4.3.2.5.7` — Test and update the business continuity plan regularly
- `4.3.2.6.1` — Develop high-level cyber security policies approved by management
- `4.3.2.6.2` — Develop approved cyber security procedures
- `4.3.2.6.4` — Policies and procedures SHALL include compliance requirements
- `4.3.2.6.5` — Determine and document risk tolerance
- `4.3.2.6.6` — Communicate policies and procedures to all appropriate personnel
- `4.3.2.6.7` — Review and update policies and procedures regularly
- `4.3.2.6.8` — Senior leadership SHALL endorse cyber security policies

### Selected Security Countermeasures (§4.3.3)
- `4.3.3.2.1` — Establish a personnel security policy
- `4.3.3.2.2` — Screen all personnel with IACS access (including contractors)
- `4.3.3.2.5` — Document and communicate security expectations and responsibilities
- `4.3.3.2.6` — State cyber security terms and conditions of employment clearly
- `4.3.3.3.1` — Establish complementary physical and cyber security policies
- `4.3.3.3.2` — Establish physical security perimeters
- `4.3.3.3.3` — Provide entry controls at each barrier
- `4.3.3.3.4` — Protect assets against environmental damage
- `4.3.3.4.1` — Develop a zone-based network segmentation architecture
- `4.3.3.4.2` — Isolate high-risk IACS using barrier devices
- `4.3.3.4.3` — Barrier devices SHALL block all non-essential communications
- `4.3.3.5.3` — Access accounts granted/changed/removed by authorised manager only
- `4.3.3.5.4` — Record all access accounts with permissions
- `4.3.3.5.5` — Suspend or remove unneeded accounts immediately
- `4.3.3.5.7` — Change default passwords before putting IACS into service
- `4.3.3.6.1` — Develop an authentication strategy
- `4.3.3.6.2` — Authenticate all users before system use
- `4.3.3.6.3` — Require strong authentication for all admin and config accounts
- `4.3.3.6.5` — Authenticate all remote users at appropriate strength
- `4.3.3.6.6` — Develop a remote login and connection policy
- `4.3.3.7.1` — Define an authorization security policy with role-based rules
- `4.3.3.7.2` — Establish logical and physical permission methods

### Implementation (§4.3.4)
- `4.3.4.2.1` — Adopt a risk management framework governing IACS device selection and countermeasures
- `4.3.4.3.1` — Define security functions and capabilities for each new IACS component
- `4.3.4.3.2` — Develop and implement a change management system with separation of duties
- `4.3.4.3.3` — Assess all proposed changes for HSE and cyber security risk
- `4.3.4.3.4` — New systems must meet the security policies of the zone they enter
- `4.3.4.3.6` — Review and maintain operations and change management policies
- `4.3.4.3.7` — Establish, document, and follow a patch management procedure
- `4.3.4.3.8` — Establish, document, and follow an antivirus/malware management procedure
- `4.3.4.3.9` — Establish a backup and restoration procedure; verify by testing
- `4.3.4.4.1` — Develop a lifecycle document management process for IACS information
- `4.3.4.4.2` — Define information classification levels
- `4.3.4.4.3` — Classify all CSMS logical assets
- `4.3.4.5.1` — Implement an incident response plan naming responsible personnel
- `4.3.4.5.2` — Communicate the IRP to all appropriate organisations
- `4.3.4.5.6` — Promptly respond to identified incidents per established procedures
- `4.3.4.5.8` — Document the details of all identified incidents
- `4.3.4.5.10` — Address and correct issues discovered through incidents

### Monitoring and Improving (§4.4)
- `4.4.2.1` — Specify the audit programme methodology
- `4.4.2.2` — Conduct periodic IACS audits validating policy performance
- `4.4.2.4` — Establish a document audit trail
- `4.4.2.5` — Define what non-conformance means and document punitive measures
- `4.4.3.1` — Assign an organisation to manage and coordinate CSMS changes
- `4.4.3.4` — Identify and implement corrective and preventive actions
- `4.4.3.7` — Identify applicable and changing legislation relevant to cyber security

---

## Frequently Asked Questions

**Q: Our organisation already has an ISO/IEC 27001 ISMS. Do we need a separate CSMS?**

Not necessarily a separate system, but a significant extension. Annex C maps every requirement in this standard to its ISO/IEC 27001 equivalent. The gaps are primarily around OT-specific concerns: HSE integration, real-time availability requirements, long asset lifecycles, and vendor-specific constraints. Review Table C.1 to identify what your existing ISMS already covers and where IACS-specific additions are needed.

**Q: How do we handle legacy systems that cannot support modern authentication?**

The standard explicitly accommodates this. Physical authentication measures (locked rooms, access-controlled areas) can serve as compensating controls for electronic authentication limitations on legacy systems (§4.3.3.6 Description). Document the compensating control in your risk register with the justification, and review it at each reassessment cycle.

**Q: We are a small organisation. Does the full CSMS apply to us?**

Yes, but proportionally. §4.1 notes that while the CSMS may be more formalised in a large company, similar activities must be conducted in smaller organisations, albeit less formally. The standard is explicit that it applies regardless of organisation size. The scope document (§4.3.2.2) is where you define the boundaries — a smaller organisation may have a narrower scope, but the activities within that scope are still required.

**Q: What is the difference between a security zone and a network segment?**

A security zone (§3.1) is defined by shared security requirements and a common target security level — it is a logical concept. A network segment is a technical implementation. A single zone may span multiple network segments, and a single network segment could theoretically contain multiple zones (though this should be avoided). Design zones first based on risk and SL-T, then implement network segmentation to enforce the zone boundaries.

**Q: How often must we re-run the risk assessment?**

There is no single mandated frequency. §4.2.3.10 (SHALL) requires you to identify your own reassessment triggers. The standard requires risk assessments through all lifecycle stages (§4.2.3.12 SHALL). Best practice is an annual lightweight review of the risk register, with a full reassessment triggered by any of the documented triggers: major change, security incident, regulatory change, or elapsed time threshold you have set.

---

## Case Study: Sunrise Refinery

All practical examples throughout this training use the **Sunrise Refinery** — a fictional process facility used consistently across all five stages. This provides a coherent narrative from initial risk assessment through to autonomous CSMS operation.

**Facility Profile:**
- Crude oil refinery, 120,000 barrels per day production capacity
- Process control: Triconex SIS (Safety Instrumented System) on Unit 3
- DCS across Units 1, 2, and 3
- SCADA historian server
- Control room HMIs running Windows 7 (unpatched)
- Pipeline compressor PLCs with unchanged default passwords
- All initially connected to the same network as corporate ERP

**Why this case study:** The Sunrise Refinery begins in a state that reflects real-world OT environments — systems that grew organically over decades, where IT and OT converged without a security framework, and where the most critical safety system (the SIS) was discovered to be reachable from the corporate LAN. The programme walks through transforming this environment into a fully compliant, effective, and eventually autonomous CSMS.

---

## References

- **IEC 62443-2-1:2010** — Industrial communication networks — Network and system security — Part 2-1: Establishing an industrial automation and control system security programme. Edition 1.0, November 2010.
- **IEC/TS 62443-1-1** — Industrial communication networks — Network and system security — Part 1-1: Terminology, concepts and models.
- **IEC/TR 62443-2-3** — Technical report on patch management for IACS (referenced in Annex A §A.3.4.3.7).
- **ISO/IEC 27001** — Information security management systems — Requirements. Mapped to IEC 62443-2-1 requirements in Annex C.
- **NIST SP 800-30** — Guide for Conducting Risk Assessments (compatible methodology for §4.2.3.1 compliance).
- **ICS-CERT** — Industrial Control Systems Cyber Emergency Response Team advisories. Subscribe for §4.2.3.10 trigger monitoring.

---

## Licence and Usage

This training programme was developed as a practical interpretation of IEC 62443-2-1:2010 for educational purposes. The standard itself is copyright IEC Geneva, Switzerland and must be obtained through authorised distributors.

All practical examples, the Sunrise Refinery case study, risk registers, zone architectures, and worked assessments contained in this programme are original educational materials.

---

*IEC 62443-2-1:2010 · Complete Training Programme · Stages 1–5 · Practical · Standards-Based · Autonomous CSMS Ready*
