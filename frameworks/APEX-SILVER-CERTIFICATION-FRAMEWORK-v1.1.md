# APEX SILVER CERTIFICATION FRAMEWORK (v1.1)
**Non-Production Environments... Operational Maturity**

> **Changelog from v1.0:** "API Gateway Profile" renamed to "Cascading Risk Profile" for clarity. Evaluation period updated to 6 months. Probation Period (PP) and PIP remain 3 months.

---

## FRAMEWORK OVERVIEW

| Attribute | Detail |
|---|---|
| **Target Environment** | Non-Production (Dev, Test, Staging), Advanced Readiness |
| **Philosophy** | Operational maturity, teams demonstrate they can operate at production standards *before* going live. Silver practices in non-prod are what Gold demands in prod. |
| **Score Range** | 351–500 points out of 1000 (35.1%–50%) |
| **Prerequisite** | Must have achieved Bronze certification OR score ≥200 |
| **Scoring Dimensions** | **2-Dimensional**: Capability (50%) + Performance (50%) |
| **Evaluation Period** | 6 months |
| **Probation Period (PP)** | 3 months → Full Certification |
| **Performance Improvement Plan (PIP)** | 3 months |
| **Validity** | 12 months with annual re-certification |

> **Key Shift from Bronze → Silver:** Bronze is about having the *foundations* in place. Silver is about demonstrating those foundations *work consistently* at production-grade discipline, in a non-production environment. The Bronze nice-to-haves become Silver hard gates.

> **Dimension Floor Rule:** A total score of 351–500 qualifies for Silver territory, but both dimension floors must be met independently. This ensures the score reflects genuine, balanced operational maturity, not excellence in one pillar masking a critical weakness in another. Think of it as passing each paper individually, not just on aggregate.
> - Capability Score ≥175 pts
> - Performance Score ≥175 pts
> Failing either floor = No Silver Certification, regardless of total score.

---

## COMPLEXITY CLASSIFICATION (Same as Bronze)

| Level | Score | Characteristics |
|---|---|---|
| **Simple** | 0–25 pts | 1–3 components, single team, Tier 3–5 |
| **Mid-Tier** | 26–50 pts | 4–10 components, 2–4 teams, Tier 2–3 |
| **Complex** | 51–80 pts | 11+ components, 5+ teams, Tier 0–1 |

*(See Bronze v1.1 for the full 8-Criteria Weighted Scoring System)*

### How Tier Differentiation Works in APEX

APEX does not use tier multipliers to move the certification finish line. A Silver application always needs 351–500 points regardless of its tier. Instead, tier differentiation is built into the journey through:

1. **Complexity Classification:** Tier 0 presence automatically pushes an app to Complex via the Tier Composition criterion (3× weight, 15 pts max) — the heaviest weighted criterion in the system
2. **Profile Weights:**  Complex apps have category weights amplified for their risk profile. Framework admin can adjust weights with documented justification
3. **Performance Thresholds within Categories:** Complex apps face stricter expectations across chaos success rates, incident resolution times, and monitoring coverage
4. **Non-Negotiables:** Complex apps face more demanding hard gate requirements
5. **Incident Penalties:** Severity classification hits harder on complex/high-tier apps

> **One universal finish line. Differentiation happens in how demanding the journey is to get there.**

---

## APPLICATION PROFILE ASSIGNMENT (Same as Bronze)

| Profile | Key Weight Adjustments | Best Suited For |
|---|---|---|
| **High-Velocity** | Deployment Automation 2×, Chaos Testing 1.5×, IaC 1.5× | Frequent releases, breaking changes |
| **Stable Enterprise** | DR & BC 1.5×, Architecture 1.5×, Documentation 1.5× | Infrequent releases, stability-focused |
| **Data-Intensive** | Data Complexity 2×, Backup Strategy 1.5×, Monitoring 1.5× | Complex data flows, ETL pipelines |
| **Cascading Risk** | Dependency Management 2×, Circuit Breakers 1.5×, Availability 1.5× | High external/internal dependencies with cascading failure risk |
| **Standard** | All weights 1× | Balanced, default |

Framework admin may override individual weights with documented justification.

---

## SILVER NON-NEGOTIABLES (Hard Gates)

**MUST PASS ALL 10 to qualify for Silver.**
*(All 6 Bronze non-negotiables remain in force, plus 4 new Silver-specific gates)*

### Inherited from Bronze (1–6)
| # | Requirement |
|---|---|
| 1 | DR Plan exists and tested in last 12 months |
| 2 | RTO/RPO defined and documented |
| 3 | Basic monitoring in place (infra + app) |
| 4 | Chaos tool installed and 1+ test executed |
| 5 | Dependencies documented |
| 6 | Owner identified |

### New at Silver (7–10): Former Bronze Nice-to-Haves, Now Mandatory

| # | Requirement | Simple | Mid-Tier | Complex |
|---|---|---|---|---|
| 7 | **DR tested quarterly, >70% success rate** | Quarterly tests, results documented | All services tested quarterly | All tiers tested quarterly |
| 8 | **On-call rotation established (2+ people minimum)** | 2-person rotation | Per-service rotations | Tier coverage |
| 9 | **Deployment pipeline fully automated with rollback** | Automated deploy + rollback tested | All services automated | Tier orchestration automated |
| 10 | **≤8 non-prod incidents/month (3-month average)** | ≤8/month | ≤8/month | ≤10/month |

> Failure of ANY of the 10 non-negotiables = No Silver Certification, regardless of score.

---

## DIMENSION 1: CAPABILITY SCORE (500 points max)

### 1. DISASTER RECOVERY & BUSINESS CONTINUITY (90 pts)

#### 1.1 DR Plan Documentation (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | Comprehensive runbook, version controlled, regularly updated | All services detailed, dependency map current, automated updates | Tier-by-tier runbook, cross-tier orchestration, automated validation |
| 18–22 | Complete runbook, quarterly updates | All services covered, mostly current | All tiers covered, mostly current |
| 13–17 | Good runbook, bi-annual updates | Most services, some updates needed | Most tiers, some gaps |
| 0–12 | Basic or outdated | Incomplete | Incomplete tiers |

**Silver Minimum: 18 pts (comprehensive, regularly updated)**

#### 1.2 RTO/RPO Definition & Validation (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | RTO <2hrs, RPO <30min, validated quarterly | Per-service, validated quarterly | Per-tier, validated quarterly |
| 18–22 | RTO <4hrs, RPO <1hr, validated quarterly (Silver minimum) | Per-service validated quarterly | Per-tier validated quarterly |
| 13–17 | RTO <4hrs, RPO <1hr, tested but not always met | Some services validated | Some tiers validated |
| 0–12 | Defined but not consistently achieved | Not validated | Not validated |

**Silver Minimum: 18 pts**

#### 1.3 Backup Strategy & Validation (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Daily automated backups, 30-day retention, monthly restore tests | All stores, 30-day retention, monthly restore validation | Tiered strategy, 30-day retention, monthly tier-specific restore tests |
| 14–17 | Daily automated, 14-day retention, quarterly restore tests | All stores, quarterly validation | Tiered, quarterly validation |
| 10–13 | Automated backups, basic validation | Most stores validated | Most tiers validated |
| 0–9 | Minimal validation or ad-hoc | Inconsistent | Inconsistent |

**Silver Minimum: 14 pts (quarterly restore validation minimum)**

#### 1.4 DR Testing Frequency & Success Rate (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Quarterly tests, >90% success rate, all scenarios | Quarterly, >90% success, all services | Quarterly, >90% success, all tiers |
| 14–17 | Quarterly tests, 70–90% success (Silver minimum) | Quarterly, 70–90% | Quarterly, 70–90% |
| 10–13 | Quarterly but <70% success | Quarterly, partial coverage | Quarterly, partial tiers |
| 0–9 | Less than quarterly or poor results | Inconsistent | Inconsistent |

**Silver Minimum: 14 pts (Non-Negotiable #7 — Quarterly + >70% success)**

---

### 2. CHAOS ENGINEERING & RESILIENCE TESTING (100 pts)

#### 2.1 Chaos Engineering Maturity (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Quarterly scheduled chaos, 5+ scenario types, results tracked | Quarterly multi-service chaos, automated rollback tested | Quarterly multi-tier chaos, blast radius controls validated |
| 22–26 | Quarterly chaos, 3–4 scenarios (Silver minimum) | Quarterly, 4+ scenarios | Quarterly, 5+ scenarios across tiers |
| 16–21 | Bi-monthly chaos, limited scenarios | Bi-monthly, partial services | Bi-monthly, partial tiers |
| 0–15 | Ad-hoc or less frequent | Inconsistent | Inconsistent |

**Silver Minimum: 22 pts**

#### 2.2 Chaos Testing Coverage & Sophistication (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 32–35 | 80%+ component coverage, advanced scenarios (data corruption, cascading failures) | 80%+ service coverage, dependency failures, network partitions | 75%+ tier coverage, cross-tier failure scenarios |
| 25–31 | 60%+ coverage, network/latency/restart | 70%+ service coverage, multi-service scenarios | 65%+ tier coverage, multi-tier scenarios |
| 18–24 | 40–60% coverage, basic scenarios | 50–70% coverage | 50–65% coverage |
| 0–17 | <40% coverage | <50% | <50% |

**Silver Minimum: 25 pts**

#### 2.3 Game Day Frequency & Scope (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 32–35 | Quarterly game days, cross-functional, customer-impact scenarios | Quarterly, multiple teams, realistic scenarios | Quarterly, multi-tier coordination, executive involvement |
| 25–31 | Bi-annual game days, cross-functional participation | Bi-annual, good team participation | Bi-annual, multi-tier scenarios |
| 18–24 | Annual game days, basic participation | Annual, cross-functional | Annual, multi-tier |
| 0–17 | Infrequent or single-team only | Infrequent | Infrequent |

**Silver Minimum: 25 pts (bi-annual minimum with cross-functional teams)**

---

### 3. INCIDENT MANAGEMENT & RESPONSE (110 pts)

#### 3.1 Incident Response Process Documentation (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Comprehensive runbooks, version controlled, tested quarterly, escalation matrix clear | Service-specific runbooks, severity definitions, escalation tested | Tier-specific runbooks, cross-tier escalation, incident command structure tested |
| 22–26 | Complete runbooks, annual testing, clear escalation (Silver minimum) | Per-service runbooks, tested | Per-tier runbooks, tested |
| 16–21 | Runbooks exist, mostly current | Most services covered | Most tiers covered |
| 0–15 | Basic or outdated | Incomplete | Incomplete |

**Silver Minimum: 22 pts**

#### 3.2 On-Call Practices & Coverage (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | 3+ person rotation, schedule published, intelligent routing, handoff procedures | Per-service rotations (2+), clear escalation, load balancing | Tier-specific coverage, cross-tier escalation clear |
| 18–22 | 2-person rotation, schedule published (Silver minimum) | 2+ per service, published | Basic tier coverage |
| 12–17 | 2 people identified, informal | Partial service coverage | Partial tier coverage |
| 0–11 | Single person or ad-hoc | None | None |

**Silver Minimum: 18 pts (Non-Negotiable #8 — 2-person rotation minimum)**

#### 3.3 Incident Tracking & Metrics (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Formal system, severity tracked, metrics dashboard (MTTD, MTTR, frequency), trend analysis | All services tracked, comprehensive metrics, automated reporting | Tier-aware tracking, cross-tier impact analysis, predictive insights |
| 22–26 | Formal system, severity tracked, basic metrics calculated | Per-service tracking, basic metrics | Per-tier tracking, basic metrics |
| 16–21 | Ticketing system, severity classification | Most services tracked | Most tiers tracked |
| 0–15 | Basic tracking only | Inconsistent | Inconsistent |

**Silver Minimum: 22 pts**

#### 3.4 Post-Incident Review Process (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | PIRs for all Sev 0–2, blameless culture, action items with SLA, pattern analysis | All Sev 0–2, cross-service learnings, feedback loops | All Sev 0–2, cross-tier learnings, knowledge sharing |
| 18–22 | PIRs for all Sev 0–2, action tracking, blameless (Silver minimum) | All Sev 0–2, action tracking | All Sev 0–2, action tracking |
| 12–17 | PIRs for Sev 0–1, basic tracking | Most Sev 0–2 covered | Most Sev 0–2 covered |
| 0–11 | Inconsistent PIRs | Inconsistent | Inconsistent |

**Silver Minimum: 18 pts**

---

### 4. OBSERVABILITY & DETECTION (90 pts)

#### 4.1 Monitoring Coverage (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | 85%+ coverage, infra + app + business metrics, proactive alerting | 85%+ all services, full-stack visibility | 85%+ all tiers, cross-tier visibility |
| 22–26 | 70–85% coverage, infra + app + basic business metrics (Silver minimum) | 70–85% services | 70–85% tiers |
| 16–21 | 60–70% coverage | 60–70% | 60–70% |
| 0–15 | <60% coverage | <60% | <60% |

**Silver Minimum: 22 pts (70%+ coverage with business metrics)**

#### 4.2 Logging & Tracing (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | Centralized logging, 30-day retention, distributed tracing 70%+ requests, correlation IDs | All services centralized, basic distributed tracing, correlation across services | Tier-tagged logging, distributed tracing across tiers, 30-day retention |
| 18–22 | Centralized, 14-day retention, basic tracing capability | All services centralized, 14-day | Tier-tagged, 14-day |
| 12–17 | Centralized, 7–14 day retention | Most services centralized | Most tiers centralized |
| 0–11 | Decentralized or minimal retention | Inconsistent | Inconsistent |

**Silver Minimum: 18 pts**

#### 4.3 Alerting Quality & Actionability (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | <15% false positives, context-rich alerts, runbook links, severity-based routing | <15% false positives, service-specific alerting, auto-enrichment | <15% false positives, tier-aware alerting, intelligent routing |
| 18–22 | <30% false positives, actionable alerts, basic context (Silver minimum) | <30% false positives, per-service alerts | <30% false positives, tier alerts |
| 12–17 | 30–45% false positives, mostly actionable | Partial context | Partial tier context |
| 0–11 | >45% false positives or non-actionable | Poor quality | Poor quality |

**Silver Minimum: 18 pts (<30% false positives)**

#### 4.4 SLI/SLO/SLA Tracking (10 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 9–10 | 5+ SLIs defined, SLOs set and tracked, error budgets monitored, automated dashboards | Per-service SLIs/SLOs (3+ per service), budget tracking | Per-tier SLIs/SLOs, cross-tier budget tracking |
| 7–8 | 3+ SLIs defined and tracked, SLOs documented (Silver minimum) | Per-service SLIs (3+ minimum) | Per-tier SLIs (3+ minimum) |
| 4–6 | 1–2 SLIs defined | Partial service coverage | Partial tier coverage |
| 0–3 | No SLIs or not tracked | None | None |

**Silver Minimum: 7 pts (3+ SLIs defined — now mandatory)**

---

### 5. AUTOMATION & SELF-HEALING (55 pts)

#### 5.1 Infrastructure as Code (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | 80%+ IaC, version controlled, automated testing, immutable infrastructure | 80%+ all services, environment parity tested | 80%+ all tiers, tier templates validated |
| 14–17 | 60–80% IaC, version controlled, basic testing (Silver minimum) | 60–80% services | 60–80% tiers |
| 10–13 | 50–60% IaC | 50–60% | 50–60% |
| 0–9 | <50% IaC | <50% | <50% |

**Silver Minimum: 14 pts (60%+ IaC with testing)**

#### 5.2 Deployment Automation & Progressive Delivery (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | Fully automated CI/CD, blue-green or canary, automated rollback tested quarterly | All services automated, progressive delivery, rollback validated | Tier orchestration automated, rollback tested |
| 18–22 | Fully automated CI/CD, rollback capability tested (Silver minimum) | All services automated, rollback works | Orchestrated deployment, rollback works |
| 12–17 | Automated with manual rollback | Most services automated | Partial tier automation |
| 0–11 | Semi-automated or manual | Inconsistent | Inconsistent |

**Silver Minimum: 18 pts (Non-Negotiable #9: fully automated with tested rollback)**

#### 5.3 Auto-Remediation Capabilities (10 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 9–10 | 30%+ incidents auto-remediated (restart, scaling, failover) | 35%+ auto-remediation across common patterns | 40%+ auto-remediation, tier-aware healing |
| 7–8 | 20–30% auto-remediation (Silver target) | 25–35% | 30–40% |
| 4–6 | 10–20% auto-remediation | 15–25% | 20–30% |
| 0–3 | <10% or none | <15% | <20% |

**Silver Target: 7+ pts (20%+ auto-remediation encouraged)**

---

### 6. ARCHITECTURE & DESIGN RESILIENCE (30 pts)

#### 6.1 Dependency Management & Circuit Breakers (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 14–15 | Comprehensive dependency map, circuit breakers implemented, graceful degradation tested | Per-service circuit breakers, timeout policies, fallback mechanisms | Tier-aware circuit breakers, cross-tier graceful degradation |
| 11–13 | Dependency map current, basic circuit breakers (Silver minimum) | Service-level circuit breakers, basic fallbacks | Tier-level circuit breakers |
| 7–10 | Dependencies mapped, planning circuit breakers | Most services mapped | Most tiers mapped |
| 0–6 | Incomplete dependency mapping | Incomplete | Incomplete |

**Silver Minimum: 11 pts**

#### 6.2 Environment Parity & Data Quality (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 14–15 | Non-prod mirrors 90%+ production, realistic data volumes, sanitized prod data | Staging 90%+ production fidelity, realistic load testing | Staging 85%+ fidelity across tiers, tier-representative data |
| 11–13 | 80–90% parity, good data quality (Silver minimum) | 80–90% fidelity | 75–85% tier fidelity |
| 7–10 | 70–80% parity | 70–80% | 65–75% |
| 0–6 | <70% parity | <70% | <65% |

**Silver Minimum: 11 pts (80%+ environment parity)**

---

### 7. CULTURE & ORGANIZATIONAL MATURITY (25 pts)

#### 7.1 Resilience Ownership & Champions (10 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 9–10 | Dedicated resilience champion embedded in team, clear accountability, executive visibility |
| 7–8 | Resilience champion identified and active (Silver minimum) |
| 4–6 | Owner identified, some resilience focus |
| 0–3 | No dedicated focus |

**Silver Minimum: 7 pts**

#### 7.2 Training & Skill Development (8 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 7–8 | Bi-annual resilience training, chaos engineering workshops, certifications encouraged |
| 5–6 | Annual training, some team participation (Silver minimum) |
| 3–4 | Ad-hoc training |
| 0–2 | No formal training |

**Silver Minimum: 5 pts**

#### 7.3 Knowledge Management & Documentation (7 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 6–7 | Centralized knowledge base, searchable, regularly updated, lessons learned documented |
| 4–5 | Knowledge base exists, basic documentation (Silver minimum) |
| 2–3 | Basic documentation scattered |
| 0–1 | Tribal knowledge only |

**Silver Minimum: 4 pts**

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

> Silver performance measures **non-production execution at production-grade discipline**, faster response times, higher success rates, and stricter thresholds than Bronze across all categories.

---

### 1. CHAOS TESTING OUTCOMES (150 pts)

#### 1.1 Chaos Test Success Rate (80 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 72–80 | >85% success rate | >80% success | >75% success |
| 54–71 | 75–85% (Silver minimum) | 70–80% | 65–75% |
| 36–53 | 60–75% | 60–70% | 55–65% |
| 0–35 | <60% | <60% | <55% |

**Silver Minimum: 54 pts (75%+ Simple, 70%+ Mid, 65%+ Complex)**

#### 1.2 Blast Radius Containment (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | Failures isolated, circuit breakers prevent cascade | Service-level containment, graceful degradation works | Tier-level containment, cross-tier protection works |
| 27–35 | Single component impact only (Silver minimum) | 1–2 services affected | Single tier affected |
| 18–26 | Limited cascade | 2–3 services | 2 tiers |
| 0–17 | Widespread cascade | >3 services | >2 tiers |

**Silver Minimum: 27 pts**

#### 1.3 Recovery Time from Chaos (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | Recovery <3 minutes | <5 minutes | <10 minutes |
| 20–26 | 3–10 minutes (Silver minimum) | 5–15 minutes | 10–20 minutes |
| 12–19 | 10–20 minutes | 15–30 minutes | 20–45 minutes |
| 0–11 | >20 minutes | >30 minutes | >45 minutes |

**Silver Minimum: 20 pts**

---

### 2. GAME DAY PERFORMANCE (120 pts)

#### 2.1 Scenario Completion Rate (50 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 45–50 | 100% scenarios, advanced complexity | 90%+ completed, multi-service coordination | 85%+ completed, multi-tier scenarios |
| 34–44 | 80–100% completion (Silver minimum) | 75–90% | 70–85% |
| 22–33 | 65–80% | 60–75% | 55–70% |
| 0–21 | <65% | <60% | <55% |

**Silver Minimum: 34 pts**

#### 2.2 Team Response Time (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | <5 min detection + mitigation | <10 min cross-team | <15 min multi-tier |
| 27–35 | 5–15 minutes (Silver minimum) | 10–20 minutes | 15–30 minutes |
| 18–26 | 15–30 minutes | 20–45 minutes | 30–60 minutes |
| 0–17 | >30 minutes | >45 minutes | >60 minutes |

**Silver Minimum: 27 pts**

#### 2.3 Lessons Learned Quality (30 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 27–30 | PIR within 24 hours, 7+ actionable items, pattern analysis, cross-team sharing |
| 20–26 | PIR within 48 hours, 5–7 items, owners assigned, timelines set (Silver minimum) |
| 12–19 | PIR within 1 week, 3–5 items |
| 0–11 | >1 week or incomplete |

**Silver Minimum: 20 pts**

---

### 3. DEPLOYMENT SUCCESS METRICS (100 pts)

#### 3.1 Deployment Success Rate (50 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 45–50 | >97% success | >95% | >93% |
| 34–44 | 93–97% (Silver minimum) | 91–95% | 88–93% |
| 22–33 | 88–93% | 85–91% | 82–88% |
| 0–21 | <88% | <85% | <82% |

**Silver Minimum: 34 pts**

#### 3.2 Rollback Speed & Reliability (30 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 27–30 | Automated rollback <5 minutes, 100% success rate, tested monthly |
| 20–26 | Automated rollback <10 minutes, >95% success (Silver minimum) |
| 12–19 | Rollback <15 minutes, >90% success |
| 0–11 | >15 minutes or <90% success |

**Silver Minimum: 20 pts**

#### 3.3 Deployment Incident Rate (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | 0 deployment incidents/month | 0–1 incidents/month | 0–2 incidents/month |
| 13–17 | 1–2 incidents (Silver minimum) | 2–3 incidents | 3–5 incidents |
| 7–12 | 3–4 incidents | 4–6 incidents | 6–8 incidents |
| 0–6 | >4 incidents | >6 incidents | >8 incidents |

**Silver Minimum: 13 pts**

---

### 4. NON-PROD INCIDENT METRICS (80 pts)

#### 4.1 Incident Resolution Time (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | Average <1 hour | <2 hours | <3 hours |
| 27–35 | 1–2 hours (Silver minimum) | 2–4 hours | 3–6 hours |
| 18–26 | 2–4 hours | 4–8 hours | 6–12 hours |
| 0–17 | >4 hours | >8 hours | >12 hours |

**Silver Minimum: 27 pts**

#### 4.2 Non-Prod Incident Frequency (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | <2 incidents/month | <3 incidents/month | <5 incidents/month |
| 27–35 | 2–4 incidents | 3–5 incidents | 5–8 incidents |
| 18–26 | 5–8 incidents | 6–8 incidents | 9–10 incidents |
| 0–17 | >8 incidents | >8 incidents | >10 incidents |

**Silver Minimum: 18 pts (Non-Negotiable #10, ≤8/month for Simple/Mid, ≤10 for Complex)**

---

### 5. MONITORING EFFECTIVENESS (50 pts)

#### 5.1 Alert Quality (30 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 27–30 | <10% false positives, ML-tuned, context-rich, auto-enriched |
| 20–26 | <20% false positives, actionable, good context (Silver minimum) |
| 12–19 | <30% false positives |
| 0–11 | >30% false positives |

**Silver Minimum: 20 pts (<20% false positives)**

#### 5.2 Production Mirroring Quality (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | 90%+ production mirroring | 88%+ mirroring | 85%+ tier mirroring |
| 13–17 | 80–90% (Silver minimum) | 78–88% | 75–85% |
| 7–12 | 70–80% | 68–78% | 65–75% |
| 0–6 | <70% | <68% | <65% |

**Silver Minimum: 13 pts**

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

## SILVER CERTIFICATION REQUIREMENTS

### Score Requirements

| Dimension | Min Required | Max Available |
|---|---|---|
| Capability Score | ≥175 pts | 500 pts |
| Performance Score | ≥175 pts | 500 pts |
| **Total Score** | **351–500 pts** | **1000 pts** |

> **Dimension Floor Rule:** Scoring 351+ total qualifies for Silver territory, but both floors must be met independently. An application with excellent chaos game day scores but poor capability documentation cannot use performance to compensate, both pillars must stand on their own. Think of it as passing each paper individually, not just on aggregate.

### Prerequisite
Must hold active Bronze Certification OR have a total score ≥200.

---

## CERTIFICATION PROCESS

```
Step 1: Bronze Validation
  → Confirm active Bronze certification or score ≥200

Step 2: Non-Negotiables Gate Check (10 total)
  → ALL must pass → Proceed to scoring
  → ANY failure → No Silver, remediation required

Step 3: Capability Assessment
  → Score all subcategories at Silver thresholds
  → Apply profile weights, normalize to 500 max
  → Must achieve ≥175 pts

Step 4: Performance Assessment
  → Collect non-prod metrics (trailing 3 months)
  → Apply profile weights, normalize to 500 max
  → Must achieve ≥175 pts

Step 5: Total Score Calculation
  → Capability + Performance = Total
  → Must fall within 351–500 range

Step 6: Award "APEX Silver (Provisional)"
  → 3-month Probation Period begins
  → Monthly check-ins with framework admin

Step 7: Full Certification
  → Re-assess at end of probation:
     - All 10 non-negotiables still passing?
     - Score still ≥351 with both floors met?
     - No systemic failures during probation?
  → Award "APEX Silver Certified"
  → Valid for 12 months / 6-month evaluation cycle
```

---

## PROBATION PERIOD (PP) & PERFORMANCE IMPROVEMENT PLAN (PIP)

### Probation Period: 3 Months
- **Status:** APEX Silver (Provisional)
- Maintain all 10 non-negotiables
- Score remains ≥351 with both dimension floors met
- Monthly check-ins with framework admin
- **Outcome:** ✅ Full Silver Certified | ❌ Extend PP (once) or downgrade to Bronze

### Performance Improvement Plan: 3 Months
Triggered by:
- Score drops below 351
- Either dimension floor fails
- Any non-negotiable fails
- >3 consecutive months above incident limits (Non-Negotiable #10)

- **Status:** APEX Silver (PIP)
- Bi-weekly reviews with framework admin
- Documented improvement plan with timeline
- Business sponsor notified
- **Outcome:** ✅ Return to Silver Certified | ❌ Certification lapsed → Bronze

---

## CERTIFICATION DISPLAY

```
══════════════════════════════════════════════════════
    APEX RESILIENCE FRAMEWORK
    SILVER CERTIFIED

    Application:    E-Commerce Checkout Platform
    Complexity:     Mid-Tier
    Profile:        High-Velocity

    Capability:     240/500  (48.0%)
    Performance:    235/500  (47.0%)

    TOTAL SCORE:    475/1000 (47.5%)

    Certified:      February 1, 2025
    Valid Through:  January 31, 2026
    Next Evaluation: August 1, 2025
══════════════════════════════════════════════════════
```

---

## EXAMPLE SCORING SCENARIOS

### Example 1: Simple App, Lower Silver (365 pts) ✅
**Application:** Customer Portal | **Complexity:** Simple | **Profile:** Standard

| Dimension | Category | Score |
|---|---|---|
| **Capability (185/500)** | DR & BC | 75/90 |
| | Chaos Engineering | 82/100 |
| | Incident Management | 95/110 |
| | Observability | 72/90 |
| | Automation | 45/55 |
| | Architecture | 24/30 |
| | Culture | 20/25 |
| **Performance (180/500)** | Chaos Outcomes | 110/150 |
| | Game Day | 85/120 |
| | Deployments | 82/100 |
| | Non-Prod Incidents | 65/80 |
| | Monitoring Effectiveness | 38/50 |

**Non-Negotiables:** ✅ All 10 passed
**Result:** Silver (Provisional) → Silver Certified

---

### Example 2: Mid-Tier App, Strong Silver (475 pts) ✅
**Application:** Payment Processing Platform | **Complexity:** Mid-Tier | **Profile:** High-Velocity

| Dimension | Score |
|---|---|
| Capability (weighted) | 240/500 |
| Performance (weighted) | 235/500 |
| **Total** | **475/1000** |

**Non-Negotiables:** ✅ All 10 passed
**Result:** Silver Certified (well-positioned for Gold preparation)

---

### Example 3: Mid-Tier App, Silver Denied (Performance Floor Fail) ✗
**Application:** Logistics Management | **Complexity:** Mid-Tier | **Profile:** Stable Enterprise

| Dimension | Score |
|---|---|
| Capability | 220/500 |
| Performance | **158/500** ← Below 175 floor |
| **Total** | **378/1000** (Silver range) |

**Result:** Silver DENIED : Performance dimension below floor.
Message: *"Your total score reaches Silver territory, but performance outcomes fall below the floor. Focus on: chaos test success rate (currently 58%), game day completion, and reducing non-prod incidents to ≤8/month."*

---

### Example 4: Non-Negotiable Failure ✗
**Application:** Analytics Dashboard | **Complexity:** Mid-Tier | **Profile:** Standard

**Total Score: 410** (Silver range), BUT:
- ✗ DR tested only annually, not quarterly (Non-Negotiable #7)
- ✗ On-call coverage: 1 person only (Non-Negotiable #8)

**Result:** Silver DENIED regardless of score. Bronze retained.
Required actions: Implement quarterly DR testing, establish 2-person on-call rotation. Re-apply in next 6-month evaluation cycle.

---

## SILVER TO GOLD TRANSITION GUIDANCE

### When to pursue Gold:
- Consistently scoring 450–500 (upper Silver range) over 6-month evaluation period
- All 10 non-negotiables solidly passing with margin
- Ready for production deployment
- Team demonstrating production-grade discipline in non-prod

### Key Shift: Silver → Gold
| Dimension | Silver Standard | Gold Standard |
|---|---|---|
| Environment | Non-Production | Production (live) |
| Performance Metrics | Non-prod incidents, chaos outcomes | Real MTTD, MTTR, prod incidents |
| Scoring | 2-Dimensional | 3-Dimensional (+ Stakeholder Experience) |
| Stakes | Practice | Live business operations |
| Chaos | Quarterly, non-prod | Monthly, production (controlled) |
| Availability | Non-prod mirroring | 99.9%+ production uptime |
| Sev 0 Rule | Not applicable | Immediate certification downgrade |

---

## FRAMEWORK VERSIONING & FUTURE-PROOFING

| Attribute | Detail |
|---|---|
| **Version** | v1.1 |
| **Effective Date** | TBD |
| **Review Cycle** | Annual |
| **Changelog** | "API Gateway Profile" → "Cascading Risk Profile"; Evaluation period updated to 6 months; Dimension Floor Rule clarified |

**Built-in flexibility:**
- Category weights adjustable in future versions
- New subcategories can be added within existing categories
- New profiles can be introduced (e.g., "AI-Native Profile", "Edge Computing Profile")
- Existing certifications honoured for 6 months after framework updates

---

*APEX Silver Certification Framework v1.1 : Non-Production Operational Maturity*   
*Builds on: APEX Bronze v1.1 : Non-Production Foundational Resilience*  
*Next Level: APEX Gold : Production Engineering Excellence*
