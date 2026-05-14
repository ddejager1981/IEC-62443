# Risk Analysis and Assessment — Third Edition
## OT / ICS Cybersecurity University Textbook

> **Industry Contributor:** Daniel de Jager, Director – Cyber Security (Oceania–APAC), DP World  
> CISM · CSSLP · CIPP | BSc IT, BSc (Hons) CS | OWASP · AISA

---

## Project Status

| Part | Status | Chapters | Pages | Paragraphs |
|------|--------|----------|-------|------------|
| **Part I — Foundations** | ✅ COMPLETE | Ch 1–5 | ~188 | ~3,221 |
| **Part II — Risk Assessment Methodologies** | ✅ COMPLETE | Ch 6–10 | ~202 | ~3,625 |
| **Part III — CSMS Implementation and Monitoring** | 🔄 IN PROGRESS | Ch 11–13 | ~115 | ~2,259 |
| **Part IV — OT Security Assessment and Penetration Testing** | ✅ COMPLETE | Ch 14–16 | ~199 | ~4,629 |
| **TOTAL** | | **14 of 16 complete** | **~704 pages** | **~13,734 paragraphs** |

> ⚠️ **Part III is still in progress.** Chapters 14 and 15 of Part III
> (Countermeasure Implementation; Monitoring, Audit and Continuous Improvement)
> are the next chapters to be written. All other parts are complete.

---

## Textbook Overview

A complete university-level OT/ICS cybersecurity textbook aligned to:
- **IEC 62443-2-1:2010** — CSMS establishment and operation
- **IEC 62443-3-2:2020** — Security risk assessment for system design
- **IEC 62443-3-3:2013** — System security requirements and security levels
- **IEC 61511-1:2016** — Safety Instrumented Systems (process industry)
- **MITRE ATT&CK for ICS** — Adversary TTP reference framework
- **NIST SP 800-82** — Guide to ICS security
- **SANS ICS methodology** — Hands-on penetration testing approach (Part IV)

Two consistent case studies run across all chapters:
- **Sunrise Refinery** — 120,000 bbl/day; Honeywell Experion DCS; Triconex Tricon SIS; ControlLogix PLCs
- **Pacific Gateway Port** — 24 IGVs (40t, 15 km/h); Fleet Management Server; V2X 802.11p; MQTT

---

## Part I — Foundations of OT Security ✅

| Chapter | Title | File | Pages | Paragraphs |
|---------|-------|------|-------|------------|
| Ch 1 | Introduction to OT Security | `Chapter1_Introduction_OT_Security.docx` | 35 | 627 |
| Ch 2 | Hazard Identification | `Chapter2_Hazard_Identification.docx` | 40 | 754 |
| Ch 3 | Consequence Analysis | `Chapter3_Consequence_Analysis.docx` | 34 | 539 |
| Ch 4 | Likelihood and Probability Assessment | `Chapter4_Likelihood_Probability.docx` | 42 | 643 |
| Ch 5 | Risk Evaluation and Treatment | `Chapter5_Risk_Evaluation_Treatment.docx` | 37 | 658 |

**Key content:**
- OT/IT distinction; Purdue model; IEC 62443 zone architecture
- Hazard register methodology; COMAH/PSM alignment
- Five-stage physical consequence chain; CATASTROPHIC–NEGLIGIBLE framework
- Four-factor likelihood model; threat actor reference classes
- ALARP three-zone framework; Avoid/Reduce/Transfer/Retain treatment options
- Hierarchy of controls applied to OT security
- 17-field risk register template; CSMS lifecycle integration

---

## Part II — Risk Assessment Methodologies ✅

| Chapter | Title | File | Pages | Paragraphs |
|---------|-------|------|-------|------------|
| Ch 6 | ISA/IEC 62443 Risk Matrix | `Chapter6_IEC62443_Risk_Matrix.docx` | 39 | 766 |
| Ch 7 | HAZOP in OT Security | `Chapter7_HAZOP_Textbook.docx` | 40 | 712 |
| Ch 8 | STRIDE Threat Modelling | `Chapter8_STRIDE_OT.docx` | 46 | 768 |
| Ch 9 | LOPA in OT Security | `Chapter9_LOPA_OT.docx` | 39 | 776 |
| Ch 10 | Bow-Tie Analysis | `Chapter10_BowTie_OT.docx` | 38 | 603 |

**Key content:**
- IEC 62443 4×4 risk matrix; SL-T determination; FR1–FR7 mapping
- HAZOP guide word methodology applied to cyber scenarios
- STRIDE for OT: Spoofing/Tampering/Repudiation/Info Disclosure/DoS/Elevation of Privilege
- LOPA with IEC 61511 IPL requirements; SIL determination calculations
- Bow-Tie: prevention and recovery barriers; critical control identification
- All five methodologies applied to Sunrise Refinery and Pacific Gateway Port

---

## Part III — CSMS Implementation and Monitoring 🔄 IN PROGRESS

| Chapter | Title | File | Pages | Paragraphs | Status |
|---------|-------|------|-------|------------|--------|
| Ch 11 | Building the CSMS: Governance | `Chapter11_CSMS_Governance.docx` | 37 | 693 | ✅ Complete |
| Ch 12 | OT Assessment Mindset | `Chapter12_OT_Assessment_Mindset.docx` | 38 | 768 | ✅ Complete |
| Ch 13 | ICS Cyber Kill Chain & Scenario Development | `Chapter13_ICS_Kill_Chain.docx` | 40 | 838 | ✅ Complete |
| Ch 14 | Countermeasure Implementation | *(not yet written)* | — | — | 📋 **PENDING** |
| Ch 15 | Monitoring, Audit & Continuous Improvement | *(not yet written)* | — | — | 📋 **PENDING** |

### Ch 11 — Building the CSMS: Governance ✅
- IEC 62443-2-1 Category 2 SHALL requirements mapped to governance activities
- Four-tier OT security policy hierarchy; eight mandatory Tier 2 policies with full content
- RACI matrix (14 activities × 8 roles); CSMS Governance Committee structure
- Management commitment: genuine vs performative indicators (Table 11.2)
- Role-based training (6 audience groups); tabletop exercise design
- Sunrise Refinery worked example: Month 6 governance programme

### Ch 12 — OT Assessment Mindset ✅
- The Five Cardinal Rules of OT penetration testing (with operational rationale)
- Five assessment types: Health Check → Red Team (Table 12.1)
- Three-stage CJA identification process; CJA assessment target register
- Pre-engagement stakeholder matrix (7 stakeholders); scope definition document (9 sections)
- Emergency abort procedure template with signature block
- Pacific Gateway Port pre-engagement worked example

### Ch 13 — ICS Cyber Kill Chain and Attack Scenario Development ✅
- ICS Cyber Kill Chain: two-phase model (10 stages); Phase 1→2 transition analysis
- MITRE ATT&CK for ICS: 11 tactics; 10 high-value techniques with ATT&CK IDs
- ATT&CK Navigator heatmap exercise; threat actor profiles (7 groups including XENOTIME, ELECTRUM)
- Ukraine 2015 grid attack kill chain (10-stage table); TRITON/TRISIS callout
- Three-step scenario development process; complete scenario template (Table 13.6)
- Scenario SR-001: Sunrise Refinery VPN → SIS (10-stage kill chain table, stopping at TCP/1502)
- Scenario PGP-001: Pacific Gateway Port V2X rogue beacon (dual stopping points)
- Five-sector scenario library

### Ch 14 — Countermeasure Implementation 📋 PENDING
*Planned content:*
- Translating SL-T determinations into FR1–FR7 technical controls
- Network segmentation design (zones, conduits, industrial DMZ)
- Identity and access management for OT: MFA, PAM, RBAC
- OT-specific endpoint security and patch management
- Remote access security architecture
- OT network monitoring deployment (Dragos, Claroty, Nozomi)

### Ch 15 — Monitoring, Audit, and Continuous Improvement 📋 PENDING
*Planned content:*
- KPI framework for OT security
- OT security audit programme
- Management review process (IEC 62443-2-1 §4.4.3)
- Reassessment trigger framework
- CSMS maturity model and continuous improvement

---

## Part IV — OT Security Assessment and Penetration Testing ✅

> **SANS-style hands-on content.** Lab exercises with complete terminal command sequences,
> expected outputs, and safety warnings. Intermediate to advanced practitioner level.

| Chapter | Title | File | Pages | Paragraphs |
|---------|-------|------|-------|------------|
| Ch 14* | Passive Assessment Techniques | `Chapter14_Passive_Assessment.docx` | 39 | 989 |
| Ch 15* | Active Assessment Techniques and Tool Safety | `Chapter15_Active_Assessment.docx` | 41 | 1,189 |
| Ch 16* | Assessment Reporting and CSMS Integration | `Chapter16_Reporting_CSMS.docx` | 41 | 845 |

*\*Final chapter numbers will be resolved in editorial pass. Part IV also draws on  
Chapters 12 (OT Assessment Mindset) and 13 (ICS Kill Chain) catalogued under Part III.*

### Ch 14 (Part IV) — Passive Assessment Techniques ✅
- External OSINT: Shodan CLI, Censys, certificate transparency, LinkedIn profiling
- Lab 1: Shodan OT exposure assessment (complete CLI commands + analysis workflow)
- Lab 2: LinkedIn technology profiling
- On-site capture: tcpdump setup; Wireshark OT filters; Modbus FC reference table (FC01–FC2B)
- Lab 3: Wireshark OT protocol analysis (Modbus, DNP3 object groups, EtherNet/IP CIP codes)
- tshark asset communication matrix extraction; process value extraction from FC03
- Lab 4: Zeek with ICS scripts; zeek-cut analysis; passive asset inventory construction
- Architecture review: 7 discrepancy categories with severity ratings
- Lab 5: SIS independence verification (passive only); complete finding template SR-PA-001
- CVE cross-reference with nvdlib Python; CISA KEV correlation
- Sunrise Refinery passive findings: 3 CRITICAL (SIS reachable; CVE-2022-1159; undocumented FC06), 3 HIGH

### Ch 15 (Part IV) — Active Assessment Techniques and Tool Safety ✅
- Six-question OT Tooling Safety Evaluation Framework
- Tool safety table (17 tools): SAFE / CAUTION / DANGEROUS / EXPERT-ONLY
- Lab 1: Authorised PLC programme review (Studio 5000 read-only)
- Lab 2: Nmap OT-safe profile (mandatory parameter set: -T2 --max-rate 50 -Pn --version-intensity 0)
- Redpoint NSE scripts: enip-info, s7-info, modbus-discover with expected outputs
- Lab 3: mbtget Modbus read enumeration
- Lab 4: Zone boundary testing; conduit policy validation; segmentation results matrix
- OT default credential reference table (14 vendors including Rockwell, Siemens, Honeywell)
- Lab 5: Lateral movement simulation — VPN → engineering WS → SIS TCP/1502 (stopping point)
- Industrial protocol exploitation (lab only): pymodbus FC16 write, pycomm3 tag write, python-snap7
- Integrated finding register: 8 findings, kill chain mapping, evidence status

### Ch 16 (Part IV) — Assessment Reporting and CSMS Integration ✅
- Report structure: 6 sections with audience and purpose
- OT severity matrix: CVSS + physical consequence + CJA proximity (Table 16.2)
- Six-field finding structure quality standards; complete SR-001 worked finding
- Attack path narrative: 6 structural elements; full Sunrise Refinery SR-001 story
- Executive debrief (30 min); technical debrief (4-hour workshop agenda); operations debrief
- Remediation roadmap: IMMEDIATE/SHORT/MEDIUM tiers; $430K Sunrise Refinery plan
- Regulatory compliance mapping: NERC CIP-007, NIS2, COMAH, Australian CI Act, IEC 62443
- CSMS integration: risk register updates; treatment plan revision; monitoring calibration
- Assessment maturity model (Level 0–4); practitioner certification pathway (GICSP, GPEN, SANS ICS)

---

## Case Studies Reference

### Sunrise Refinery
| Attribute | Detail |
|-----------|--------|
| Throughput | 120,000 bbl/day |
| DCS | Honeywell Experion PKS |
| SIS | Triconex Tricon 3008 — Unit 3 ESD, SIL 2 |
| PLCs | 12× Rockwell ControlLogix 1756-L71S (firmware 32.011) |
| HMIs | 2× Windows 7 EOL workstations |
| Network | Flat — no industrial DMZ; SIS reachable from DCS engineering workstation |
| Remote access | Vendor VPN PSK only, unchanged 36 months, no MFA |
| Highest risk | R-002: VPN → SIS — Score 16 CRITICAL; TRITON attack pathway confirmed |
| Assessment findings | 4 CRITICAL, 4 HIGH confirmed findings; $430K remediation roadmap |

### Pacific Gateway Port
| Attribute | Detail |
|-----------|--------|
| Fleet | 24 IGVs — 40-tonne capacity, 15 km/h maximum speed |
| Systems | Fleet Management Server (FMS); Terminal Operating System (TOS) |
| Comms | V2X 802.11p — no authentication; MQTT — plaintext, no authentication |
| CJAs | IGV Navigation (Score 16); FMS (Score 12); MQTT Broker (Score 12) |
| Key finding | T-01: Rogue V2X beacon → IGV navigation manipulation → worker fatality |
| Assessment approach | Production: passive V2X capture; Lab: isolated test IGV demonstration |

---

## Chapter Standards

Every chapter contains:
- **8 Learning Outcomes** aligned to cognitive levels and assessment objectives
- **30 properly formatted references** (APA-style; standards; academic texts; practitioner sources)
- **13 review questions** across three cognitive levels:
  - Part A (Level 1): Knowledge and comprehension — 6 questions
  - Part B (Level 2): Application and analysis — 4 exercises
  - Part C (Level 3): Synthesis and critical evaluation — 2–3 extended questions
- **Complete glossary** of 10–15 key terms
- **Worked examples** using Sunrise Refinery and Pacific Gateway Port consistently

Part IV additionally provides:
- **SANS-style lab exercises** (5–8 per chapter) with complete terminal commands
- **Safety warning boxes** (red border) for all active techniques
- **Dark terminal code blocks** with syntax highlighting
- **Stopping point boxes** documenting CJA access demonstration boundaries
- **Finding documentation templates** (amber boxes)

---

## Regulatory and Standards Alignment

| Standard / Framework | Application in Textbook |
|---------------------|------------------------|
| IEC 62443-2-1:2010 | CSMS establishment; SHALL requirements throughout Parts I–III |
| IEC 62443-3-2:2020 | Risk assessment for system design; SL-T determination |
| IEC 62443-3-3:2013 | FR1–FR7 security requirements at SL 1–4 |
| IEC 61511-1:2016 | SIS independence §11.6; SIL determination; LOPA |
| ISO 31000:2018 | Risk management framework |
| ISO 45001:2018 | Hierarchy of controls |
| NIST SP 800-82 Rev.2 | ICS security guidance |
| NIST SP 800-115 | Security testing and assessment methodology |
| MITRE ATT&CK for ICS v14.0 | TTP reference for all assessment scenarios (Part IV) |
| NERC CIP (CIP-007-6) | Electric utility compliance mapping |
| NIS2 Directive (EU 2022/2555) | European CI compliance mapping |
| COMAH 1999 (UK) | Major hazard facility requirements |
| Australian CI Act 2018 | Port and CI security obligations |

---

## Technical Build Notes

- **Build tool:** Node.js with `docx` npm package
- **Validation:** `python3 validate.py [chapter].docx`
- **All outputs:** `/mnt/user-data/outputs/`
- **Build scripts:** `/home/claude/ch{N}_chapter/build_ch{N}.js`
- **Page size:** US Letter — 12240 × 15840 twips
- **Body font:** Times New Roman 12pt
- **Heading fonts:** Arial (H1: 16pt navy; H2: 14pt teal; H3: 12pt blue)

---

*Last updated: May 2026*  
*14 of 16 planned chapters complete — Part III Chapters 14 and 15 still to be written*