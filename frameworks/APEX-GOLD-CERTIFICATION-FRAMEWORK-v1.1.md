# APEX GOLD CERTIFICATION FRAMEWORK (v1.1)
**Production Environments — Engineering Excellence**

> **Changelog from v1.0:** Non-Negotiable #15 updated — Zero Sev 0 window changed from trailing 12 months to trailing 6 months. Production chaos engineering frequency updated from monthly to quarterly. Gold-to-Platinum transition table updated accordingly.

---

## FRAMEWORK OVERVIEW

| Attribute | Detail |
|---|---|
| **Target Environment** | Production (Live customer-facing systems) |
| **Philosophy** | Real-world resilience under production conditions, measurable customer impact prevention |
| **Score Range** | 501–800 points out of 1000 (50.1%–80%) |
| **Prerequisite** | Must have achieved Silver certification OR score ≥351 |
| **Scoring Dimensions** | **3-Dimensional**: Capability (40%) + Performance (40%) + Stakeholder Experience (20%) |
| **Evaluation Period** | 3 months |
| **Probation Period (PP)** | 3 months → Full Certification |
| **Performance Improvement Plan (PIP)** | 3 months |
| **Validity** | 12 months with quarterly health checks |

> **Key Shift from Silver → Gold:**
> Silver = production-ready *practices* validated in non-prod.
> Gold = those same practices *operating under live production conditions*, with real customers, real incidents, and real consequences. The stakes are no longer simulated.

---

## SCORING ARCHITECTURE (3 Dimensions)

| Dimension | Weight | Max Points | What It Measures |
|---|---|---|---|
| **Capability** | 40% | 400 pts | Tooling, processes, architecture in production |
| **Performance** | 40% | 400 pts | Real production MTTD, MTTR, incidents, DR, error budgets |
| **Stakeholder Experience** | 20% | 200 pts | Customer NPS, SRE/DevOps team confidence, business satisfaction |
| **TOTAL** | 100% | 1000 pts | |

> **Dimension Floor Rule:** A total score of 501–800 qualifies for Gold territory, but all three dimension floors must be met independently. This ensures the score reflects genuine, balanced resilience — not excellence in one pillar masking a critical weakness in another. Think of it as passing each paper individually, not just on aggregate.
> - Capability ≥200 pts
> - Performance ≥200 pts
> - Stakeholder Experience ≥120 pts
>
> Failing any single floor = No Gold Certification, regardless of total score.

---

## COMPLEXITY CLASSIFICATION (Same 8-Criteria System)

| Level | Score | Production Characteristics |
|---|---|---|
| **Simple** | 0–25 pts | Single-region, 1–3 services, Tier 3–5, low traffic |
| **Mid-Tier** | 26–50 pts | Multi-AZ, 4–10 services, Tier 2–3, moderate traffic |
| **Complex** | 51–80 pts | Multi-region, 11+ services, Tier 0–1, high traffic, mission-critical |

> **Tier Eligibility:** Tier 5 applications are ineligible for Gold certification. Gold requires Tier 0–4 applications only.

### How Tier Differentiation Works in APEX

APEX does not use tier multipliers to move the certification finish line. A Gold application always needs 501–800 points regardless of its tier. Instead, tier differentiation is built into the journey through:

1. **Complexity Classification** — Tier 0 presence automatically pushes an app to Complex via the Tier Composition criterion (3× weight, 15 pts max) — the heaviest weighted criterion in the system
2. **Profile Weights** — Complex apps have category weights amplified for their risk profile. Framework admin can adjust weights with documented justification
3. **Performance Thresholds within Categories** — Complex apps face stricter expectations across chaos success rates, incident resolution times, and monitoring coverage
4. **Non-Negotiables** — Complex apps face more demanding hard gate requirements
5. **Incident Penalties** — Severity classification hits harder on complex/high-tier apps

> **One universal finish line. Differentiation happens in how demanding the journey is to get there.**

---

## APPLICATION PROFILE ASSIGNMENT

| Profile | Key Weight Adjustments | Best Suited For |
|---|---|---|
| **High-Velocity** | Deployment Automation 2×, Chaos Engineering 1.5×, MTTR 1.5× | Frequent releases, breaking changes |
| **Stable Enterprise** | DR & BC 1.5×, Architecture 1.5×, SLO Tracking 1.5× | Infrequent releases, stability-focused |
| **Data-Intensive** | Backup & Recovery 2×, Data Resilience 1.5×, MTTD 1.5× | Complex data flows, ETL pipelines |
| **Cascading Risk** | Dependency Management 2×, Circuit Breakers 1.5×, Availability 1.5× | High external/internal dependencies with cascading failure risk |
| **Standard** | All weights 1× | Balanced, default |

Framework admin may override individual weights with documented justification.

---

## GOLD NON-NEGOTIABLES (Hard Gates)

**MUST PASS ALL 15 to qualify for Gold.**
*(Includes all 10 Silver non-negotiables, plus 5 production-specific gates)*

### Inherited from Silver (1–10)
All Bronze + Silver non-negotiables must remain satisfied.

### Production-Specific (11–15)

| # | Requirement | Simple | Mid-Tier | Complex |
|---|---|---|---|---|
| 11 | **DR tested monthly ≥90% success in production** | Monthly, full recovery validated | Monthly, all services tested | Monthly, all tiers tested, orchestrated |
| 12 | **RTO <1hr, RPO <15min — consistently achieved in production** | Validated over trailing 90 days | Per-service, trailing 90 days | Per-tier, trailing 90 days |
| 13 | **MTTD <10 min (trailing 90-day production average)** | Prod alerting <10 min avg | Per-service <10 min | Per-tier <10 min |
| 14 | **MTTR <1hr (trailing 90-day production average)** | Prod resolution <60 min avg | Per-service <60 min | Per-tier <60 min |
| 15 | **Zero Sev 0 incidents in trailing 6 months in production** | Zero | Zero | Zero |

> **Incident penalty override:** Even one Sev 0 in trailing 6 months = automatic cap at Silver, regardless of total score. Non-Negotiable #15 is the hardest gate in the Gold framework.

---

## DIMENSION 1: CAPABILITY SCORE (400 points max)

### 1. DISASTER RECOVERY & BUSINESS CONTINUITY (72 pts)

#### 1.1 DR Plan & Runbook Maturity (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Runbook version-controlled, auto-updated, DR owner assigned, tested in prod | All services, dependency-aware runbooks, orchestration scripts | Tier-by-tier orchestration, cross-tier recovery sequences, automated validation |
| 14–17 | Complete runbook, quarterly updates, tested | Most services, mostly current | Most tiers, minor gaps |
| 8–13 | Runbook exists, outdated | Partial service coverage | Partial tier coverage |
| 0–7 | Minimal or not tested in prod | Missing critical services | Missing tiers |

**Gold Minimum: 14 pts**

#### 1.2 RTO/RPO Achievement & Validation (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | RTO <30min, RPO <5min, validated monthly in prod | Per-service, validated monthly | Per-tier, validated monthly |
| 14–17 | RTO <1hr, RPO <15min, validated monthly (Gold minimum) | Per-service validated | Per-tier validated |
| 8–13 | RTO <1hr, RPO <15min, validated quarterly | Some services | Some tiers |
| 0–7 | Not consistently achieved | Not validated | Not validated |

**Gold Minimum: 14 pts (Non-Negotiable #12)**

#### 1.3 Production Backup Strategy & PITR (17 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 15–17 | Continuous replication, PITR <5min, automated restore validation weekly | Multi-region replication, PITR per service, weekly validation | Active-active data, cross-tier PITR, continuous validation |
| 11–14 | Daily backups + PITR, monthly restore validation | All stores, PITR, monthly validation | Tiered, PITR, monthly validation |
| 6–10 | Daily backups, quarterly restore tests | Most stores with PITR | Most tiers |
| 0–5 | Basic backups, inconsistent validation | Gaps | Gaps |

**Gold Minimum: 11 pts**

#### 1.4 Failover Capabilities (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 13–15 | Automated failover <5min cutover, tested monthly, multi-AZ | Per-service automated failover, cross-service coordination | Multi-region failover, tier-orchestrated, <5min per tier |
| 10–12 | Automated failover, tested quarterly | Most services automated | Most tiers automated |
| 5–9 | Semi-automated failover, manual intervention needed | Partial | Partial |
| 0–4 | Manual failover only | Manual | Manual |

**Gold Minimum: 10 pts**

---

### 2. CHAOS ENGINEERING & RESILIENCE TESTING (80 pts)

#### 2.1 Production Chaos Engineering (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | Quarterly controlled chaos in prod, automated rollback, safety gates, results tracked and acted on | Quarterly multi-service production chaos, blast radius controlled, findings feed improvement backlog | Quarterly multi-tier prod chaos, tier-aware safety controls, cross-tier scenarios |
| 18–22 | Quarterly prod chaos (controlled), manual rollback (Gold minimum) | Quarterly, partial service coverage | Quarterly, partial tier coverage |
| 11–17 | Bi-annual prod chaos | Bi-annual | Bi-annual |
| 0–10 | Non-prod only or ad-hoc | Non-prod only | Non-prod only |

**Gold Minimum: 18 pts (quarterly production chaos mandatory)**

#### 2.2 Chaos Coverage & Failure Scenario Sophistication (30 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 27–30 | >85% component coverage, advanced: data corruption, dependency cascades, region failure | >80% service coverage, network partitions, DB failure, traffic surge | >75% tier coverage, cross-tier cascades, region failover, data plane failures |
| 20–26 | 70–85% coverage, latency/restart/dependency scenarios | 65–80%, multi-service scenarios | 60–75%, multi-tier scenarios |
| 12–19 | 50–70% coverage, basic scenarios | 50–65% | 50–60% |
| 0–11 | <50% coverage | <50% | <50% |

**Gold Minimum: 20 pts**

#### 2.3 Game Day Frequency, Scope & Exec Involvement (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | Quarterly game days, cross-functional, customer-impact scenarios, leadership debrief | Quarterly, multi-team, business scenarios, exec sponsor | Quarterly, multi-tier, exec participation, business impact modeling |
| 18–22 | Quarterly, cross-functional (Gold minimum) | Quarterly, good team participation | Quarterly, multi-tier coordination |
| 10–17 | Bi-annual game days | Bi-annual | Bi-annual |
| 0–9 | Annual or infrequent | Annual | Annual |

**Gold Minimum: 18 pts**

---

### 3. INCIDENT MANAGEMENT & RESPONSE (88 pts)

#### 3.1 Production Runbooks & Escalation (22 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 20–22 | Auto-triggered runbooks on alert, real-time update, exec notification templates | Service-specific, auto-triggered, war room protocols | Tier-specific, incident command structure, cross-tier coordination playbooks |
| 16–19 | Comprehensive production runbooks, tested quarterly, clear escalation (Gold minimum) | Per-service runbooks tested | Per-tier runbooks tested |
| 10–15 | Good runbooks, bi-annual testing | Most services | Most tiers |
| 0–9 | Basic or outdated | Incomplete | Incomplete |

**Gold Minimum: 16 pts**

#### 3.2 On-Call & Follow-the-Sun Coverage (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Follow-the-sun OR 24/7 on-call, intelligent alert routing, handoff ceremonies | Per-service 24/7 coverage, intelligent routing, load balancing | Tier-specific 24/7, cross-tier escalation, incident commanders identified |
| 14–17 | 3+ person rotation, 24/7 pager coverage (Gold minimum) | 3+ per service, 24/7 | Tier coverage 24/7 |
| 8–13 | 2-person rotation, gaps in coverage | 2+ per service | Partial tier coverage |
| 0–7 | Business-hours only or ad-hoc | Unclear | Unclear |

**Gold Minimum: 14 pts**

#### 3.3 Auto-Remediation Coverage (25 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 23–25 | >60% incident types auto-remediated in prod (restart, scale-out, failover, rollback) | >55% auto-remediation, pattern library maintained | >50% auto-remediation, tier-aware healing |
| 18–22 | 40–60% auto-remediation (Gold minimum) | 35–55% | 30–50% |
| 10–17 | 20–40% auto-remediation | 20–35% | 20–30% |
| 0–9 | <20% | <20% | <20% |

**Gold Minimum: 18 pts**

#### 3.4 Post-Incident Reviews — Blameless Culture (21 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 19–21 | All Sev 0–2 PIRs within 24hrs, blameless, action items with SLA, pattern library, cross-org sharing | All Sev 0–2, cross-service pattern analysis, feedback to chaos program | All Sev 0–2, cross-tier learnings, feeds architecture decisions |
| 15–18 | All Sev 0–2 PIRs, blameless, tracked action items (Gold minimum) | All Sev 0–2, action tracking | All Sev 0–2, action tracking |
| 9–14 | Sev 0–1 PIRs, basic tracking | Sev 0–2 inconsistent | Sev 0–2 inconsistent |
| 0–8 | Inconsistent PIRs | Rare | Rare |

**Gold Minimum: 15 pts**

---

### 4. OBSERVABILITY & DETECTION (72 pts)

#### 4.1 Full-Stack Production Monitoring (24 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 22–24 | 95%+ coverage — infra, app, business metrics, user journeys, dependency health | 95%+ all services, real-time business KPI dashboards | 90%+ all tiers, cross-tier topology maps, real-time business dashboards |
| 17–21 | 85–95% coverage, business metrics included (Gold minimum) | 85–95% all services | 85–90% all tiers |
| 10–16 | 70–85% coverage | 70–85% | 70–85% |
| 0–9 | <70% or missing business metrics | <70% | <70% |

**Gold Minimum: 17 pts**

#### 4.2 Distributed Tracing & Correlation (18 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 16–18 | 90%+ trace coverage, auto-correlation, anomaly detection, <1min correlation | All services traced, auto-correlation, ML-assisted | All tiers traced, cross-tier correlation, intelligent root cause suggestion |
| 12–15 | 75%+ trace coverage, correlation IDs, basic anomaly detection (Gold minimum) | 75%+ services, correlation across services | 70%+ tier coverage, basic cross-tier correlation |
| 7–11 | 50–75% trace coverage | 50–75% | 50–70% |
| 0–6 | <50% or no distributed tracing | <50% | <50% |

**Gold Minimum: 12 pts**

#### 4.3 SLI/SLO/Error Budget Management (18 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 16–18 | 8+ SLIs, SLOs enforced, error budget burn rate alerts, automated freeze on budget exhaustion | Per-service SLIs/SLOs (5+ per service), cross-service budget rollup | Per-tier SLIs/SLOs, cross-tier budget cascade, automated escalation |
| 12–15 | 5+ SLIs, SLOs enforced, error budgets tracked (Gold minimum) | Per-service (4+ minimum), budgets tracked | Per-tier (4+ minimum), budgets tracked |
| 7–11 | 3–5 SLIs, basic SLO tracking | Partial service coverage | Partial tier coverage |
| 0–6 | <3 SLIs or not enforced | Minimal | Minimal |

**Gold Minimum: 12 pts**

#### 4.4 Production Alerting Quality & AIOps (12 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 11–12 | <5% false positives, ML-tuned, predictive alerts, auto-enriched, AIOps platform | <5% false positives, service-level predictive alerting | <8% false positives, tier-aware predictive alerting |
| 8–10 | <10% false positives, ML-assisted (Gold minimum) | <10% false positives | <12% false positives |
| 5–7 | <20% false positives | <20% | <20% |
| 0–4 | >20% false positives | >20% | >20% |

**Gold Minimum: 8 pts**

---

### 5. AUTOMATION & SELF-HEALING (44 pts)

#### 5.1 Infrastructure as Code — Production (16 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 14–16 | 95%+ IaC, immutable infrastructure, automated drift detection & correction, policy-as-code | 90%+ all services, env parity enforced, automated compliance | 85%+ all tiers, tier templates, policy gates in pipeline |
| 10–13 | 80–95% IaC, drift detection (Gold minimum) | 80–90%, drift detection | 75–85%, drift detection |
| 6–9 | 60–80% IaC | 60–80% | 60–75% |
| 0–5 | <60% | <60% | <60% |

**Gold Minimum: 10 pts**

#### 5.2 Progressive Delivery & Zero-Downtime Deployment (18 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 16–18 | Blue-green or canary in prod, automated rollback <3min, feature flags, AI-validated deployment gates | All services progressive delivery, automated rollback, canary analysis | Tier-orchestrated deployments, automated rollback per tier, canary at each tier |
| 12–15 | Blue-green/canary in prod, automated rollback (Gold minimum) | All services, automated rollback | Orchestrated, automated rollback |
| 7–11 | Automated deployment, manual rollback | Most services automated | Most tiers automated |
| 0–6 | Manual or basic automation | Inconsistent | Inconsistent |

**Gold Minimum: 12 pts**

#### 5.3 Self-Healing & Auto-Scaling in Production (10 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 9–10 | Predictive auto-scaling, self-healing for top 5 failure patterns, AI-driven capacity planning | Predictive scaling per service, healing covers 60%+ patterns | Tier-aware predictive scaling, tiered healing strategies |
| 7–8 | Reactive auto-scaling, self-healing for common patterns (Gold minimum) | Reactive scaling all services | Tier-aware reactive scaling |
| 4–6 | Basic auto-scaling, some self-healing | Partial service coverage | Partial tier coverage |
| 0–3 | Manual scaling only | Manual | Manual |

**Gold Minimum: 7 pts**

---

### 6. ARCHITECTURE & DESIGN RESILIENCE (24 pts)

#### 6.1 Production Redundancy & High Availability (10 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 9–10 | Multi-region active-active, zero-downtime failover, traffic shaping | Multi-AZ + DR region, active-active for critical paths | Active-active multi-region, tier-specific HA strategies |
| 7–8 | Multi-AZ + DR region, automated failover (Gold minimum — Tier 0–2 required) | Multi-AZ all services, DR region | Multi-AZ all tiers |
| 4–6 | Multi-AZ, manual DR | Most services multi-AZ | Most tiers multi-AZ |
| 0–3 | Single AZ or single region | Single region | Single region |

**Gold Minimum: 7 pts (Multi-AZ mandatory for Tier 0–2)**

#### 6.2 Dependency Resilience — Circuit Breakers & Bulkheads (8 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 7–8 | Circuit breakers + bulkheads + rate limiting on all external dependencies, chaos-validated | Per-service circuit breakers, adaptive throttling, fallback chains | Tier-level bulkheads, cross-tier isolation, blast radius proven via chaos |
| 5–6 | Circuit breakers on critical paths, tested (Gold minimum) | Most services, tested | Most tiers, tested |
| 3–4 | Circuit breakers exist, not tested | Some services | Some tiers |
| 0–2 | Minimal or none | None | None |

**Gold Minimum: 5 pts**

#### 6.3 Data Resilience — Multi-Region & Integrity (6 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 5–6 | Multi-region replication, automated integrity checks, PITR <5min, validated | All data stores multi-region, integrity checks | Active-active data, cross-tier consistency, continuous integrity validation |
| 3–4 | Cross-AZ replication, PITR, monthly validation (Gold minimum) | Most stores replicated | Most tiers replicated |
| 1–2 | Single-region replication | Limited replication | Limited |
| 0 | No replication | None | None |

**Gold Minimum: 3 pts**

---

### 7. CULTURE & ORGANIZATIONAL MATURITY (20 pts)

#### 7.1 Dedicated Resilience Engineering Function (8 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 7–8 | Dedicated SRE/Resilience team embedded in squads, exec sponsorship, quarterly resilience reviews with leadership |
| 5–6 | Resilience champions per squad, bi-annual exec reviews (Gold minimum) |
| 3–4 | Resilience champions identified, periodic reviews |
| 0–2 | No dedicated function |

**Gold Minimum: 5 pts**

#### 7.2 Resilience Training & Certification (6 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 5–6 | Quarterly training, chaos engineering certifications, incident commander certifications, cross-team exercises |
| 3–4 | Bi-annual training, certifications encouraged (Gold minimum) |
| 1–2 | Annual training |
| 0 | Ad-hoc only |

**Gold Minimum: 3 pts**

#### 7.3 Continuous Improvement & Feedback Loops (6 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 5–6 | Monthly resilience metrics review, chaos findings feed architecture decisions, error budget policy enforced, OKRs tied to resilience |
| 3–4 | Quarterly reviews, chaos findings acted on, basic OKRs (Gold minimum) |
| 1–2 | Semi-annual reviews, reactive improvements |
| 0 | No structured improvement cycle |

**Gold Minimum: 3 pts**

---

### CAPABILITY SCORE SUMMARY

| Category | Base Points |
|---|---|
| DR & Business Continuity | 72 pts |
| Chaos Engineering | 80 pts |
| Incident Management | 88 pts |
| Observability & Detection | 72 pts |
| Automation & Self-Healing | 44 pts |
| Architecture & Design | 24 pts |
| Culture & Org Maturity | 20 pts |
| **TOTAL** | **400 pts** |

---

## DIMENSION 2: PERFORMANCE SCORE (400 points max)

> Performance is measured in *production* with real incidents, real customer impact, and real operational metrics. All metrics use trailing 90-day averages unless otherwise stated.

---

### 1. PRODUCTION INCIDENT PERFORMANCE (160 pts)

#### 1.1 Production MTTD — Mean Time to Detect (50 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 45–50 | <2 min average | <3 min average | <5 min average |
| 35–44 | 2–5 min | 3–7 min | 5–10 min |
| 20–34 | 5–10 min (Gold minimum) | 7–10 min (Gold minimum) | 10–15 min (Gold minimum) |
| 0–19 | >10 min | >10 min | >15 min |

**Gold Minimum: 20 pts (Non-Negotiable #13)**

#### 1.2 Production MTTR — Mean Time to Resolve (50 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 45–50 | <10 min average | <15 min average | <20 min average |
| 35–44 | 10–20 min | 15–30 min | 20–40 min |
| 20–34 | 20–60 min (Gold minimum) | 30–60 min (Gold minimum) | 40–60 min (Gold minimum) |
| 0–19 | >60 min | >60 min | >60 min |

**Gold Minimum: 20 pts (Non-Negotiable #14)**

#### 1.3 Production Incident Severity Profile (60 pts) × Profile Weight

| Points | Sev 0 (trailing 6mo) | Sev 1 (trailing 12mo) | Sev 2 (trailing 3mo) |
|---|---|---|---|
| 54–60 | 0 | 0 | 0–1 |
| 40–53 | 0 | 0–1 | 2–3 |
| 25–39 | 0 | 2 | 4–6 |
| 0–24 | 0 | 3+ | 7+ |

> **Hard rule:** Any single Sev 0 incident in trailing 6 months = immediate cap at Silver (Non-Negotiable #15). Sev 0 rows do not exist in Gold scoring.

**Gold Minimum: 25 pts**

---

### 2. PRODUCTION DR & AVAILABILITY PERFORMANCE (80 pts)

#### 2.1 DR Test Success Rate in Production (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 32–35 | >95% success, monthly, fully automated | >95% success, all services | >92% success, all tiers |
| 24–31 | 90–95% success, monthly (Gold minimum) | 90–95% all services | 88–92% all tiers |
| 14–23 | 80–90% success | 80–90% | 80–88% |
| 0–13 | <80% or quarterly only | <80% | <80% |

**Gold Minimum: 24 pts (Non-Negotiable #11)**

#### 2.2 Production Uptime / Availability (25 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 23–25 | ≥99.99% uptime (trailing 90 days) |
| 17–22 | 99.9%–99.99% (Gold minimum) |
| 10–16 | 99.5%–99.9% |
| 0–9 | <99.5% |

**Gold Minimum: 17 pts (99.9%+ required)**

#### 2.3 Error Budget Compliance (20 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 18–20 | Error budget ≥80% remaining consistently, burns managed proactively, freeze policy enforced |
| 13–17 | Error budget ≥60% remaining, burns tracked, policy exists (Gold minimum) |
| 7–12 | Error budget 40–60% remaining, some tracking |
| 0–6 | Error budget frequently exhausted or not tracked |

**Gold Minimum: 13 pts**

> **Error Budget Escalation Policy:**
> - **Stage 1 — Score Deduction:** Error budget exhausted in any single month → –75 pts applied immediately
> - **Stage 2 — PIP Triggered:** Error budget exhausted for 2+ consecutive months → PIP initiated
> - **Score Restoration:** If root cause is addressed and validated within the PP/PIP window, the deducted points are restored. Standard PP/PIP policies apply.

---

### 3. CHAOS ENGINEERING PRODUCTION OUTCOMES (80 pts)

#### 3.1 Production Chaos Test Success Rate (40 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 36–40 | >90% tests pass, graceful recovery | >88% success | >85% success |
| 27–35 | 80–90% (Gold minimum) | 78–88% (Gold minimum) | 75–85% (Gold minimum) |
| 16–26 | 65–80% | 65–78% | 60–75% |
| 0–15 | <65% | <65% | <60% |

**Gold Minimum: 27 pts**

#### 3.2 Blast Radius Proven in Production (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Zero cross-component cascade in prod chaos, circuit breakers proven | Zero cross-service cascade, graceful degradation verified | Zero cross-tier cascade, tier isolation proven |
| 13–17 | Minimal cascade (1 component), contained quickly (Gold minimum) | 1–2 services, controlled | 1 tier, controlled |
| 7–12 | Moderate cascade, manually contained | Multiple services | Multiple tiers |
| 0–6 | Widespread cascade | Widespread | Widespread |

**Gold Minimum: 13 pts**

#### 3.3 Recovery Time in Production Chaos (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Recovery <3 min in prod chaos | <5 min | <10 min |
| 13–17 | 3–8 min (Gold minimum) | 5–12 min (Gold minimum) | 10–20 min (Gold minimum) |
| 7–12 | 8–20 min | 12–30 min | 20–40 min |
| 0–6 | >20 min | >30 min | >40 min |

**Gold Minimum: 13 pts**

---

### 4. DEPLOYMENT & RELEASE PERFORMANCE (80 pts)

#### 4.1 Production Deployment Success Rate (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 32–35 | >99.5% success | >99% | >98% |
| 24–31 | 98–99.5% | 97–99% | 96–98% |
| 14–23 | 95–98% (Gold minimum) | 94–97% (Gold minimum) | 92–96% (Gold minimum) |
| 0–13 | <95% | <94% | <92% |

**Gold Minimum: 24 pts**

#### 4.2 Mean Time to Deploy & Release Frequency (25 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 23–25 | Deployment pipeline <10 min end-to-end, multiple deployments per day capable |
| 17–22 | Pipeline <20 min, daily deployment capable (Gold minimum) |
| 10–16 | Pipeline <45 min, weekly capable |
| 0–9 | >45 min or infrequent releases |

**Gold Minimum: 17 pts**

#### 4.3 Production Rollback Speed & Zero-Downtime Compliance (20 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 18–20 | Automated rollback <2 min, zero-downtime validated, tested monthly |
| 13–17 | Rollback <5 min, zero-downtime achieved (Gold minimum) |
| 7–12 | Rollback <10 min, brief downtime acceptable |
| 0–6 | Rollback >10 min or causes downtime |

**Gold Minimum: 13 pts**

---

### PERFORMANCE SCORE SUMMARY

| Category | Base Points |
|---|---|
| Production Incident Performance | 160 pts |
| Production DR & Availability | 80 pts |
| Chaos Engineering Production Outcomes | 80 pts |
| Deployment & Release Performance | 80 pts |
| **TOTAL** | **400 pts** |

---

## DIMENSION 3: STAKEHOLDER EXPERIENCE SCORE (200 points max)

> Capability + Performance can look strong on paper while customer sentiment and team confidence tell a different story. Dimension 3 captures the human signal that numbers alone cannot.

> **Survey Administration:** All stakeholder surveys are anonymous and administered independently by the framework admin to ensure integrity and prevent bias. Surveys are conducted quarterly.

---

### 1. CUSTOMER EXPERIENCE (100 pts)

#### 1.1 Net Promoter Score (NPS) or Equivalent (40 pts) × Profile Weight

| Points | NPS Range | Signal |
|---|---|---|
| 36–40 | ≥70 | Customers are active promoters |
| 27–35 | 50–69 (Gold minimum) | Positive sentiment, room to grow |
| 16–26 | 30–49 | Neutral — resilience gaps visible to customers |
| 0–15 | <30 | Customers experiencing visible reliability issues |

**Gold Minimum: 27 pts (NPS ≥50 required)**

#### 1.2 Customer-Impacting Incident Rate (30 pts) × Profile Weight

| Points | Trailing 90 days |
|---|---|
| 27–30 | Zero customer-facing incidents |
| 20–26 | 1–2 low-impact incidents, <5 min customer impact each |
| 12–19 | 3–5 incidents, managed proactively (Gold minimum) |
| 0–11 | >5 incidents or extended customer impact |

**Gold Minimum: 12 pts**

#### 1.3 Proactive Customer Communication & Transparency (15 pts) × Profile Weight

| Points | Behaviour |
|---|---|
| 13–15 | Status page updated in real-time, proactive comms before complaints, post-incident summaries published |
| 10–12 | Status page active, comms within 15 min of incident, summary published (Gold minimum) |
| 5–9 | Status page exists, comms reactive |
| 0–4 | No status page or comms only after escalation |

**Gold Minimum: 10 pts**

#### 1.4 Customer Feedback on Reliability (15 pts) × Profile Weight

| Points | Practice |
|---|---|
| 13–15 | Structured reliability feedback loop (surveys + usage analytics + support ticket analysis), actioned quarterly |
| 10–12 | Quarterly reliability surveys, results acted on (Gold minimum) |
| 5–9 | Ad-hoc feedback only |
| 0–4 | No feedback mechanism |

**Gold Minimum: 10 pts**

---

### 2. SRE / DEVOPS TEAM CONFIDENCE (60 pts)

#### 2.1 On-Call Toil & Operational Burden (25 pts) × Profile Weight

| Points | Signal |
|---|---|
| 23–25 | <20% on-call time spent on toil, >80% incidents auto-handled, team reports high confidence |
| 17–22 | 20–40% toil, >60% auto-handled (Gold minimum) |
| 10–16 | 40–60% toil, team frequently overwhelmed |
| 0–9 | >60% toil, team in constant reactive mode |

**Gold Minimum: 17 pts**

#### 2.2 Team Confidence in Deployment Safety (20 pts) × Profile Weight

| Points | Signal |
|---|---|
| 18–20 | Team deploys without fear at any time, canary + automated rollback gives full confidence, no deployment freezes |
| 13–17 | Maintenance windows rare, team confident in most deployments (Gold minimum) |
| 7–12 | Deployment anxiety present, change freezes used frequently |
| 0–6 | Frequent deployment-related incidents, team reluctant to release |

**Gold Minimum: 13 pts**

#### 2.3 SRE / Team Satisfaction Survey Score (15 pts) × Profile Weight

| Points | Score (Anonymous quarterly survey — 1–10 scale) |
|---|---|
| 13–15 | Average ≥8.5 — "We trust our systems" |
| 10–12 | Average 7.0–8.4 (Gold minimum) |
| 5–9 | Average 5.0–6.9 — team under stress |
| 0–4 | Average <5.0 — team confidence crisis |

**Gold Minimum: 10 pts**

---

### 3. BUSINESS STAKEHOLDER CONFIDENCE (40 pts)

#### 3.1 Business Leadership Confidence Score (20 pts) × Profile Weight

| Points | Signal |
|---|---|
| 18–20 | Quarterly resilience review with exec sponsor, leadership reports confidence, resilience tied to business OKRs |
| 13–17 | Bi-annual exec review, leadership aware of resilience posture (Gold minimum) |
| 7–12 | Annual review, leadership aware but passive |
| 0–6 | No exec engagement |

**Gold Minimum: 13 pts**

#### 3.2 Incident Business Impact Score (20 pts) × Profile Weight

| Points | Trailing 90 days |
|---|---|
| 18–20 | Zero business-impacting incidents (revenue loss, SLA breach, regulatory risk) |
| 13–17 | 1 minor business impact, no SLA breach, no regulatory issue (Gold minimum) |
| 7–12 | 2–3 business impacts, at least one SLA breach |
| 0–6 | >3 impacts, or regulatory notification triggered |

**Gold Minimum: 13 pts**

---

### STAKEHOLDER EXPERIENCE SCORE SUMMARY

| Category | Base Points |
|---|---|
| Customer Experience | 100 pts |
| SRE / DevOps Team Confidence | 60 pts |
| Business Stakeholder Confidence | 40 pts |
| **TOTAL** | **200 pts** |

---

## GOLD CERTIFICATION REQUIREMENTS

### Score Requirements

| Dimension | Floor (Min Required) | Max Available |
|---|---|---|
| Capability Score | ≥200 pts | 400 pts |
| Performance Score | ≥200 pts | 400 pts |
| Stakeholder Experience | ≥120 pts | 200 pts |
| **Total Score** | **501–800 pts** | **1000 pts** |

> All three dimension floors must be met independently. A strong total score does not compensate for a floor failure in any single dimension.

### Incident-Based Dynamic Recertification

| Incident Event | Consequence | Restoration |
|---|---|---|
| 1× Sev 0 in trailing 6 months | Immediate downgrade to Silver + 90-day probation | Gold re-eligibility after 6 months from incident date |
| 3+ Sev 1 in trailing 12 months | –100 pts + recertification review triggered | Score restored if root cause fixed and validated within PP/PIP window |
| SLA breach (customer-facing) | –50 pts + PIP triggered | Score restored if root cause fixed and validated within PP/PIP window |
| Error budget exhausted (1 month) | –75 pts (Stage 1) | Score restored if resolved and validated |
| Error budget exhausted (2+ consecutive months) | PIP triggered (Stage 2) | Score restored upon PIP completion and validation |

> **Score Restoration Principle:** Penalties are not permanent. If the root cause is identified, fixed, and validated by the framework admin within the active PP/PIP window, the deducted points are restored. Standard PP/PIP timelines and check-in policies apply throughout.

---

## CERTIFICATION PROCESS

```
Step 1: Silver Validation
  → Confirm active Silver certification or score ≥351

Step 2: Non-Negotiables Gate Check (15 total)
  → ALL must pass → Proceed to scoring
  → ANY failure → No Gold, remediation required

Step 3: 3-Dimensional Scoring
  → Capability assessment (400 pts max)
  → Performance assessment (400 pts max, trailing 90 days)
  → Stakeholder surveys + metrics (200 pts max, anonymous, admin-administered)

Step 4: Dimension Floor Check
  → Capability ≥200?        ✓/✗
  → Performance ≥200?       ✓/✗
  → Stakeholder ≥120?       ✓/✗
  → All pass → Proceed

Step 5: Total Score Check
  → 501–800 → Provisional Gold
  → <501    → Below threshold
  → >800    → Consider Platinum path

Step 6: Award "APEX Gold (Provisional)"
  → 3-month Probation Period begins
  → Monthly health checks with framework admin

Step 7: Full Certification
  → All 15 non-negotiables still passing?
  → Score ≥501 with all dimension floors met?
  → Zero Sev 0 incidents during probation?
  → Award "APEX Gold Certified"
  → Valid 12 months / 3-month evaluation cycle
```

---

## PROBATION PERIOD (PP) & PERFORMANCE IMPROVEMENT PLAN (PIP)

### Probation Period — 3 Months
- **Status:** APEX Gold (Provisional)
- Maintain all 15 non-negotiables
- No Sev 0 incidents during probation
- All dimension floors maintained
- Monthly health checks with framework admin
- **Outcome:** ✅ Full Gold Certified | ❌ Extend PP (once) or downgrade to Silver

### Performance Improvement Plan — 3 Months
Triggered by:
- Total score drops below 501
- Any dimension floor fails
- Any non-negotiable fails
- Sev 0 incident in production
- Error budget exhausted 2+ consecutive months

- **Status:** APEX Gold (PIP)
- Bi-weekly reviews with framework admin
- Documented remediation plan with milestones
- Business sponsor notified
- **Outcome:** ✅ Return to Gold Certified | ❌ Certification revoked → Silver

---

## CERTIFICATION DISPLAY

```
═══════════════════════════════════════════════════════════
    ██████  APEX RESILIENCE FRAMEWORK
   ██   ██  GOLD CERTIFIED  (v1.1)
   ██   ██
    ██████  Application:   Payment Gateway Service
            Complexity:    Complex (Tier 0)
            Profile:       High-Velocity

            Capability:    335/400  (83.8%)
            Performance:   298/400  (74.5%)
            Stakeholder:   152/200  (76.0%)

            TOTAL SCORE:   785/1000 (78.5%)

            Certified:     March 1, 2025
            Valid Through: February 28, 2026
            Next Review:   June 1, 2025
═══════════════════════════════════════════════════════════
```

---

## EXAMPLE SCORING SCENARIOS

### Example 1: Mid-Tier App — Gold Denied (Stakeholder Floor) ✗
**Application:** E-Commerce Platform | **Complexity:** Mid-Tier | **Profile:** Standard

| Dimension | Score |
|---|---|
| Capability | 205/400 |
| Performance | 210/400 |
| Stakeholder | 100/200 ← Below floor |
| **Total** | **515/1000** |

**Result:** Gold DENIED — Stakeholder floor not met despite total of 515.
Message: *"Strong capability and performance, but stakeholder experience falls below the ≥120 floor. Focus on: NPS improvement, proactive customer communication, and SRE satisfaction scores."*

---

### Example 2: Mid-Tier App — Gold Certified (620 pts) ✅
**Application:** E-Commerce Platform (6 months later) | **Complexity:** Mid-Tier | **Profile:** Standard

| Dimension | Score |
|---|---|
| Capability | 225/400 |
| Performance | 245/400 |
| Stakeholder | 150/200 |
| **Total** | **620/1000** |

**Non-Negotiables:** ✅ All 15 passed
**Result:** APEX Gold (Provisional) → Gold Certified

---

### Example 3: Complex Tier 0 — Strong Gold (742 pts) ✅
**Application:** Banking Payment System | **Complexity:** Complex | **Profile:** Stable Enterprise

| Dimension | Score |
|---|---|
| Capability | 310/400 |
| Performance | 285/400 |
| Stakeholder | 147/200 |
| **Total** | **742/1000** |

**Non-Negotiables:** ✅ All 15 passed
**Result:** Gold Certified (approaching Platinum territory)

---

### Example 4: Sev 0 Incident Override ✗
**Application:** Retail Checkout | **Total Score:** 620 (Gold range)

Had 1 Sev 0 incident 4 months ago in production (within trailing 6 months).

**Result:** Capped at Silver — Non-Negotiable #15 override.
Gold re-application eligible 6 months from incident date.

---

## GOLD TO PLATINUM TRANSITION GUIDANCE

### When to pursue Platinum:
- Consistently scoring 760–800+ over the 3-month evaluation period
- All 15 non-negotiables solidly passing for 12+ months
- Zero Sev 0 in trailing 12 months AND Zero Sev 1 in trailing 6 months
- Stakeholder scores consistently ≥150/200
- AI-driven chaos engineering capability in place or in active development
- Auto-remediation exceeding 60% and trending toward 80%+
- SRE team toil <20% consistently

### Key Gaps: Gold → Platinum

| Dimension | Gold Standard | Platinum Standard |
|---|---|---|
| Chaos Engineering | Quarterly controlled prod chaos | AI-driven, always-on continuous chaos |
| MTTD | <10 min | <2 min |
| MTTR | <1 hr | <15 min |
| Availability | 99.9%+ | 99.99%+ |
| Sev 0 Gate | Zero in trailing 6 months | Zero in trailing 12 months |
| Sev 1 Gate | ≤2 per year | Zero in trailing 6 months |
| Auto-Remediation | 40–60% | 80%+ (non-negotiable) |
| NPS | ≥50 | ≥70 |
| Stakeholder Floor | ≥120/200 | ≥150/200 |
| Tier Eligibility | Tier 0–4 | Tier 0–3 only |
| Game Days | Quarterly full | Monthly micro + quarterly full |

---

## FRAMEWORK VERSIONING & FUTURE-PROOFING

| Attribute | Detail |
|---|---|
| **Version** | v1.1 |
| **Effective Date** | TBD |
| **Review Cycle** | Annual |
| **Changelog** | Sev 0 trailing window changed from 12 to 6 months (Non-Negotiable #15). Production chaos frequency changed from monthly to quarterly. Gold-to-Platinum transition table updated. |

**Built-in flexibility:**
- Category weights adjustable in future versions
- New subcategories can be added within existing categories without restructuring
- New profiles can be introduced (e.g., "AI-Native Profile", "Edge Computing Profile")
- Existing certifications honoured for 6 months after framework updates
- Grandfathering clause: certifications valid at time of framework update remain in force until next annual re-certification

---

*APEX Gold Certification Framework v1.1 — Production Engineering Excellence*
*Builds on: APEX Bronze v1.1 (Non-Prod Foundational) | APEX Silver v1.1 (Non-Prod Advanced)*
*Next: APEX Platinum v1.0 — Autonomous Resilience*