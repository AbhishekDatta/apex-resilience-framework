# APEX PLATINUM CERTIFICATION FRAMEWORK (v1.0)
**Production Environments — Autonomous Resilience**

---

## FRAMEWORK OVERVIEW

| Attribute | Detail |
|---|---|
| **Target Environment** | Production (Live customer-facing systems — elite tier) |
| **Philosophy** | Autonomous resilience — AI-driven, self-healing, always-on chaos, near-zero human intervention for common failure patterns. Platinum is not just a score — it is a declaration of operational excellence that the industry can benchmark against. |
| **Score Range** | 801–1000 points out of 1000 (80.1%–100%) |
| **Prerequisite** | Must have achieved Gold certification OR score ≥501 |
| **Scoring Dimensions** | **3-Dimensional**: Capability (40%) + Performance (40%) + Stakeholder Experience (20%) |
| **Evaluation Period** | 3 months |
| **Probation Period (PP)** | 3 months → Full Certification |
| **Performance Improvement Plan (PIP)** | 3 months |
| **Validity** | 12 months with monthly health checks |
| **Tier Eligibility** | Tier 0, 1, 2 and 3 only — Tier 4 and Tier 5 are ineligible |

> **Key Shift from Gold → Platinum:**
> Gold = engineering excellence with controlled, periodic resilience practices.
> Platinum = **autonomous resilience** — the system defends itself. AI drives chaos, detects anomalies before they become incidents, heals automatically, and the team's role shifts from firefighting to continuous improvement. Platinum organisations don't just survive failures — they are designed to make failures inconsequential.

---

## SCORING ARCHITECTURE (3 Dimensions)

| Dimension | Weight | Max Points | What It Measures |
|---|---|---|---|
| **Capability** | 40% | 400 pts | Advanced tooling, autonomous processes, AI-native architecture |
| **Performance** | 40% | 400 pts | Real production metrics at elite thresholds — MTTD, MTTR, zero serious incidents, error budgets |
| **Stakeholder Experience** | 20% | 200 pts | Customer delight, SRE team confidence at scale, business leadership alignment |
| **TOTAL** | 100% | 1000 pts | |

> **Dimension Floor Rule:** A total score of 801–1000 qualifies for Platinum territory, but all three dimension floors must be met independently. Think of it as passing each paper individually, not just on aggregate.
> - Capability ≥200 pts
> - Performance ≥200 pts
> - Stakeholder Experience ≥150 pts
>
> Failing any single floor = No Platinum Certification, regardless of total score.

---

## COMPLEXITY CLASSIFICATION (Same 8-Criteria System)

| Level | Score | Production Characteristics |
|---|---|---|
| **Simple** | 0–25 pts | Single-region, 1–3 services, Tier 3, low-moderate traffic |
| **Mid-Tier** | 26–50 pts | Multi-AZ, 4–10 services, Tier 2–3, moderate-high traffic |
| **Complex** | 51–80 pts | Multi-region, 11+ services, Tier 0–1, high traffic, mission-critical |

> **Tier Eligibility:** Platinum is available to Tier 0, 1, 2 and 3 applications only. Tier 4 and Tier 5 applications are ineligible — the investment required to operate at Platinum standard is disproportionate to the business criticality of these tiers.

### How Tier Differentiation Works in APEX

APEX does not use tier multipliers to move the certification finish line. A Platinum application always needs 801–1000 points regardless of its tier. Tier differentiation is built into the journey through:

1. **Complexity Classification** — Tier 0 presence automatically pushes an app to Complex via the Tier Composition criterion (3× weight, 15 pts max)
2. **Profile Weights** — Complex apps have category weights amplified for their risk profile. Framework admin can adjust weights with documented justification
3. **Performance Thresholds within Categories** — Complex apps face the most demanding expectations at Platinum level
4. **Non-Negotiables** — The most stringent hard gates in the APEX framework
5. **Incident Penalties** — Any serious incident at Platinum level triggers immediate and severe consequences

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

## PLATINUM NON-NEGOTIABLES (Hard Gates)

**MUST PASS ALL 20 to qualify for Platinum.**
*(Includes all 15 Gold non-negotiables, plus 5 Platinum-specific gates)*

### Inherited from Gold (1–15)
All Bronze + Silver + Gold non-negotiables must remain satisfied, with the following Gold gates tightened for Platinum:

| # | Gold Requirement | Platinum Tightening |
|---|---|---|
| 11 | DR tested monthly ≥90% success | DR tested weekly ≥95% success with automated validation |
| 12 | RTO <1hr, RPO <15min | RTO <15min, RPO <5min consistently achieved |
| 13 | MTTD <10 min trailing 90-day avg | MTTD <2 min trailing 90-day avg |
| 14 | MTTR <1hr trailing 90-day avg | MTTR <15 min trailing 90-day avg |
| 15 | Zero Sev 0 in trailing 6 months | Zero Sev 0 in trailing 12 months |

### Platinum-Specific (16–20)

| # | Requirement | Simple | Mid-Tier | Complex |
|---|---|---|---|---|
| 16 | **Zero Sev 1 incidents in trailing 6 months** | Zero | Zero | Zero |
| 17 | **AI-driven continuous chaos engineering active in production** | Always-on chaos, AI-generated scenarios | Multi-service continuous chaos, AI scenario generation | Multi-tier continuous chaos, AI-driven blast radius prediction |
| 18 | **Auto-remediation ≥80% of incident types in production** | ≥80% auto-remediated | ≥80% across services | ≥80% across tiers |
| 19 | **NPS ≥70 or equivalent customer satisfaction metric** | Validated quarterly | Validated quarterly | Validated quarterly |
| 20 | **Active-active multi-region deployment (Tier 0–1 apps)** | N/A for Simple/Tier 3 | Active-active for critical paths | Full active-active multi-region |

> **Incident override — Platinum's zero-tolerance standard:**
> - 1× Sev 0 in trailing 12 months → Immediate downgrade to Silver + 12-month bar from Platinum re-application
> - 1× Sev 1 in trailing 6 months → Immediate downgrade to Gold + 90-day probation
> - These are the strictest incident gates in the APEX framework. Platinum organisations have earned the right to call themselves autonomous — a serious incident is a fundamental contradiction of that claim.

---

## DIMENSION 1: CAPABILITY SCORE (400 points max)

### 1. DISASTER RECOVERY & BUSINESS CONTINUITY (72 pts)

#### 1.1 DR Plan & Runbook Maturity (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | Self-updating runbooks, AI-assisted recovery steps, DR owner and deputy assigned, weekly automated validation | All services, AI-assisted orchestration, automated dependency-aware recovery, self-testing runbooks | Tier-by-tier AI-orchestrated recovery, predictive dependency failure detection, continuous runbook validation |
| 15–17 | Automated runbooks, version controlled, monthly validation, DR owner assigned | All services, automated runbooks, orchestration scripts | All tiers, orchestration, cross-tier sequences, automated validation |
| 10–14 | Complete runbook, quarterly updates, tested | Most services, mostly current | Most tiers, minor gaps |
| 0–9 | Outdated or missing | Partial coverage | Incomplete tiers |

**Platinum Minimum: 15 pts**

#### 1.2 RTO/RPO Achievement & Validation (20 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 18–20 | RTO <5min, RPO <1min, validated weekly in prod, AI-monitored continuously | Per-service, validated weekly, predictive RTO breach detection | Per-tier, validated weekly, AI predicts and prevents RTO breaches |
| 15–17 | RTO <15min, RPO <5min, validated weekly (Platinum minimum) | Per-service validated weekly | Per-tier validated weekly |
| 10–14 | RTO <15min, RPO <5min, validated monthly | Some services | Some tiers |
| 0–9 | Not consistently achieved at Platinum thresholds | Not validated | Not validated |

**Platinum Minimum: 15 pts (Non-Negotiable #12 tightened)**

#### 1.3 Production Backup Strategy & Continuous Replication (17 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 15–17 | Continuous replication, PITR <1min, automated restore validation daily, AI integrity checks | Multi-region active replication, PITR <1min per service, daily automated restore | Active-active data across regions, PITR <1min per tier, continuous integrity validation with AI anomaly detection |
| 12–14 | Continuous replication, PITR <5min, weekly automated restore validation (Platinum minimum) | Multi-region replication, PITR <5min | Cross-region replication, PITR <5min |
| 7–11 | Hourly snapshots, tested monthly | Hourly, multi-region | Hourly, multi-tier |
| 0–6 | Daily snapshots only | Daily | Daily |

**Platinum Minimum: 12 pts**

#### 1.4 Failover Testing — Weekly Automated (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 13–15 | Automated weekly failover tests, AI validates success criteria, zero manual intervention, results fed back to chaos engine | Per-service automated weekly failover, cross-service dependency validated | Per-tier automated weekly failover, cross-tier cascade prevention validated |
| 10–12 | Automated weekly failover tests, results reported (Platinum minimum) | Per-service weekly | Per-tier weekly |
| 6–9 | Bi-weekly automated tests | Bi-weekly | Bi-weekly |
| 0–5 | Monthly or manual | Monthly or manual | Monthly or manual |

**Platinum Minimum: 10 pts (Non-Negotiable #11 tightened)**

---

### 2. CHAOS ENGINEERING (80 pts)

#### 2.1 Continuous Chaos — AI-Driven, Always-On (28 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 25–28 | AI generates novel chaos scenarios continuously, blast radius predicted before execution, autonomous scope adjustment, zero human approval needed for safe scenarios, findings feed architecture decisions | AI chaos across all services continuously, cross-service blast radius prediction, autonomous approval for pre-approved scenario classes | AI chaos across all tiers continuously, cross-tier blast radius modelling, multi-tier cascade scenarios, learning model updated daily |
| 19–24 | AI-driven continuous chaos, human review for novel scenarios only (Platinum minimum) | Continuous, human review for cross-service novel scenarios | Continuous, human review for cross-tier novel scenarios |
| 11–18 | Scheduled daily chaos, partially AI-assisted | Weekly, AI-assisted | Weekly, AI-assisted |
| 0–10 | Weekly or less frequent | Less than weekly | Less than weekly |

**Platinum Minimum: 19 pts (Non-Negotiable #17 enforced)**

#### 2.2 Game Days — Monthly Micro + Quarterly Full (22 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 20–22 | Monthly micro game days (targeted, 2hr, AI-generated scenarios) + Quarterly full game days (cross-team, executive observer, real production blast radius), findings tracked and resolved within sprint | Same cadence, cross-service scenarios, multi-team | Same cadence, cross-tier, multi-team, regulatory observer invited for compliance tiers |
| 15–19 | Monthly micro + quarterly full, findings actioned (Platinum minimum) | Same cadence | Same cadence |
| 9–14 | Quarterly game days only | Quarterly | Quarterly |
| 0–8 | Bi-annual or ad-hoc | Bi-annual | Bi-annual |

**Platinum Minimum: 15 pts**

#### 2.3 Chaos Coverage & Blast Radius Control (18 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 16–18 | 100% of critical paths covered by chaos scenarios, blast radius predicted and enforced automatically, zero uncontrolled cascades in trailing 90 days | 100% of services, automated blast radius enforcement, cross-service cascade prevention | 100% of tier-critical paths, automated cross-tier blast radius gates, cascade failure prevention at each tier boundary |
| 12–15 | ≥90% critical paths covered, blast radius controls in place (Platinum minimum) | ≥90% services | ≥90% tier-critical paths |
| 7–11 | 70–90% coverage | 70–90% | 70–90% |
| 0–6 | <70% coverage or no blast radius controls | <70% | <70% |

**Platinum Minimum: 12 pts**

#### 2.4 Chaos Findings → Architecture Feedback Loop (12 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 10–12 | Every chaos finding automatically creates architecture review ticket, AI triages severity, critical findings resolved within sprint, chaos findings dashboard reviewed in monthly exec resilience review |
| 7–9 | All findings tracked, critical findings resolved within sprint, monthly review (Platinum minimum) |
| 4–6 | Findings tracked, quarterly review |
| 0–3 | Findings informally tracked or not actioned |

**Platinum Minimum: 7 pts**

---

### 3. INCIDENT MANAGEMENT (88 pts)

#### 3.1 Autonomous Incident Detection & Self-Healing (28 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 25–28 | AI detects and self-heals ≥90% of known incident types without human involvement, MTTD <30 sec, auto-remediation with audit trail, novel incidents escalated with full context | Per-service autonomous healing ≥90%, cross-service correlation in <30 sec | Per-tier autonomous healing ≥90%, cross-tier cascade prevention automated, tier-level blast radius contained autonomously |
| 19–24 | AI detects and self-heals ≥80% of incident types, MTTD <2 min (Platinum minimum) | ≥80% per service, MTTD <2 min | ≥80% per tier, MTTD <2 min |
| 11–18 | AI-assisted detection, 50–80% auto-remediation | 50–80% | 50–80% |
| 0–10 | <50% auto-remediation or primarily manual | <50% | <50% |

**Platinum Minimum: 19 pts (Non-Negotiables #13, #14, #18 enforced)**

#### 3.2 Incident Command & Escalation — Predictive (20 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 18–20 | AI predicts incident severity before escalation, auto-assembles war room with right stakeholders, Incident Commander pre-notified, runbook pre-loaded, customer comms drafted by AI — all before human joins |
| 13–17 | AI-assisted escalation with severity prediction, Incident Commander on-call with <2 min response SLA (Platinum minimum) |
| 8–12 | Defined escalation, IC on-call, <5 min response |
| 0–7 | Manual escalation, >5 min IC response |

**Platinum Minimum: 13 pts**

#### 3.3 Post-Incident Review (PIR) — Blameless & Systemic (20 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 18–20 | PIR completed within 24hrs for Sev 0–1, 48hrs for Sev 2, AI generates timeline draft, action items automatically tracked in backlog, PIR findings fed to chaos engine as new scenario candidates, PIR quality scored |
| 13–17 | PIR within 24hrs (Sev 0–1) / 72hrs (Sev 2), AI-assisted timeline, actions tracked (Platinum minimum) |
| 8–12 | PIR within 48hrs, manual, tracked |
| 0–7 | PIR delayed, incomplete or not done |

**Platinum Minimum: 13 pts**

#### 3.4 Customer Communication — Proactive & Autonomous (20 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 18–20 | AI drafts and sends customer status updates within 60 sec of incident detection, personalised by customer segment, multi-channel, post-incident summary sent proactively before customers ask |
| 13–17 | AI-drafted comms, human approves and sends within 5 min (Platinum minimum) |
| 8–12 | Human-drafted comms, sent within 15 min |
| 0–7 | Reactive communication only or >15 min delay |

**Platinum Minimum: 13 pts**

---

### 4. OBSERVABILITY & DETECTION (72 pts)

#### 4.1 Full-Stack Observability — AI-Correlated (17 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 15–17 | Metrics, logs, traces, events — 100% coverage, AI correlates across all signals in real-time, topology-aware, continuous baseline learning | All signals across all services, AI cross-service correlation, topology auto-discovered | All signals across all tiers, AI cross-tier correlation, predictive failure identification |
| 12–14 | 100% coverage, AI-assisted correlation, continuous baseline learning (Platinum minimum) | 100% services, AI-assisted | 100% tiers, AI-assisted |
| 7–11 | ≥90% coverage, ML-assisted correlation | ≥90% | ≥90% |
| 0–6 | <90% or manual correlation | <90% | <90% |

**Platinum Minimum: 12 pts**

#### 4.2 Distributed Tracing — AI Root Cause in <30 sec (15 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 13–15 | All services traced, AI root cause in <30 sec, cross-service correlation, pre-emptive action | All services traced, AI cross-service correlation, <30 sec | All tiers traced, AI cross-tier root cause, <30 sec, predictive failure identification |
| 10–12 | 95%+ trace coverage, AI-assisted root cause <2 min (Platinum minimum) | 95%+ services, AI root cause <2 min | 90%+ tiers, AI root cause <2 min |
| 6–9 | 80–95% coverage, ML-assisted | 80–95% | 80–90% |
| 0–5 | <80% or basic correlation only | <80% | <80% |

**Platinum Minimum: 10 pts**

#### 4.3 SLI/SLO/Error Budget — Predictive Management (18 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 16–18 | 10+ SLIs, AI predicts budget exhaustion days in advance, autonomous burn rate management, error budget policy enforced with automated deployment freeze | Per-service 8+ SLIs, predictive budget management, autonomous freeze triggers | Per-tier 8+ SLIs, cross-tier budget cascade, AI predicts cross-tier budget impact |
| 13–15 | 8+ SLIs, predictive budget alerts, automated freeze on exhaustion (Platinum minimum) | Per-service 6+ SLIs, predictive | Per-tier 6+ SLIs, predictive |
| 8–12 | 5–8 SLIs, error budgets tracked | 4–6 SLIs | 4–6 SLIs |
| 0–7 | <5 SLIs or reactive only | <4 SLIs | <4 SLIs |

**Platinum Minimum: 13 pts**

#### 4.4 AIOps Platform — Fully Operational (12 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 11–12 | Full AIOps platform: event correlation, anomaly detection, root cause analysis, predictive alerts, autonomous remediation triggers, self-learning models updated continuously | AIOps across all services, self-learning, autonomous remediation, cross-service correlation | AIOps across all tiers, cross-tier self-learning, autonomous remediation, predictive tier-level failure prevention |
| 8–10 | AIOps platform operational, predictive alerts, ML-tuned <5% false positives (Platinum minimum) | AIOps operational, <5% false positives | AIOps operational, <8% false positives |
| 5–7 | ML-assisted alerting, <10% false positives | ML-assisted | ML-assisted |
| 0–4 | Basic ML or rule-based only | Basic | Basic |

**Platinum Minimum: 8 pts**

#### 4.5 Business Observability & Revenue Impact Tracking (10 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 9–10 | Real-time revenue impact dashboard, AI correlates technical degradation to business KPIs in <60 sec, executive-facing observability layer, automated SLA breach prediction |
| 7–8 | Revenue impact tracking, correlation to business KPIs, executive dashboard (Platinum minimum) |
| 4–6 | Business metrics tracked, manual correlation |
| 0–3 | Technical observability only |

**Platinum Minimum: 7 pts**

---

### 5. AUTOMATION & SELF-HEALING (44 pts)

#### 5.1 Infrastructure as Code — 100% Immutable (12 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 11–12 | 100% IaC, immutable infrastructure enforced (no manual changes possible in prod), AI drift detection in real-time, self-remediation of drift within seconds |
| 8–10 | 100% IaC, immutable, AI drift detection, drift remediated within 5 min (Platinum minimum) |
| 5–7 | ≥95% IaC, drift detection in place |
| 0–4 | <95% IaC or mutable infrastructure |

**Platinum Minimum: 8 pts**

#### 5.2 Auto-Remediation Coverage (16 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 14–16 | ≥90% of incident types auto-remediated, self-learning playbooks, novel incidents handled with AI-guided operator assist, audit trail for every auto-action | ≥90% per service, cross-service auto-remediation, self-healing dependency chains | ≥90% per tier, cross-tier auto-remediation, tier-level blast radius healing |
| 11–13 | ≥80% auto-remediated (Platinum minimum) | ≥80% per service | ≥80% per tier |
| 6–10 | 60–80% | 60–80% | 60–80% |
| 0–5 | <60% | <60% | <60% |

**Platinum Minimum: 11 pts (Non-Negotiable #18 enforced)**

#### 5.3 CI/CD Pipeline — Autonomous with AI Validation (10 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 9–10 | Fully autonomous CI/CD, AI validates each deployment against resilience criteria before promotion, automatic rollback on anomaly without human approval, canary/blue-green default |
| 7–8 | Autonomous CI/CD, AI-validated gates, rollback <2 min (Platinum minimum) |
| 4–6 | Automated CI/CD, human approval gates, rollback <5 min |
| 0–3 | Partially automated or manual gates |

**Platinum Minimum: 7 pts**

#### 5.4 Capacity & Scaling Automation (6 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 5–6 | Predictive auto-scaling, AI models traffic patterns 48hrs ahead, pre-scales before demand spikes, zero manual capacity intervention in trailing 90 days |
| 3–4 | Predictive auto-scaling, capacity managed autonomously (Platinum minimum) |
| 1–2 | Reactive auto-scaling |
| 0 | Manual capacity management |

**Platinum Minimum: 3 pts**

---

### 6. ARCHITECTURE & DESIGN RESILIENCE (24 pts)

#### 6.1 Resilience Patterns — Fully Implemented (10 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 9–10 | All patterns implemented and AI-monitored: circuit breakers, bulkheads, retry with jitter, timeouts, rate limiting, graceful degradation, fallback strategies — all continuously validated by chaos |
| 7–8 | All patterns implemented, chaos-validated quarterly (Platinum minimum) |
| 4–6 | Core patterns implemented, partially tested |
| 0–3 | Some patterns, not systematically tested |

**Platinum Minimum: 7 pts**

#### 6.2 Active-Active Multi-Region Architecture (8 pts) × Profile Weight

| Points | Simple (Tier 3) | Mid-Tier | Complex (Tier 0–1) |
|---|---|---|---|
| 7–8 | N/A (passes by default) or active-passive with <5 min failover | Active-active on critical paths, automated traffic shifting | Full active-active, zero-downtime regional failover, AI manages traffic distribution |
| 5–6 | N/A or active-passive <15 min failover | Active-active partial | Active-active partial (Platinum minimum) |
| 3–4 | N/A or DR site exists | Active-passive | Active-passive |
| 0–2 | N/A or single-region only | Single-region | Single-region |

**Platinum Minimum: 5 pts (Non-Negotiable #20 enforced for Tier 0–1)**

#### 6.3 Dependency Risk Management (6 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 5–6 | All dependencies mapped, risk scored, circuit breakers on every external call, AI monitors dependency health and pre-emptively routes around degraded dependencies, quarterly dependency resilience review |
| 3–4 | All dependencies mapped and risk scored, circuit breakers on critical dependencies (Platinum minimum) |
| 1–2 | Key dependencies mapped, some circuit breakers |
| 0 | Limited mapping or no circuit breakers |

**Platinum Minimum: 3 pts**

---

### 7. CULTURE & ORGANIZATIONAL MATURITY (20 pts)

#### 7.1 Resilience Engineering as a Core Discipline (8 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 7–8 | Dedicated SRE/Resilience Engineering team, resilience OKRs published company-wide, exec sponsor actively engaged monthly, resilience-first culture embedded in hiring, onboarding and delivery processes |
| 5–6 | Dedicated resilience team, quarterly exec reviews, resilience OKRs in place, resilience-first culture developing (Platinum minimum) |
| 3–4 | Resilience champions per squad, bi-annual exec reviews |
| 0–2 | Champions only, no dedicated function |

**Platinum Minimum: 5 pts**

#### 7.2 Continuous Learning & Industry Contribution (6 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 5–6 | Monthly training, chaos engineering certifications mandatory, incident commander certifications, team contributes to industry (blogs, conference talks, open source chaos tools) |
| 3–4 | Quarterly training, certifications encouraged, knowledge shared internally (Platinum minimum) |
| 1–2 | Bi-annual training |
| 0 | Ad-hoc only |

**Platinum Minimum: 3 pts**

#### 7.3 Autonomous Improvement — AI-Driven Optimisation (6 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 5–6 | AI recommends and auto-implements resilience improvements, chaos findings automatically fed into architecture decisions and runbooks, monthly resilience score reviewed with exec sponsor, error budget policy self-enforcing |
| 3–4 | AI recommends improvements, monthly resilience review, chaos findings acted on within sprint, error budget policy enforced (Platinum minimum) |
| 1–2 | Quarterly reviews, manual improvement process |
| 0 | Reactive only |

**Platinum Minimum: 3 pts**

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

> Platinum performance metrics are the most demanding in the APEX framework. These are not aspirational targets — they are the baseline expectation for an organisation declaring autonomous resilience. All metrics use trailing 90-day averages unless otherwise stated.

---

### 1. PRODUCTION INCIDENT PERFORMANCE (160 pts)

#### 1.1 Incident Severity Record (60 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 54–60 | Zero Sev 0 (trailing 12 months), Zero Sev 1 (trailing 6 months), Zero Sev 2 (trailing 90 days) |
| 42–53 | Zero Sev 0 (trailing 12 months), Zero Sev 1 (trailing 6 months), ≤1 Sev 2 (Platinum minimum) |
| 24–41 | Zero Sev 0, ≤1 Sev 1, ≤3 Sev 2 |
| 0–23 | Any Sev 0 or 2+ Sev 1 — immediately triggers non-negotiable override |

**Platinum Minimum: 42 pts (Non-Negotiables #15, #16 enforced)**

#### 1.2 MTTD — Mean Time to Detect (50 pts) | Trailing 90-day avg

| Points | All Apps |
|---|---|
| 45–50 | <30 sec average (AI-detected) |
| 35–44 | <2 min average (Platinum minimum) |
| 20–34 | 2–5 min |
| 0–19 | >5 min |

**Platinum Minimum: 35 pts**

#### 1.3 MTTR — Mean Time to Recover (50 pts) | Trailing 90-day avg

| Points | All Apps |
|---|---|
| 45–50 | <5 min average (autonomous healing) |
| 35–44 | <15 min average (Platinum minimum) |
| 20–34 | 15–30 min |
| 0–19 | >30 min |

**Platinum Minimum: 35 pts**

---

### 2. PRODUCTION DR & AVAILABILITY (80 pts)

#### 2.1 DR Test Success Rate (30 pts) | Trailing 90 days (weekly tests)

| Points | All Apps |
|---|---|
| 27–30 | ≥99% weekly automated DR test success |
| 21–26 | 95–99% success (Platinum minimum) |
| 12–20 | 90–95% success |
| 0–11 | <90% |

**Platinum Minimum: 21 pts**

#### 2.2 Production Availability / Uptime (30 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 27–30 | 99.999%+ (≤26 sec/month downtime) |
| 21–26 | 99.99%+ (≤4.4 min/month) — Platinum minimum |
| 12–20 | 99.9%+ |
| 0–11 | <99.9% |

**Platinum Minimum: 21 pts**

#### 2.3 Error Budget Management (20 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 18–20 | Error budget consumed <25% across all SLOs, AI proactively prevented budget exhaustion at least once |
| 13–17 | Error budget consumed <50%, no exhaustion events (Platinum minimum) |
| 7–12 | Budget consumed 50–80%, no exhaustion |
| 0–6 | Budget exhausted in any SLO — triggers incident penalty |

**Platinum Minimum: 13 pts**

---

### 3. CHAOS ENGINEERING PRODUCTION OUTCOMES (80 pts)

#### 3.1 Continuous Chaos Success Rate (40 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 36–40 | ≥98% of chaos scenarios pass (system behaves as designed under failure) |
| 28–35 | ≥90% pass rate (Platinum minimum) |
| 16–27 | 80–90% |
| 0–15 | <80% or not continuously running |

**Platinum Minimum: 28 pts**

#### 3.2 Zero Uncontrolled Cascades (24 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 21–24 | Zero uncontrolled cascades, blast radius fully contained in all chaos events, zero customer-impacting chaos escapes |
| 16–20 | Zero uncontrolled cascades, all blast radius contained (Platinum minimum) |
| 9–15 | ≤1 minor contained cascade |
| 0–8 | Any uncontrolled cascade reaching production customer traffic |

**Platinum Minimum: 16 pts**

#### 3.3 Game Day Outcomes (16 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 14–16 | All monthly micro + quarterly full game days completed, findings actioned within sprint, exec stakeholder debrief documented |
| 10–13 | All cadence completed, findings tracked (Platinum minimum) |
| 6–9 | Quarterly game days completed only |
| 0–5 | Game day cadence missed or findings not actioned |

**Platinum Minimum: 10 pts**

---

### 4. DEPLOYMENT & RELEASE PERFORMANCE (80 pts)

#### 4.1 Production Deployment Success Rate (35 pts) × Profile Weight

| Points | Simple | Mid-Tier | Complex |
|---|---|---|---|
| 32–35 | >99.9% success | >99.5% | >99% |
| 24–31 | 99–99.9% | 99–99.5% | 98.5–99% (Platinum minimum) |
| 14–23 | 98–99% (Platinum minimum) | 98–99% | 97–98.5% |
| 0–13 | <98% | <98% | <97% |

**Platinum Minimum: 24 pts**

#### 4.2 Mean Time to Deploy & Continuous Delivery (25 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 23–25 | Deployment pipeline <5 min end-to-end, continuous delivery capable (multiple times per hour if needed), AI validates each deployment |
| 17–22 | Pipeline <10 min, multiple deployments per day, AI-assisted validation (Platinum minimum) |
| 10–16 | Pipeline <20 min, daily deployment |
| 0–9 | >20 min or less than daily |

**Platinum Minimum: 17 pts**

#### 4.3 Production Rollback — Instant & Zero-Downtime (20 pts) × Profile Weight

| Points | All Apps |
|---|---|
| 18–20 | Automated rollback <1 min, zero-downtime proven, AI-triggered on anomaly detection, tested continuously via chaos |
| 13–17 | Automated rollback <2 min, zero-downtime proven, tested weekly (Platinum minimum) |
| 7–12 | Rollback <5 min, zero-downtime proven |
| 0–6 | Rollback >5 min or causes downtime |

**Platinum Minimum: 13 pts**

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

> At Platinum, stakeholder experience is not a secondary measure — it is the ultimate proof that autonomous resilience translates into tangible human outcomes. Customers should not notice failures. SRE teams should not fear their systems. Business leaders should have full confidence in their platform.

> **Survey Administration:** All stakeholder surveys are anonymous and administered independently by the framework admin. Surveys conducted monthly at Platinum level — not quarterly — reflecting the elite standard expected.

---

### 1. CUSTOMER EXPERIENCE (100 pts)

#### 1.1 Net Promoter Score (NPS) or Equivalent (50 pts) | Monthly

| Points | All Apps |
|---|---|
| 45–50 | NPS ≥80 |
| 35–44 | NPS ≥70 (Platinum minimum — Non-Negotiable #19) |
| 20–34 | NPS 60–69 |
| 0–19 | NPS <60 |

**Platinum Minimum: 35 pts**

#### 1.2 Customer-Impacting Incidents (30 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 27–30 | Zero customer-facing incidents, zero degraded experiences, zero unplanned maintenance windows |
| 20–26 | Zero customer-facing incidents (Platinum minimum) |
| 11–19 | ≤1 minor customer-impacting incident |
| 0–10 | Any significant customer-impacting incident |

**Platinum Minimum: 20 pts**

#### 1.3 Proactive Communication Score (20 pts) | Monthly survey

| Points | All Apps |
|---|---|
| 18–20 | Customers consistently report being informed before they notice issues; proactive comms satisfaction ≥90% |
| 13–17 | Proactive comms satisfaction ≥80% (Platinum minimum) |
| 7–12 | Reactive comms, satisfaction 60–80% |
| 0–6 | Customers report poor or reactive communication |

**Platinum Minimum: 13 pts**

---

### 2. SRE / DEVOPS TEAM CONFIDENCE (60 pts)

#### 2.1 Team Confidence Score (30 pts) | Monthly anonymous survey

| Points | All Apps |
|---|---|
| 27–30 | Average score ≥9.0/10 — team fully trusts the system to defend itself |
| 21–26 | Average score ≥8.0/10 (Platinum minimum) |
| 12–20 | 7.0–7.9/10 |
| 0–11 | <7.0/10 |

**Platinum Minimum: 21 pts**

#### 2.2 SRE Toil Reduction (18 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 16–18 | Toil <5% of SRE team time — autonomous systems handle everything else |
| 12–15 | Toil <10% (Platinum minimum) |
| 7–11 | Toil 10–20% |
| 0–6 | Toil >20% |

**Platinum Minimum: 12 pts**

#### 2.3 On-Call Burden & Psychological Safety (12 pts) | Monthly survey

| Points | All Apps |
|---|---|
| 10–12 | Team rates on-call burden ≤2/10, zero out-of-hours P0/P1 pages in trailing 90 days, psychological safety score ≥9/10 |
| 7–9 | On-call burden ≤4/10, ≤2 out-of-hours escalations, safety ≥8/10 (Platinum minimum) |
| 4–6 | On-call burden ≤6/10 |
| 0–3 | High on-call burden, team reporting fatigue |

**Platinum Minimum: 7 pts**

---

### 3. BUSINESS STAKEHOLDER CONFIDENCE (40 pts)

#### 3.1 Executive Resilience Confidence Score (20 pts) | Monthly survey to exec sponsor + product owner

| Points | All Apps |
|---|---|
| 18–20 | Exec stakeholders score confidence ≥9/10, actively endorse the platform's resilience in business forums |
| 13–17 | Confidence score ≥8/10 (Platinum minimum) |
| 7–12 | Confidence score 6–7/10 |
| 0–6 | Confidence score <6/10 or execs disengaged |

**Platinum Minimum: 13 pts**

#### 3.2 Business Impact — Zero SLA Breaches & Regulatory Risk (20 pts) | Trailing 90 days

| Points | All Apps |
|---|---|
| 18–20 | Zero business-impacting incidents — no revenue loss, no SLA breaches, no regulatory risk, no customer escalations |
| 13–17 | Zero SLA breaches, zero regulatory issues, 1 minor internal impact only (Platinum minimum) |
| 7–12 | 1 minor SLA near-miss, no breach |
| 0–6 | Any SLA breach or regulatory notification |

**Platinum Minimum: 13 pts**

---

### STAKEHOLDER EXPERIENCE SCORE SUMMARY

| Category | Base Points |
|---|---|
| Customer Experience | 100 pts |
| SRE / DevOps Team Confidence | 60 pts |
| Business Stakeholder Confidence | 40 pts |
| **TOTAL** | **200 pts** |

---

## PLATINUM CERTIFICATION REQUIREMENTS

### Score Requirements

| Dimension | Floor (Min Required) | Max Available |
|---|---|---|
| Capability Score | ≥200 pts | 400 pts |
| Performance Score | ≥200 pts | 400 pts |
| Stakeholder Experience | ≥150 pts | 200 pts |
| **Total Score** | **801–1000 pts** | **1000 pts** |

> All three dimension floors must be met independently. A perfect performance score cannot compensate for a Stakeholder floor failure — the human signal matters as much as the operational signal at Platinum.

### Incident-Based Dynamic Recertification

| Incident Event | Consequence | Restoration Path |
|---|---|---|
| 1× Sev 0 in trailing 12 months | Immediate downgrade to Silver + 12-month Platinum bar | Platinum re-application eligible 12 months from incident date |
| 1× Sev 1 in trailing 6 months | Immediate downgrade to Gold + 90-day Gold probation | Gold certification restored post-probation; Platinum re-application after 6 months |
| SLA breach (customer-facing) | –50 pts + PIP triggered | Score restored if root cause fixed and validated within PIP window |
| Error budget exhausted (1 month) | –75 pts (Stage 1) | Score restored if resolved and validated |
| Error budget exhausted (2+ consecutive months) | PIP triggered (Stage 2) | Score restored upon PIP completion and validation |
| NPS drops below 70 | –50 pts + mandatory improvement plan | Score restored when NPS ≥70 sustained for 60 days |

> **Score Restoration Principle:** Penalties are not permanent. If root cause is identified, fixed, and validated by the framework admin within the active PP/PIP window, deducted points are restored. Standard PP/PIP timelines and check-in policies apply throughout.

---

## CERTIFICATION PROCESS

```
Step 1: Gold Validation
  → Confirm active Gold certification or score ≥501

Step 2: Non-Negotiables Gate Check (20 total)
  → ALL must pass → Proceed to scoring
  → ANY failure → No Platinum, remediation required

Step 3: 3-Dimensional Scoring
  → Capability assessment (400 pts max)
  → Performance assessment (400 pts max, trailing 90 days)
  → Stakeholder surveys + metrics (200 pts max)
    → Anonymous, admin-administered MONTHLY at Platinum

Step 4: Dimension Floor Check
  → Capability ≥200?        ✓/✗
  → Performance ≥200?       ✓/✗
  → Stakeholder ≥150?       ✓/✗
  → All pass → Proceed

Step 5: Total Score Check
  → 801–1000 → Provisional Platinum
  → <801     → Below threshold — remain at Gold
  → Review gaps and build improvement roadmap

Step 6: Award "APEX Platinum (Provisional)"
  → 3-month Probation Period begins
  → Monthly health checks with framework admin
  → Executive sponsor notified

Step 7: Full Certification
  → All 20 non-negotiables still passing?
  → Score ≥801 with all dimension floors met?
  → Zero Sev 0 and Sev 1 incidents during probation?
  → Award "APEX Platinum Certified"
  → Valid 12 months / 3-month evaluation cycle
  → Monthly health checks ongoing
```

---

## PROBATION PERIOD (PP) & PERFORMANCE IMPROVEMENT PLAN (PIP)

### Probation Period — 3 Months
- **Status:** APEX Platinum (Provisional)
- Maintain all 20 non-negotiables
- Zero Sev 0 and Zero Sev 1 incidents during probation
- All dimension floors maintained
- Monthly health checks with framework admin
- Executive sponsor sign-off required at end of probation
- **Outcome:** ✅ Full Platinum Certified | ❌ Extend PP (once) or remain at Gold

### Performance Improvement Plan — 3 Months
Triggered by:
- Total score drops below 801
- Any dimension floor fails
- Any non-negotiable fails
- Sev 0 or Sev 1 incident in production
- NPS drops below 70 for 2 consecutive months
- Error budget exhausted 2+ consecutive months

- **Status:** APEX Platinum (PIP)
- Bi-weekly reviews with framework admin
- Executive sponsor actively involved
- Documented remediation plan with milestones and owners
- **Outcome:** ✅ Return to Platinum Certified | ❌ Certification revoked → Gold

---

## CERTIFICATION REVOCATION & RE-ENTRY

> Platinum certification is a privilege, not a permanent state. The APEX framework treats revocation as a signal to invest, not a punishment. The re-entry path is clear, structured, and fair.

### Revocation Triggers

| Trigger | Immediate Consequence |
|---|---|
| Sev 0 incident in production | Downgrade to Silver + 12-month Platinum bar |
| Sev 1 incident in production | Downgrade to Gold + 90-day probation |
| PIP not resolved within 3 months | Certification revoked → Gold |
| PIP extended and failed (second time) | Certification revoked → Silver |
| Two consecutive PIP cycles within 12 months | Permanent Platinum bar for 24 months |
| NPS below 70 for 4 consecutive months | Certification revoked → Gold |

### Re-Entry Path After Revocation

The re-entry path is designed to be rigorous but not punitive. An organisation that has been revoked is not starting from scratch — they retain their Gold certification and their operational knowledge. The path back to Platinum requires demonstrating that the root cause of revocation has been systematically resolved, not just patched.

```
Revocation Event
     ↓
Return to Gold (or Silver if double-PIP failure)
     ↓
90-day stabilisation period (no re-application during this window)
     ↓
Root cause analysis submitted to framework admin
     ↓
Remediation plan approved and milestones tracked
     ↓
Re-application eligible after bar period expires
     ↓
Full Platinum assessment — no shortcuts, no grandfathering
     ↓
Provisional Platinum → 3-month PP → Full Platinum Certified
```

> **Re-entry is not accelerated for previous Platinum holders.** The 3-month evaluation, 20 non-negotiables, dimension floors, and total score requirements all apply in full. The expectation is that a previously Platinum-certified organisation has the muscle memory to move through the re-entry process faster — but the bar does not lower.

### Repeat Revocation — Extended Bar

| Scenario | Platinum Bar Duration |
|---|---|
| First revocation (Sev 1 / PIP failure) | 6 months |
| First revocation (Sev 0) | 12 months |
| Second revocation within 24 months | 24 months |
| Third revocation | 36 months + executive review board approval required |

---

## GOLD TO PLATINUM TRANSITION GUIDANCE

### When to pursue Platinum

The right time to pursue Platinum is when Gold has become comfortable. Not when it is merely achievable — when the team no longer finds Gold demanding. Specifically, consider initiating a Platinum assessment when all of the following are true:

- Consistently scoring 760–800+ across the 3-month evaluation period
- All 15 Gold non-negotiables passing solidly for 12+ consecutive months
- Zero Sev 0 in the past 12 months AND Zero Sev 1 in the past 6 months
- Stakeholder scores consistently ≥150/200 — not occasionally, consistently
- AI-driven continuous chaos engineering is live in production or in final integration testing
- Auto-remediation is demonstrably exceeding 60% and trending toward 80%+
- SRE team toil is below 20% and the team is expressing confidence, not anxiety, about the system

If any of these conditions is not yet true, invest there first. A premature Platinum attempt that fails wastes 3 months of evaluation time and can demoralise the team.

### Key Gaps: Gold → Platinum

| Dimension | Gold Standard | Platinum Standard | Investment Required |
|---|---|---|---|
| Chaos Engineering | Quarterly controlled prod chaos | AI-driven, always-on continuous chaos | AIOps + chaos platform upgrade |
| Game Days | Quarterly full | Monthly micro + quarterly full | Team time + tooling |
| MTTD | <10 min | <2 min | AIOps, distributed tracing, anomaly detection |
| MTTR | <1 hr | <15 min | Auto-remediation playbooks, self-healing pipelines |
| Availability | 99.9%+ | 99.99%+ | Architecture review, active-active |
| Sev 0 Gate | Zero in trailing 6 months | Zero in trailing 12 months | Cultural + engineering discipline |
| Sev 1 Gate | ≤2 per year | Zero in trailing 6 months | Predictive prevention, not reactive response |
| Auto-Remediation | 40–60% | 80%+ (non-negotiable) | Runbook automation, AI playbooks |
| NPS | ≥50 | ≥70 | Customer experience investment |
| Stakeholder Floor | ≥120/200 | ≥150/200 | Proactive comms, exec alignment |
| DR Testing | Monthly ≥90% success | Weekly ≥95% + automated validation | Automated DR harness |
| RTO/RPO | <1hr / <15min | <15min / <5min | Architecture + replication investment |
| Tier Eligibility | Tier 0–4 | Tier 0–3 only | Confirm eligibility before assessment |
| Scoring Dimension | 3D (same as Platinum) | 3D — same structure, harder floors | — |

### Readiness Checklist Before Applying

Use this as a self-assessment gate before requesting a formal Platinum assessment:

```
□  AI-driven continuous chaos active in production for ≥60 days
□  Auto-remediation ≥80% validated in trailing 30 days
□  MTTD <2 min trailing 90-day average confirmed
□  MTTR <15 min trailing 90-day average confirmed
□  Zero Sev 0 in past 12 months
□  Zero Sev 1 in past 6 months
□  NPS ≥70 validated in last monthly survey
□  Stakeholder survey score ≥150/200 in last monthly cycle
□  DR tests passing ≥95% weekly for past 8 weeks
□  Active-active confirmed (Tier 0–1 apps) or exemption documented (Tier 3)
□  Executive sponsor briefed and endorsing the application
□  All 15 Gold non-negotiables passing — framework admin confirmed
```

If any box is unchecked, address it before applying. The formal assessment process cannot be paused mid-way.

---

## CERTIFICATION DISPLAY

```
═══════════════════════════════════════════════════════════════
  ██████╗ ██╗      █████╗ ████████╗██╗███╗   ██╗██╗   ██╗███╗   ███╗
  ██╔══██╗██║     ██╔══██╗╚══██╔══╝██║████╗  ██║██║   ██║████╗ ████║
  ██████╔╝██║     ███████║   ██║   ██║██╔██╗ ██║██║   ██║██╔████╔██║
  ██╔═══╝ ██║     ██╔══██║   ██║   ██║██║╚██╗██║██║   ██║██║╚██╔╝██║
  ██║     ███████╗██║  ██║   ██║   ██║██║ ╚████║╚██████╔╝██║ ╚═╝ ██║
  ╚═╝     ╚══════╝╚═╝  ╚═╝   ╚═╝   ╚═╝╚═╝  ╚═══╝ ╚═════╝ ╚═╝     ╚═╝

    APEX RESILIENCE FRAMEWORK — PLATINUM CERTIFIED

    Application:      Payment Gateway Service
    Complexity:       Complex (Tier 0)
    Profile:          High-Velocity

    Capability:       368/400   (92.0%)
    Performance:      352/400   (88.0%)
    Stakeholder:      172/200   (86.0%)

    TOTAL SCORE:      892/1000  (89.2%)

    Certified:        March 1, 2025
    Valid Through:    February 28, 2026
    Next Review:      June 1, 2025
    Monthly Checks:   1st of every month

    🏆 APEX PLATINUM — THE APEX OF RESILIENCE
═══════════════════════════════════════════════════════════════
```

---

## EXAMPLE SCORING SCENARIOS

### Example 1: Complex Tier 0 — Platinum Certified (852 pts) ✅
**Application:** Banking Payment System | **Complexity:** Complex | **Profile:** Stable Enterprise

| Dimension | Category | Score |
|---|---|---|
| **Capability (345/400)** | DR & BC | 65/72 |
| | Chaos Engineering | 72/80 |
| | Incident Management | 80/88 |
| | Observability | 65/72 |
| | Automation | 38/44 |
| | Architecture | 18/24 |
| | Culture | 17/20 |
| **Performance (355/400)** | Incident Performance (MTTD <2min, MTTR <12min, 0 Sev0, 0 Sev1) | 145/160 |
| | DR & Availability (97% DR success weekly, 99.995% uptime) | 72/80 |
| | Chaos Outcomes (91% continuous chaos success, zero cascade) | 68/80 |
| | Deployment (99.2% success, <1min rollback) | 70/80 |
| **Stakeholder (152/200)** | Customer Experience (NPS 74, zero customer incidents) | 78/100 |
| | SRE Confidence (6% toil, score 8.7/10) | 45/60 |
| | Business Confidence (monthly exec review, zero business impact) | 29/40 |

**Non-Negotiables:** ✅ All 20 passed
**Result:** APEX Platinum (Provisional) → Platinum Certified

---

### Example 2: Platinum Denied — Stakeholder Floor Failure ✗
**Application:** E-Commerce Platform | **Complexity:** Mid-Tier | **Profile:** High-Velocity

| Dimension | Score |
|---|---|
| Capability | 335/400 |
| Performance | 340/400 |
| Stakeholder | **138/200** ← Below ≥150 floor |
| **Total** | **813/1000** |

**Result:** Platinum DENIED — Stakeholder floor not met despite total of 813.
*"Exceptional capability and performance. Stakeholder experience is the final frontier. NPS at 62 needs to reach ≥70. SRE satisfaction at 7.4 needs to reach ≥8.0. These are cultural and product investments, not just technical ones."*

---

### Example 3: Sev 1 Override — Immediate Gold Downgrade ✗
**Application:** Retail Platform | **Total Score:** 835 (Platinum range)

Had 1 Sev 1 incident 3 months ago (within trailing 6 months).

**Result:** Immediate downgrade to Gold + 90-day Gold probation.
Non-Negotiable #16 override. Platinum re-application eligible 6 months from incident date.
*"Zero Sev 1 tolerance in trailing 6 months is non-negotiable at Platinum. Focus on predictive incident prevention and autonomous remediation to prevent recurrence."*

---

### Example 4: Mid-Tier Tier 3 App — Strong Platinum (821 pts) ✅
**Application:** Customer Analytics Platform | **Complexity:** Simple | **Profile:** Data-Intensive

| Dimension | Score |
|---|---|
| Capability | 320/400 |
| Performance | 335/400 |
| Stakeholder | 166/200 |
| **Total** | **821/1000** |

**Non-Negotiables:** ✅ All 20 passed (Note: Non-Negotiable #20 active-active N/A for Simple/Tier 3 — passes by default)
**Result:** Platinum Certified — demonstrates Platinum is achievable beyond Tier 0–1 for operationally excellent teams

---

### Example 5: Revocation & Re-Entry (Illustrative) ✗ → ✅
**Application:** Insurance Claims Platform | **Complexity:** Mid-Tier | **Profile:** Stable Enterprise

**Month 0:** Platinum Certified (Score: 824)
**Month 4:** Sev 1 incident during peak processing window. Auto-remediation contained it within 18 min but the incident clock was non-negotiable.

**Immediate action:** Downgraded to Gold. 90-day Gold probation begins. Platinum bar: 6 months from incident date.

**Month 7:** Root cause analysis completed. Dependency circuit breaker missing on legacy payment processor integration. Fixed and chaos-validated. Gold probation successfully completed.

**Month 10:** 6-month bar expires. Re-application submitted. Full Platinum assessment conducted — no shortcuts.

**Month 13:** APEX Platinum re-certified (Score: 841). Stronger than before — the incident directly drove the architecture improvement that closed the gap.

*"Revocation is not failure. It is the framework working as designed — catching the gap that chaos missed. The re-entry path exists because Platinum organisations learn faster than others."*

---

## FRAMEWORK VERSIONING & FUTURE-PROOFING

| Attribute | Detail |
|---|---|
| **Version** | v1.0 |
| **Effective Date** | TBD |
| **Review Cycle** | Annual |

**Built-in flexibility:**
- AI/AIOps weighting can increase in future versions as adoption matures across the industry
- New subcategories can be added within existing categories without restructuring
- New profiles can be introduced (e.g., "AI-Native Profile", "Edge Computing Profile", "Quantum-Resilient Profile")
- Existing certifications honoured for 6 months after framework updates
- Grandfathering clause: certifications valid at time of framework update remain in force until next annual re-certification
- As AI-native architectures mature, Platinum will evolve to reflect new standards (e.g., self-designing resilience, autonomous architecture optimisation)

---

## APEX FRAMEWORK — COMPLETE CERTIFICATION LADDER

| Level | Environment | Score Range | Dimensions | Key Philosophy |
|---|---|---|---|---|
| **Bronze v1.1** | Non-Production | 200–350 | 2D (Cap + Perf) | Foundational resilience — get started |
| **Silver v1.1** | Non-Production | 351–500 | 2D (Cap + Perf) | Operational maturity — production-ready practices |
| **Gold v1.1** | Production | 501–800 | 3D (Cap + Perf + Stakeholder) | Engineering excellence — real production resilience |
| **Platinum v1.0** | Production | 801–1000 | 3D (Cap + Perf + Stakeholder) | Autonomous resilience — systems defend themselves |

---

*APEX Platinum Certification Framework v1.0 — Autonomous Resilience*
*Builds on: APEX Bronze v1.1 | APEX Silver v1.1 | APEX Gold v1.1*
*The APEX of Resilience Engineering*