# Sentinel Systems — New Analyst Fact Sheet

Welcome to Sentinel Systems, the security operations team for **Ridgeview
Health**. This sheet covers the facts every new analyst gets on day one.
It is not a set of instructions. Deciding what Claude needs to know, and how
to phrase it, is your job.

---

## Ridgeview Health at a glance
- Regional, non-profit hospital network
- Ridgeview Medical Center (RMC): 420 beds, Level II trauma center
- Lakeside Community Hospital (LCH): 160 beds
- Pine Hollow Children's Hospital (PHC): 90 beds
- 14 outpatient clinics
- About 4,200 staff and about 1.1 million patient records

## Sentinel Systems
- Ridgeview's in-house security operations team, staffed 24/7
- 6 security analysts (2 per shift) and 1 SOC lead
- Every security alert is logged as a ticket in the Sentinel incident tracker

## Who's who
| Person | Role | What they handle |
|---|---|---|
| Maya Reyes | SOC Lead | Malware, intrusions, compromised accounts, any technical investigation |
| Daniel Okafor | Privacy & Compliance Officer | Anything that might expose patient information; decides whether something is a reportable breach |
| Helen Park | Chief Information Security Officer (CISO) | Final authority on security incidents; briefs executives and the board |
| Sam Whitfield | Clinical Engineering Manager | Medical devices: infusion pumps, imaging equipment |
| Linda Torres | Finance Systems Owner | FINANCE-SERVER-02 (billing, payroll, card payments) |
| IT Service Desk | — | Lost badges, password resets, laptops, routine account problems |

## Who reads Sentinel's work
- **Helen Park and Ridgeview executives** want business and patient impact,
  in plain language, in under a minute.
- **Clinical staff** (doctors, nurses, unit managers) are not technical. They
  need to know what to do and whether patient care is affected.
- **Maya Reyes and the IT engineers** want technical detail: systems,
  accounts, IP addresses, timestamps, what was already done.

## Key systems
| System | What it is | Criticality |
|---|---|---|
| EHR-DB-01 | ChartWell electronic health records (every patient record) | Tier 1 |
| PUMP-NET | Network for ~600 Aurex AX-300 infusion pumps | Tier 1 (life-critical) |
| PACS-01 | Medical imaging archive (X-ray, CT, MRI) | Tier 1 |
| WS-ER-* | Emergency department workstations | Tier 1 (clinical) |
| PORTAL-WEB | Patient portal on the internet (appointments, results, bills) | Tier 2 |
| FINANCE-SERVER-02 | Billing and payroll server; processes card payments | Tier 2 |
| VPN-GW | Remote access for staff | Tier 2 |
| MAIL-GW | Email security gateway | Tier 2 |
| BADGE-CTRL | Badge access for all buildings | Tier 3 |
| WS-LCH-*, WS-PHC-* | Clinical workstations at Lakeside and Pine Hollow (nursing stations, imaging rooms) | Tier 1 (clinical) |
| WS-ADMIN-* | Office workstations | Tier 3 |
| GUEST-WIFI | Patient and visitor Wi-Fi (separated from hospital systems) | Tier 4 |
| VULN-SCAN-01 | Ridgeview's own vulnerability scanner (10.20.5.15); runs every Tuesday 01:00–04:00 UTC | — |

What the tiers mean:
- **Tier 1:** if it fails, patient care stops or patients are at risk.
- **Tier 2:** patient data or money is at risk.
- **Tier 3:** business disruption.
- **Tier 4:** isolated, low impact.

## Ridgeview security policy: response times
| Severity | Must be acknowledged within |
|---|---|
| Critical | 15 minutes |
| High | 1 hour |
| Medium | 8 hours |
| Low | 3 business days |

## Hospital-specific policies
- **Patient safety comes first.** Clinical systems and medical devices are
  never taken offline without Clinical Engineering and the unit's nurse
  manager agreeing. Switching off a device can harm a patient more than the
  threat itself.
- **Privacy decisions belong to the Privacy & Compliance Officer.** Only
  Daniel Okafor decides whether an event is a reportable breach. Security
  analysts never contact patients.
- **Evidence is preserved.** A compromised machine is not wiped or rebuilt
  until the SOC Lead approves.
- **Medical device advisories** from vendors are handled by Clinical
  Engineering, who update devices one unit at a time.

## Regulations you will hear about
- **HIPAA (US health privacy law):** if patient information is exposed for
  **500 or more patients**, Ridgeview must report it to the U.S. Department of
  Health and Human Services (HHS) and the media within **60 days** of
  discovering it. Smaller breaches are logged and reported once a year.
  Affected patients must always be notified.
- **PCI DSS (card payment rules):** FINANCE-SERVER-02 processes card
  payments, so any suspected card-data exposure must reach the Finance
  Systems Owner the same day.
