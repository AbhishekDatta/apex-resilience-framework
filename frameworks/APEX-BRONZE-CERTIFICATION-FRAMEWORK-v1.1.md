# APEX BRONZE CERTIFICATION FRAMEWORK (v1.1)
**Non-Production Environments — Foundational Resilience**

> **Changelog from v1.0:** "API Gateway Profile" renamed to "Cascading Risk Profile" for clarity. Evaluation period updated to 6 months. Probation Period (PP) and PIP remain 3 months.

---

## FRAMEWORK OVERVIEW

| Attribute | Detail |
|---|---|
| **Target Environment** | Non-Production (Dev, Test, Staging) |
| **Philosophy** | Low barrier to entry — foundational resilience capabilities. Teams should be able to achieve Bronze without it becoming a burden alongside existing delivery commitments. |
| **Score Range** | 200–350 points out of 1000 (20%–35%) |
| **Prerequisite** | None — this is the entry point |
| **Scoring Dimensions** | **2-Dimensional**: Capability (50%) + Performance (50%) |
| **Evaluation Period** | 6 months |
| **Probation Period (PP)** | 3 months → Full Certification |
| **Performance Improvement Plan (PIP)** | 3 months |
| **Validity** | 12 months with annual re-certification |

> **Dimension Floor Rule:** A total score of 200–350 qualifies for Bronze territory, but both dimension floors must be met independently. This ensures the score reflects genuine, balanced capability — not strength in one area masking a critical gap in another. Think of it as passing each paper individually, not just on aggregate.
> - Capability Score ≥100 pts
> - Performance Score ≥100 pts
> Failing either floor = No Bronze Certification, regardless of total score.

---

## COMPLEXITY CLASSIFICATION (Prerequisite)

Before assessment, classify the application using the 8-Criteria Weighted Scoring System.

| Level | Score | Characteristics |
|---|---|---|
| **Simple** | 0–25 pts | 1–3 components, single team, Tier 3–5, low criticality |
| **Mid-Tier** | 26–50 pts | 4–10 components, 2–4 teams, Tier 2–3, moderate criticality |
| **Complex** | 51–80 pts | 11+ components, 5+ teams, Tier 0–1, mission-critical |

### 8-Criteria Weighted Scoring

| Criterion | Weight | Max Points |
|---|---|---|
| Number of Components | 2× | 10 |
| Tier Composition (Highest Tier Present) | 3× | 15 |
| Team Coordination (Number of Teams) | 1.5× | 7.5 |
| Outage Severity Impact | 3× | 15 |
| Data Complexity | 2× | 10 |
| External Dependencies | 1.5× | 7.5 |
| Transaction Volume / Scale | 2× | 10 |
| Geographic Distribution | 1× | 5 |
| **TOTAL** | | **80 pts** |

> **Rule:** If ANY component is Tier-0, the entire application scores maximum on Tier Composition (15 pts), automatically pushing toward Complex classification.

### How Tier Differentiation Works in APEX

APEX does not use tier multipliers to move the certification finish line. A Bronze application always needs 200–350 points regardless of its tier. Instead, tier differentiation is built into the journey through:

1. **Complexity Classification** — Tier 0 presence automatically pushes an app to Complex via the Tier Composition criterion (3× weight, 15 pts max) — the heaviest weighted criterion in the system
2. **Profile Weights** — Complex apps have category weights amplified for their risk profile. Framework admin can adjust weights with documented justification
3. **Performance Thresholds within Categories** — Complex apps face stricter expectations across chaos success rates, incident resolution times, and monitoring coverage
4. **Non-Negotiables** — Complex apps face more demanding hard gate requirements
5. **Incident Penalties** — Severity classification hits harder on complex/high-tier apps

> **One universal finish line. Differentiation happens in how demanding the journey is to get there.**

---

## APPLICATION PROFILE ASSIGNMENT

Assign a standardized profile with weight multipliers. Framework admin may override individual weights with documented justification.

| Profile | Key Weight Adjustments | Best Suited For |
|---|---|---|
| **High-Velocity** | Deployment Automation 2×, Chaos Testing 1.5×, IaC 1.5× | Frequent releases, breaking changes |
| **Stable Enterprise** | DR & BC 1.5×, Architecture 1.5×, Documentation 1.5× | Infrequent releases, stability-focused |
| **Data-Intensive** | Data Complexity 2×, Backup Strategy 1.5×, Monitoring 1.5× | Complex data flows, ETL pipelines |
| **Cascading Risk** | Dependency Management 2×, Circuit Breakers 1.5×, Availability 1.5× | High external/internal dependencies with cascading failure risk |
| **Standard** | All weights 1× | Balanced, default |

---

## BRONZE NON-NEGOTIABLES (Hard Gates)

**MUST PASS ALL 6 to qualify for Bronze.**

| # | Requirement | Simple | Mid-Tier | Complex |
|---|---|---|---|---|
| 1 | **DR Plan exists and tested in last 12 months** | Basic runbook, tested once | All services covered, tested | Tier-by-tier plan, tested |
| 2 | **RTO/RPO defined and documented** | Generic targets acceptable | Per-service targets | Per-tier targets |
| 3 | **Basic monitoring in place (infra + app)** | ≥50% coverage | ≥60% coverage | ≥50% across tiers |
| 4 | **Chaos tool installed and 1+ test executed** | Any chaos tool, 1 test | Platform setup, 2+ tests | Multi-tier capable, 3+ tests |
| 5 | **Dependencies documented** | List of dependencies | Dependency map | Tier-by-tier dependency map |
| 6 | **Owner identified** | Single owner | Per-service owners | Tier-specific owners |

> Failure of ANY non-negotiable = No Bronze Certification, regardless of score.

> **Note:** Incident process documentation, on-call coverage, deployment pipeline, and incident volume limits are **nice-to-haves** at Bronze — they are scored and contribute points but are not hard gates. These become mandatory at Silver.

---

## DIMENSION 1: CAPABILITY SCORE (500 points max)

### 1. DISASTER RECOVERY & BUSINESS CONTINUITY (90 pts)

#### 1.1 DR Plan Documentation (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 22–25 | Complete runbook, accessible, owner identified | All services covered, dependency map, detailed recovery steps | Comprehensive tier-by-tier runbook, cross-tier dependencies, recovery orchestration documented |
| 15–21 | Basic runbook exists, somewhat current | Most services covered, some gaps | Multiple tiers covered, minor gaps |
| 8–14 | Minimal documentation, outdated | Partial coverage only | Single tier or incomplete |
| 0–7 | No plan or extremely outdated | Missing critical services | Missing multiple tiers |

**Bronze Minimum: 15 pts**

#### 1.2 RTO/RPO Definition (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | RTO <8hrs, RPO <4hrs defined | RTO/RPO per service tier, critical path identified | RTO/RPO per tier (0/1/2/3), recovery priority sequence |
| 12–17 | Targets defined but generic | Some service breakdown, incomplete | Some tier differentiation |
| 6–11 | Vague targets only | Generic or inconsistent | No tier differentiation |
| 0–5 | Not defined | Missing | Missing |

**Bronze Minimum: 12 pts (Non-Negotiable #2)**

#### 1.3 Backup Strategy (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 22–25 | Daily automated backups, 7-day retention, monitored | All data stores covered, 14-day retention, backup monitoring | Tiered strategy (critical=daily, non-critical=weekly), 30-day retention, cross-tier dependencies |
| 15–21 | Automated backups, basic retention | Most stores covered, monitored | Tiered but incomplete |
| 8–14 | Manual or inconsistent | Partial coverage, not monitored | Inconsistent across tiers |
| 0–7 | No backups or ad-hoc | Major gaps | No strategy |

**Bronze Minimum: 18 pts (automated backups required)**

#### 1.4 DR Testing Frequency (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Tested within 6 months, documented results | Bi-annual tests, all critical services covered | Bi-annual with tier validation, critical path prioritized |
| 12–17 | Tested within 12 months | Annual test, good coverage | Annual test, most tiers |
| 6–11 | Tested 12–18 months ago | Incomplete coverage | Single tier only |
| 0–5 | >18 months or never | Never or >18 months | Never or incomplete |

**Bronze Minimum: 12 pts (Non-Negotiable #1 — tested within 12 months)**

---

### 2. CHAOS ENGINEERING & RESILIENCE TESTING (100 pts)

#### 2.1 Chaos Tool / Framework Setup (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Tool installed (Chaos Monkey, LitmusChaos, scripts), configured, documented | Platform configured for multi-service testing, blast radius controls | Enterprise platform with tier-aware capability, environment isolation |
| 20–26 | Tool installed, basic configuration | Platform installed, partial setup | Platform installed, single-tier focus |
| 12–19 | Tool identified, planning installation | Evaluating options | Evaluating options |
| 0–11 | No chaos capability | None | None |

**Bronze Minimum: 20 pts (Non-Negotiable #4 — tool must be installed)**

#### 2.2 Chaos Testing Coverage (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 30–35 | 2–3 scenarios tested (restart, latency, failure) | 3–4 scenarios covering critical services | 4–5 scenarios across multiple tiers, critical path validated |
| 20–29 | 1–2 scenarios tested | 2 scenarios tested | 2–3 scenarios, limited tier coverage |
| 10–19 | 1 scenario planned/tested | 1 scenario or planned | Single tier, 1–2 scenarios |
| 0–9 | No tests executed | None | None |

**Bronze Minimum: 10 pts (Non-Negotiable #4 — at least 1 test executed)**

#### 2.3 Game Day Participation (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 30–35 | Participated within 6 months, single team | Within 6 months, cross-functional team | Within 6 months, multi-tier scenario |
| 20–29 | Participated within 12 months | Within 12 months, cross-functional | Within 12 months, multi-tier |
| 10–19 | Participated 12–18 months ago | Within 18 months | Within 18 months |
| 0–9 | Never or >18 months | Never | Never |

**Bronze Target: 10+ pts (encouraged but not a hard gate at Bronze)**

---

### 3. INCIDENT MANAGEMENT & RESPONSE (110 pts)

#### 3.1 Incident Response Process Documentation (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Complete runbook for common issues, escalation defined, accessible | Service-specific runbooks, escalation matrix, severity definitions | Tier-specific runbooks, cross-tier escalation, incident command structure |
| 20–26 | Basic runbook exists, mostly current | Most services covered | Most tiers covered |
| 12–19 | Minimal runbook, outdated | Generic or incomplete | Generic or single tier |
| 0–11 | Undocumented or tribal knowledge | None or severely outdated | None |

**Bronze Target: 12+ pts (documentation encouraged — becomes mandatory at Silver)**

#### 3.2 On-Call Setup (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | 3+ person rotation, schedule published | Per-service rotations (3+ people), clear escalation | Tier-specific rotations, cross-tier escalation clear |
| 18–22 | 2-person rotation | 2-person rotation established | Basic tier coverage |
| 10–17 | 1 person identified, contact accessible | Single person per service | Unclear tier ownership |
| 0–9 | Ad-hoc or unclear | None | None |

**Bronze Target: 10+ pts (encouraged — becomes mandatory at Silver)**

#### 3.3 Incident Tracking & Logging (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Formal ticketing system (Jira, ServiceNow), severity tracked | All services tracked with severity, basic metrics | Tier-aware tracking, cross-component impact documented |
| 20–26 | Ticketing system, basic tracking | Most services tracked | Most tiers tracked |
| 12–19 | Informal tracking (spreadsheet) | Inconsistent tracking | Partial tier tracking |
| 0–11 | Email/Slack only or none | None or ad-hoc | None |

**Bronze Minimum: 12 pts (some formal tracking required)**

#### 3.4 Post-Incident Review Process (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | PIRs for all Sev 0–1, action items tracked to closure | PIRs for Sev 0–2, action tracking | Tier-specific PIRs, cross-tier learnings shared |
| 17–22 | PIRs for major incidents, basic tracking | PIRs for Sev 0–1, some tracking | PIRs conducted, limited sharing |
| 9–16 | Occasional PIRs, no tracking | Inconsistent | Inconsistent |
| 0–8 | No PIR process | None | None |

**Bronze Target: 9+ pts (encouraged for learning)**

---

### 4. OBSERVABILITY & DETECTION (90 pts)

#### 4.1 Monitoring Coverage (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 32–35 | Infra + app monitoring, 70%+ coverage, health checks | All services monitored, 70%+ coverage | Tier-specific monitoring, 60%+ coverage across tiers |
| 24–31 | Infra + app, 50–70% coverage | 60–70% coverage | 50–60% tier coverage |
| 15–23 | Basic infra + app, 50% coverage | 50–60% coverage | 40–50% tier coverage |
| 0–14 | Infrastructure only or <50% | <50% coverage | <40% coverage |

**Bronze Minimum: 15 pts (≥50% coverage — Non-Negotiable #3)**

#### 4.2 Logging (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Centralized logging, 14-day retention, searchable | All services centralized, 14-day retention | Centralized with tier tagging, correlation IDs, 30-day retention |
| 20–26 | Centralized, 7-day retention | Centralized, 7–14 days | Tier tagging, 14-day retention |
| 12–19 | Application logs captured, 7-day retention | Mostly centralized | Partial tier context |
| 0–11 | No structured logging or <7 days | Decentralized or minimal | Missing tier context |

**Bronze Minimum: 12 pts (basic centralized logging)**

#### 4.3 Alerting Setup (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | Alerts for service down, critical errors, actionable | All critical services, basic escalation | Tier-aware alerting, critical path prioritized |
| 17–22 | Basic alerts configured | Most services covered | Most tiers covered |
| 9–16 | Minimal alerts | Partial coverage | Partial tier coverage |
| 0–8 | No alerts | None | None |

**Bronze Minimum: 9 pts (basic alerting required)**

---

### 5. AUTOMATION & SELF-HEALING (55 pts)

#### 5.1 Infrastructure as Code (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | 50%+ IaC, version controlled, tested | 50%+ IaC, environment parity | 60%+ IaC across tiers, tier templates |
| 17–22 | 30–50% IaC, version controlled | 40–50% IaC | 50–60% IaC |
| 9–16 | 30% IaC minimum | 30–40% IaC | 40–50% IaC |
| 0–8 | <30% or manual | <30% | <40% |

**Bronze Minimum: 9 pts (≥30% IaC)**

#### 5.2 Deployment Automation (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Fully automated CI/CD, rollback tested and working | All services automated, rollback capability | Tier-aware pipelines, orchestrated deployments, rollback |
| 20–26 | Automated CI/CD, basic rollback | Most services automated | Most tiers automated |
| 12–19 | Semi-automated (build auto, deploy manual) | Semi-automated | Semi-automated coordination |
| 0–11 | Manual deployments | Manual | Manual |

**Bronze Target: 12+ pts (encouraged — becomes mandatory at Silver)**

---

### 6. ARCHITECTURE & DESIGN RESILIENCE (30 pts)

#### 6.1 Dependency Documentation (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 14–15 | Complete dependency list, visual map | Dependency map, upstream/downstream clear | Tier-by-tier map, critical path highlighted, cross-tier dependencies |
| 10–13 | Dependencies listed and documented | Map created, mostly current | Most tiers mapped |
| 6–9 | Basic list of dependencies | Partial mapping | Partial tier view |
| 0–5 | Undocumented or incomplete | Severely incomplete | Missing cross-tier view |

**Bronze Minimum: 6 pts (Non-Negotiable #5 — dependencies must be documented)**

#### 6.2 Environment Parity (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 14–15 | Non-prod mirrors 80%+ production architecture | Staging 75%+ production fidelity | Staging mirrors 70%+ production across tiers |
| 10–13 | 60–80% parity | 60–75% fidelity | 60–70% tier fidelity |
| 6–9 | 50–60% parity | 50–60% fidelity | 50–60% tier representation |
| 0–5 | <50% or no parity | <50% | Missing tier representation |

**Bronze Minimum: 6 pts (≥50% parity)**

---

### 7. CULTURE & ORGANIZATIONAL MATURITY (25 pts)

#### 7.1 Ownership & Accountability (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 14–15 | Clear owner, documented, contact accessible | Per-service owners, RACI documented | Tier-specific ownership, cross-tier coordination owner |
| 10–13 | Owner identified, mostly clear | Per-service owners identified | Tier owners identified |
| 6–9 | Owner identified but informal | Some ambiguity | Some fragmentation |
| 0–5 | Unclear ownership | Very unclear | Highly fragmented |

**Bronze Minimum: 6 pts (Non-Negotiable #6 — owner must be identified)**

#### 7.2 Documentation Quality (10 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 9–10 | README, architecture diagram, runbook accessible, current | Comprehensive per-service docs, version controlled | Tier-level docs, cross-tier integration docs, centralized |
| 6–8 | Basic docs exist, somewhat current | Adequate but some outdated | Most tiers documented |
| 3–5 | Minimal documentation | Inconsistent or scattered | Fragmented |
| 0–2 | No docs or severely outdated | None or extremely outdated | None |

**Bronze Minimum: 3 pts (basic documentation required)**

---

### CAPABILITY SCORE SUMMARY

| Category | Base Points |
|---|---|
| DR & Business Continuity | 90 pts |
| Chaos Engineering | 100 pts |
| Incident Management | 110 pts |
| Observability & Detection | 90 pts |
| Automation & Self-Healing | 55 pts |
| Architecture & Design | 30 pts |
| Culture & Org Maturity | 25 pts |
| **TOTAL** | **500 pts** |

*(Apply profile weights, then normalize proportionally if total exceeds 500)*

---

## DIMENSION 2: PERFORMANCE SCORE (500 points max)

> Performance in Bronze measures **execution quality in non-production environments** — how well the team runs chaos tests, game days, deployments, and manages non-prod incidents. Production metrics (MTTD, MTTR) are not applicable here.

---

### 1. CHAOS TESTING OUTCOMES (150 pts)

#### 1.1 Chaos Test Success Rate (80 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 72–80 | >80% tests pass, graceful recovery | >75% tests pass across services | >70% tests pass across tiers |
| 54–71 | 65–80% pass | 60–75% pass | 55–70% pass |
| 36–53 | 50–65% pass | 50–60% pass | 40–55% pass |
| 0–35 | <50% pass | <50% pass | <40% pass |

**Bronze Minimum: 36 pts**

#### 1.2 Blast Radius Containment (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | Failures isolated to single component, no cascading | Failures contained within service boundary, circuit breakers work | Failures contained within tier, no cross-tier cascade |
| 27–35 | Minimal cascade (1–2 components) | Limited cross-service impact (1–2 services) | Limited cross-tier impact (1 tier) |
| 18–26 | Moderate cascade | Multiple services affected | Multiple tiers affected |
| 0–17 | System-wide impact | Widespread cascade | System-wide cascade |

**Bronze Minimum: 18 pts**

#### 1.3 Recovery Time from Chaos Tests (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Recovery <5 minutes | Recovery <10 minutes | Recovery <15 minutes |
| 20–26 | 5–15 minutes | 10–20 minutes | 15–30 minutes |
| 12–19 | 15–30 minutes | 20–45 minutes | 30–60 minutes |
| 0–11 | >30 minutes | >45 minutes | >60 minutes |

**Bronze Minimum: 12 pts**

---

### 2. GAME DAY PERFORMANCE (120 pts)

#### 2.1 Scenario Completion Rate (50 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 45–50 | Completed all scenarios successfully | Completed 75%+ complex scenarios | Completed 70%+ multi-tier scenarios |
| 34–44 | Completed 75%+ scenarios | Completed 60–75% scenarios | Completed 55–70% scenarios |
| 22–33 | Completed 50–75% scenarios | Completed 50–60% scenarios | Completed 45–55% scenarios |
| 0–21 | <50% completion | <50% | <45% |

**Bronze Minimum: 22 pts**

#### 2.2 Team Response Time (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | Detection + mitigation started <10 min | Cross-team coordination, <15 min | Multi-tier coordination, <20 min |
| 27–35 | 10–20 minutes | 15–30 minutes | 20–40 minutes |
| 18–26 | 20–40 minutes | 30–60 minutes | 40–75 minutes |
| 0–17 | >40 minutes | >60 minutes | >75 minutes |

**Bronze Minimum: 18 pts**

#### 2.3 Lessons Learned & Action Items (30 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 27–30 | PIR completed within 48 hours, 5+ actionable items, owners assigned, timeline set |
| 20–26 | PIR completed within 1 week, 3–5 action items, owners assigned |
| 12–19 | PIR completed, <3 action items or vague ownership |
| 0–11 | No PIR or incomplete |

**Bronze Minimum: 12 pts**

---

### 3. DEPLOYMENT SUCCESS METRICS (100 pts)

#### 3.1 Deployment Success Rate (50 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 45–50 | >95% successful deployments to non-prod | >92% success across services | >88% multi-tier deployment success |
| 34–44 | 88–95% success | 85–92% success | 82–88% success |
| 22–33 | 80–88% success | 78–85% success | 75–82% success |
| 0–21 | <80% success | <78% | <75% |

**Bronze Minimum: 22 pts**

#### 3.2 Rollback Execution (30 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 27–30 | Rollback tested and successful within 10 minutes, automated |
| 20–26 | Rollback successful within 15–20 minutes |
| 12–19 | Rollback possible but slow (20–30 min) |
| 0–11 | No rollback capability or >30 min or frequently fails |

**Bronze Minimum: 12 pts**

#### 3.3 Deployment Incident Rate (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | 0–1 deployment incidents/month | 0–2 incidents/month | 0–3 incidents/month |
| 13–17 | 2–3 incidents | 3–5 incidents | 4–7 incidents |
| 7–12 | 4–5 incidents | 6–8 incidents | 8–12 incidents |
| 0–6 | >5 incidents | >8 incidents | >12 incidents |

**Bronze Minimum: 7 pts**

---

### 4. NON-PROD INCIDENT METRICS (80 pts)

#### 4.1 Test Environment Incident Resolution Time (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | Average <2 hours | Average <3 hours | Average <4 hours |
| 27–35 | 2–4 hours | 3–6 hours | 4–8 hours |
| 18–26 | 4–8 hours | 6–12 hours | 8–16 hours |
| 0–17 | >8 hours | >12 hours | >16 hours |

**Bronze Minimum: 18 pts**

#### 4.2 Non-Prod Incident Frequency (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | <3 incidents/month | <5 incidents/month | <8 incidents/month |
| 27–35 | 3–5 incidents | 5–8 incidents | 8–12 incidents |
| 18–26 | 6–8 incidents | 9–12 incidents | 13–18 incidents |
| 0–17 | >8 incidents | >12 incidents | >18 incidents |

**Bronze Minimum: 18 pts**

---

### 5. MONITORING EFFECTIVENESS (50 pts)

#### 5.1 Alert Quality in Non-Prod (30 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 27–30 | <20% false positive rate, actionable alerts, clear ownership |
| 20–26 | 20–35% false positive rate, mostly actionable |
| 12–19 | 35–50% false positive rate |
| 0–11 | >50% false positive rate or non-actionable |

**Bronze Minimum: 12 pts (≤50% false positives)**

#### 5.2 Production Mirroring Quality (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Non-prod mirrors 80%+ production monitoring setup | 78%+ match across services | 75%+ match across tiers |
| 13–17 | 65–80% match | 65–78% match | 65–75% match |
| 7–12 | 50–65% match | 55–65% match | 55–65% match |
| 0–6 | <50% match | <55% match | <55% match |

**Bronze Minimum: 7 pts (≥50% production mirroring)**

---

### PERFORMANCE SCORE SUMMARY

| Category | Base Points |
|---|---|
| Chaos Testing Outcomes | 150 pts |
| Game Day Performance | 120 pts |
| Deployment Success | 100 pts |
| Non-Prod Incident Metrics | 80 pts |
| Monitoring Effectiveness | 50 pts |
| **TOTAL** | **500 pts** |

*(Apply profile weights, then normalize proportionally if total exceeds 500)*

---

## BRONZE CERTIFICATION REQUIREMENTS

### Score Requirements

| Dimension | Min Required | Max Available |
|---|---|---|
| Capability Score | ≥100 pts | 500 pts |
| Performance Score | ≥100 pts | 500 pts |
| **Total Score** | **200–350 pts** | **1000 pts** |

> **Dimension Floor Rule:** Both dimension floors must be met independently. Scoring 200+ total without meeting both floors = No Bronze. This prevents a team with excellent chaos game days but no DR documentation from gaming the total.

---

## CERTIFICATION PROCESS

```
Step 1: Non-Negotiables Gate Check (6 total)
  → ALL must pass → Proceed to scoring
  → ANY failure → No certification, improvement plan required

Step 2: Capability Assessment
  → Score all subcategories
  → Apply profile weights, normalize to 500 max
  → Must achieve ≥100 pts

Step 3: Performance Assessment
  → Collect non-prod metrics (trailing 3 months)
  → Apply profile weights, normalize to 500 max
  → Must achieve ≥100 pts

Step 4: Total Score Calculation
  → Capability + Performance = Total
  → Must fall within 200–350 range

Step 5: Award "APEX Bronze (Provisional)"
  → 3-month Probation Period begins
  → Monthly check-ins with framework admin

Step 6: Full Certification
  → Re-assess at end of probation:
     - All non-negotiables still passing?
     - Score still ≥200 with both floors met?
     - No systemic failures during probation?
  → Award "APEX Bronze Certified"
  → Valid for 12 months / 6-month evaluation cycle
```

---

## PROBATION PERIOD (PP) & PERFORMANCE IMPROVEMENT PLAN (PIP)

### Probation Period — 3 Months
- **Status:** APEX Bronze (Provisional)
- Maintain all 6 non-negotiables
- Score remains ≥200 with both dimension floors met
- Monthly check-ins with framework admin
- **Outcome:** ✅ Full Bronze Certified | ❌ Extend PP (once) or No Certification

### Performance Improvement Plan — 3 Months
Triggered by:
- Score drops below 200
- Either dimension floor fails
- Any non-negotiable fails
- Systemic chaos failures (>2 months consecutive poor outcomes)

- **Status:** APEX Bronze (PIP)
- Bi-weekly reviews with framework admin
- Documented improvement plan with timeline
- **Outcome:** ✅ Return to Bronze Certified | ❌ Certification lapsed

---

## CERTIFICATION DISPLAY

```
══════════════════════════════════════════════════════
    APEX RESILIENCE FRAMEWORK
    BRONZE CERTIFIED

    Application:    Payment Gateway Service
    Complexity:     Mid-Tier
    Profile:        High-Velocity
    
    Capability:     155/500  (31.0%)
    Performance:    150/500  (30.0%)
    
    TOTAL SCORE:    305/1000 (30.5%)
    
    Certified:      January 15, 2025
    Valid Through:  January 14, 2026
    Next Evaluation: July 15, 2025
══════════════════════════════════════════════════════
```

---

## EXAMPLE SCORING SCENARIOS

### Example 1: Simple App — Minimal Bronze (220 pts) ✅
**Application:** Internal Dashboard | **Complexity:** Simple | **Profile:** Standard

| Dimension | Category | Score |
|---|---|---|
| **Capability (110/500)** | DR & BC | 60/90 |
| | Chaos Engineering | 50/100 |
| | Incident Management | 70/110 |
| | Observability | 55/90 |
| | Automation | 30/55 |
| | Architecture | 18/30 |
| | Culture | 17/25 |
| **Performance (110/500)** | Chaos Outcomes | 70/150 |
| | Game Day | 50/120 |
| | Deployments | 60/100 |
| | Non-Prod Incidents | 40/80 |
| | Monitoring Effectiveness | 25/50 |

**Non-Negotiables:** ✅ All 6 passed
**Result:** Bronze (Provisional) → Bronze Certified

---

### Example 2: Mid-Tier App — Strong Bronze (305 pts) ✅
**Application:** E-Commerce Checkout | **Complexity:** Mid-Tier | **Profile:** High-Velocity

| Dimension | Score |
|---|---|
| Capability | 155/500 |
| Performance | 150/500 |
| **Total** | **305/1000** |

**Non-Negotiables:** ✅ All 6 passed
**Result:** Bronze Certified (strong foundation — Silver preparation recommended)

---

### Example 3: Mid-Tier App — Bronze Denied ✗
**Application:** Inventory Management System | **Complexity:** Mid-Tier | **Profile:** Standard

| Dimension | Score |
|---|---|
| Capability | 85/500 |
| Performance | 90/500 |
| **Total** | **175/1000** |

**Non-Negotiable Failures:**
- ✗ DR not tested in 22 months (Non-Negotiable #1)
- ✗ No chaos tool installed (Non-Negotiable #4)
- ✗ Monitoring infra-only at 40% (Non-Negotiable #3)

**Result:** No Certification. 90-day remediation plan required. Reassess in 3 months.

---

## BRONZE TO SILVER TRANSITION GUIDANCE

### When to pursue Silver:
- Consistently scoring 320–350 (upper Bronze range) over 6-month evaluation period
- All 6 non-negotiables solidly passing
- Team comfortable with Bronze practices
- Ready for production deployment considerations

### Key additions at Silver:
- Bronze nice-to-haves (incident process, on-call, deployment pipeline, incident volume) become **mandatory** Silver non-negotiables
- Quarterly DR testing becomes mandatory (vs. annual at Bronze)
- Chaos testing frequency increases to quarterly minimum
- SLI/SLO definition and tracking required
- Higher thresholds across all performance categories

---

## FRAMEWORK VERSIONING & FUTURE-PROOFING

| Attribute | Detail |
|---|---|
| **Version** | v1.1 |
| **Effective Date** | TBD |
| **Review Cycle** | Annual |
| **Changelog** | "API Gateway Profile" → "Cascading Risk Profile"; Evaluation period updated to 6 months; Dimension Floor Rule clarified |

**Built-in flexibility:**
- Category weights adjustable in future versions (e.g., increasing AI/AIOps weighting)
- New subcategories can be added within existing categories
- New profiles can be introduced (e.g., "AI-Native Profile", "Edge Computing Profile")
- Existing certifications honoured for 6 months after framework updates

---

*APEX Bronze Certification Framework v1.1 — Non-Production Foundational Resilience*
*Next Level: APEX Silver v1.1 — Non-Production Operational Maturity*