# AI State-Continuity, Traceability & Governance Model (CTG)

## Whitepaper v3.2 — Release Candidate

**Draft · March 2026**

---

**Core thesis:** C (State Continuity) → T (Traceability) → G (Governance) — a three-axis directed dependency structure. T-axis = Observability + Contestability infrastructure. G-axis subjects are institutions and people, never AI itself. All labels must be accompanied by plain-language limitation statements.

**v3.2 changelog:** ① C-axis renamed from "Cognitive Continuity" to "State Continuity" (resolves cognition ≠ memory confusion) ② DDI formalized with "Behavior Envelope" baseline definition ③ T2 explicitly requires "decision justification interface", not "explainable model" ④ G3 split into G3a (regulator-assigned) / G3b (accredited pool self-selection) ⑤ Open Questions add "Digital Trust" direction ⑥ Grey-box preservation clarified as complementary to T3 change logs ⑦ DDI breaker clarified as "pause for human review", not "terminate evolution"

---

## Chapter 1: Three-Axis Model Overview

### 1.1 Why Three Axes?

Accountability requires information availability. Information availability depends on memory, logging, and state persistence. But this information need not come from the AI's own memory — it can come from external infrastructure. A witness with amnesia can still be held accountable if the entire event was recorded on surveillance cameras.

This insight drives the decomposition from a dual-axis model into three axes, making the intermediate layer explicit:

**C-axis — State Continuity:** The AI system's own technical ability to maintain state over time. How much it "remembers." Note: this is not an "intelligence" axis — Netflix Recommender ranks higher than single-shot GPT inference on C-axis, but this reflects state persistence, not reasoning capability.

**T-axis — Traceability Infrastructure:** External observation and contestation capability built around the AI system. How much it can be "seen and challenged." This is the bridge connecting C and G.

**G-axis — Governance Accountability:** Institutional accountability capability built around the AI system. The subject is always institutions and people, not AI — because AI is not a legal subject under current law.

The three axes have a **directed dependency** rather than being orthogonal: C provides raw information, T organizes it into auditable evidence, G uses evidence to enforce accountability. When C is low, T requires more external infrastructure to compensate; when C is high, T can leverage the AI's own memory to reduce costs.

### 1.2 Precise Definition of T-axis (v3.1 clarification)

> ✅ **T = Observability + Contestability Infrastructure**
>
> T-axis contains two sub-dimensions: observability (how much the system is seen — logs, snapshots, change records) and contestability (whether external parties can effectively challenge system outputs). T1 primarily corresponds to observability, T2 primarily to contestability, T3 is the complete combination of both. We do not split into four axes in order to preserve the framework's communicability.

### 1.3 2D Projection Visualization (v3.1 addition)

Three axes are difficult for human intuition. We recommend the following 2D projection for communication:

**Capability Plane (C × T):** Horizontal axis is C (State Continuity, C0→C3b), vertical axis is T (Traceability Infrastructure, T0→T3). Each AI product is a point on this plane.

**Governance Overlay (G):** G0→G3 overlays as an independent "regulatory jurisdiction layer" on top of the capability plane. Similar to administrative districts on a map — the same geographic location can belong to different jurisdictions. The same (C1, T2) system can be under G1 or G2 governance.

```
        T3 ┤ ·───────────── Full-chain Auditable
           │
        T2 ┤ ·───────────── Contestable  
           │        ╔══════════════╗
        T1 ┤ ·──────║  Most current ║── Logged
           │        ║  AI products  ║
        T0 ┤ ·──────╚══════════════╝── Unrecorded
           └──┬──────┬──────┬──────┬──────┬──
             C0     C1     C2    C3a    C3b
          Transient Session Persistent Online Auto-telic
                                      Learning (Theory)

G0─G3 overlays as regulatory jurisdiction layers
```

---

## Chapter 2: C-axis — State Continuity Classification

This axis describes the AI system's own technical ability to maintain state over time. Pure technical description, no value judgments.

| Level | Name | State Characteristics | Testable Criteria |
|-------|------|----------------------|-------------------|
| C0 | Transient | Stateless. Each input is an independent computation, equivalent to a pure function call. | Output distribution for identical inputs is unaffected by interaction history. |
| C1 | Session | Session memory. State maintained via context window within a session; cleared when session ends. | Contradiction detection rate ≥90% within N-turn dialogue. No recall after refresh. |
| C2 | Persistent | Cross-session memory. Long-term storage of user preferences and historical views, with version control. | Can accurately reference user preferences from 30 days ago. |
| C3a | Online Learning | Continuous parameter updates (e.g., recommendation systems, ad ranking). Already widely deployed. | Measurable performance drift. Parameter update frequency > 1/day. |
| C3b | Auto-telic (Theoretical) | Autonomous modification of objective function† rather than merely updating parameters. No current engineering implementation. | The objective itself (not parameters) has undergone verifiable change. |

† **Objective function layer statement (v3.1):** "Objective function" here refers to behavior-shaping objectives (e.g., RLHF reward, instruction-following policy), not training objectives (e.g., next token prediction). The core distinction of C3b is: the system modifies "what it should do", not merely "how to do it better."

‡ **C3b and G-axis decoupling risk (v3.1):** If a system has autonomously modified its objectives, developers may argue "it is no longer the machine I designed." This is C3b's fundamental challenge to current legal attribution logic. When C3b actually exists, the legal system may need innovations as fundamental as the invention of the "legal person" concept. Retained as theoretical layer for now.

---

## Chapter 3: T-axis — Traceability Infrastructure Classification

T-axis is the core addition in v3.0. It describes external observation capability built around the AI system — the bridge connecting C-axis (state continuity) and G-axis (governance). The original v2.1 I-axis (Memory Integrity) is merged into this axis as a change traceability sub-dimension.

| Level | Name | Traceability Characteristics | Testable Criteria |
|-------|------|------------------------------|-------------------|
| T0 | Unrecorded | Not observable. No logs, no environment records. | Cannot extract any historical interaction's input or intermediate state. |
| T1 | Logged (Observability) | Complete I/O records + environment snapshots (model hash, System Prompt, temperature/seed, tool state). Reproduction is approximate (GPU non-determinism). | Extract complete I/O + environment snapshot within 24h. Retention ≥90 days. |
| T2 | Contestable (Contestability) | T1 + system provides a decision justification interface for key outputs. Does not require the model itself to be explainable — only that the system provides sufficient information for a Standard Contestor to effectively challenge. Based on "Standard Contestor" definition (§3.2). Mandatory post-hoc rationalization risk disclosure. | Standard Contestor can effectively contest outputs. Evaluated via Multi-metric Evaluation Set (§3.2). |
| T3 | Full-chain Auditable | T2 + change traceability + DDI circuit breaker + Grey-box preservation. Primarily for high-risk domains (§3.5). | Any change rollback within 48h. DDI threshold triggers auto-downgrade + Grey-box preservation. |

### 3.2 Standard Contestor and Multi-metric Evaluation Set (v3.1)

> ⚠️ **Contestor Variance Problem**
>
> The same system might be T2 facing a top hacker but fail T0 for an elderly user. If "contestability" is not a fixed system property but an emergent result of system-user interaction, T-axis labels lose stability.

**Solution:** Introduce the **Standard Contestor Profile** — analogous to the "reasonable person" standard in law or "qualified pentester" in security testing. T2 evaluation is based on the Standard Contestor's capability, not arbitrary users.

**Standard Contestor definition:** An independent third party with relevant domain expertise, holding digital audit qualifications certified by regulatory authorities. Specific qualification requirements defined by domain regulators.

> ⚠️ **Goodhart's Law Risk**
>
> Once "contestation success rate" becomes a KPI, systems will optimize the KPI rather than genuine contestability — e.g., deliberately leaving small errors to mask large ones. Isomorphic to financial risk models optimizing stress test metrics.

**Solution:** Contestation success rate must not be a single metric. Must use a **Multi-metric Evaluation Set**, with evaluation methods periodically updated:

- **(a) Adversarial Challenge Success:** Can the Standard Contestor discover system errors through active challenge?
- **(b) Counterfactual Stability:** Do small input changes cause dramatic output changes, and can changes be traced?
- **(c) Decision Trace Coverage:** What proportion of decision paths does the contestation information cover?
- **(d) Evaluation Method Update Frequency:** Multi-metric set updated every 12 months, similar to penetration testing rule iteration.

### 3.3 Decision Drift Index Circuit Breaker (DDI)

**Terminology correction (v3.1):** v3.0's "cognitive entropy" was a misuse of physics terminology. Renamed to **Decision Drift Index (DDI)**.

> ✅ **DDI Formal Definition (v3.2)**
>
> DDI = degree to which system behavior deviates from the expected **Behavior Envelope**. The Behavior Envelope is jointly defined by deployer and auditor, describing expected system behavior range during normal operation. Changes within the envelope are normal (e.g., recommendation system's daily parameter adjustments); exceeding the envelope triggers DDI breaker. This prevents "recommendation systems triggering breakers daily."

**Rule:** When DDI exceeds threshold, T-axis label auto-downgrades one level until audit capability recovers.

**Critical clarification (v3.2):** The breaker pauses T-axis label and triggers human review — it does not terminate system evolution. Same logic as FDA requiring clinical trials for remarkable new drugs — not killing breakthroughs, but ensuring breakthroughs are verified before deployment.

### 3.4 Grey-box Preservation (v3.1)

> ⚠️ **Breaker-Moment Audit Vacuum**
>
> Accidents often occur at the system's most "drifting" moments. If the system downgrades due to breaker at that moment, the instant most needing audit is in audit-failed state. For C3a systems, evolution is at millisecond scale; auditor observation always has latency.

**Solution:** Borrowing the airplane black box principle — at the instant the breaker triggers, force-freeze a complete, tamper-proof accident snapshot. T-axis label downgrades, but "accident scene preservation" does not.

**Grey-box contents:** Complete I/O stream for 60 seconds before breaker + environment snapshot + DDI change curve + model parameter hash. Stored in tamper-proof third-party storage, retention matching dispute statute of limitations.

**Relationship to T3 change logs (v3.2 clarification):** Grey-box solves "accident instant" snapshot preservation. T3's change traceability (48h rollback) solves "long-term drift" historical tracing. Two mechanisms, two time scales: Grey-box is the "photograph", T3 change log is the "documentary."

### 3.5 T3 Cost Feasibility Statement (v3.1)

> ⚠️ **Storage Explosion Risk:** Full-chain trace for 100M users × 10 prompts/day could reach PB/day.

**Statement:** T3 is primarily for high-risk scenarios (finance, healthcare, autonomous driving), not all AI applications. T1 suffices for low-risk scenarios. Aligned with EU AI Act risk-based logic.

---

## Chapter 4: G-axis — Governance Accountability Classification

> ✅ **G-axis Subject Statement:** AI is not a legal subject. G-axis describes institutional accountability capability built around AI — subjects are always institutions and people.

| Level | Name | Governance Characteristics | Testable Criteria |
|-------|------|---------------------------|-------------------|
| G0 | Unframed | No institutional accountability mechanism. | Cannot determine which entity bears responsibility when errors occur. |
| G1 | Disclosed | Limitations disclosed. User informed of CTG coordinates and meaning, including Anti-Label-Illusion. | User interface contains understandable limitation prompts. Comprehension test pass rate ≥70%. |
| G2 | Allocable | Responsibility allocable. Clear boundaries. User co-responsibility uses "Category Presumption" (§4.2). | Can clearly output responsibility allocation for simulated error scenarios. |
| G3a | Enforceable (Regulator-assigned) | Complete accountability chain + remediation. Audit institutions regulator-assigned with mandatory rotation. Layered audit. For strong regulatory environments (EU, China). | Independent audit completes full responsibility determination. Mandatory rotation enforced. |
| G3b | Enforceable (Accredited pool) | Same as G3a, but audit institution selected from regulator-accredited pool. For lighter regulatory environments (US). Must satisfy four principles. | Same as G3a, but selected from accredited pool. |

### 4.2 Category Presumption (v3.1)

> ⚠️ **Administrative Cost Explosion:** Individual user comprehension testing creates a massive certification black hole. Deployers would design complex tests to shift responsibility.

**Solution — Category Presumption:**

- **(a) Professional users** (licensed physicians, certified financial analysts): Presumed capable; can co-bear responsibility.
- **(b) Ordinary consumers:** Presumed incapable; deployer bears primary responsibility by default.
- **(c) Burden reversal:** Deployers may prove their interface enables comprehension, but burden of proof is theirs.

### 4.3 Anti-Label-Illusion

Any CTG label must include a plain-language limitation statement.

**Example:** "This system is [C1, T1, G1]. This means: it only remembers this conversation; all responses are logged but it cannot explain 'why'; when errors occur, responsibility lies with you and the service provider, not the AI. For major decisions, consult a professional."

### 4.4 G3 Dual-Track and Four Principles (v3.2)

> ⚠️ **Audit Impossible Triangle + Political Risk:** Independence, expertise, and cost — at most two of three. "Regulator-assigned auditors" is regulatory overreach for US tech companies. Dual-track accommodates different political environments.

**G3a (Regulator-assigned):** For EU, China. Mandatory rotation.

**G3b (Accredited pool):** For US. Uniform minimum standards within pool to curb audit shopping.

**Layered audit** (both tracks): (a) General compliance layer — rotatable; (b) Domain expert layer — from certified pool, longer rotation cycle; (c) Two layers independent but collaborative.

**Four principles:** Separation, Assignment/rotation, Verifiability (code sealed for filing, not fully open-sourced), Game-theoretic design (incentive structures making "lying cost extremely high").

---

## Chapter 5: Responsibility Allocation Table

### 5.1 Product Coordinates

| Product | C | T | G | Description |
|---------|---|---|---|-------------|
| Early GPT API | C0 | T0 | G0 | Stateless, unrecorded, no framework. |
| ChatGPT / Claude.ai | C1 | T1 | G1 | Session memory, I/O logged, limitations disclosed. |
| Claude Memory | C2 | T1 | G1 | Cross-session memory, tracing at log level. |
| Financial Compliance AI | C1 | T2 | G2 | Contestable decisions, allocable responsibility. |
| Netflix Recommender | C3a | T1 | G1 | Continuous updates, basic tracing/accountability. |
| Ideal Medical AI | C2 | T3 | G3a | Full-chain + DDI breaker + Grey-box + layered audit. |

### 5.2 Responsibility Rules

| G | User | Deployer | Developer |
|---|------|----------|-----------|
| G0 | Full responsibility. | No institutional obligations. | No direct responsibility. |
| G1 | Primary. Informed of limitations. | Disclosure + Anti-Label-Illusion obligation. | Labeling obligation. |
| G2 | Conditional. Professionals presumed capable; consumers presumed incapable — deployer default primary. | Primary. Contestation obligation + burden of proof. | Contestability obligation. Systematic misleading → primary liability. |
| G3a/b | Limited. Only after explicit warning ignored. | Primary. G3a regulator-assigned; G3b accredited pool. Layered audit. | Joint liability for model-level systemic failures. |

**Core boundary:** G2 is the watershed. Ordinary consumers do not co-bear by default; burden of proof on deployer.

---

## Chapter 6: EU AI Act Mapping (v3.1)

CTG is **complementary** to existing frameworks, not competing.

| EU AI Act Risk | Suggested C | Suggested T | Suggested G | Notes |
|---------------|-------------|-------------|-------------|-------|
| Minimal | None | None | None | Self-regulation. |
| Limited | C0-C1 | T1 | G1 | Transparency obligations. |
| High | C1+ | T2 | G2 | Compliance + contestability. |
| Unacceptable/Critical | C2+ | T3 | G3a | Highest audit + layered. |

*Note: Preliminary mapping. Also complementary to NIST AI RMF and ISO/IEC 42001.*

---

## Chapter 7: Privacy vs. Traceability — Structural Tension

Precise attribution requires tracing to specific data points. Differential privacy obfuscates individual contributions. Logically mutually exclusive.

**No perfect solution exists.** Three mitigation paths:

- **(a) Differential Privacy Audit:** Statistical info, not raw data. For T2/G2. Cost: precision loss.
- **(b) Time-lock Audit:** Encrypted storage, judicially unlocked. For G3. Cost: judicial complexity.
- **(c) User Sovereignty:** User-side storage. For low-risk. Cost: potential tampering.

---

## Chapter 8: Recommendations and Roadmap

### 8.1 Minimum Thresholds

| Scenario | Min C | Min T | Min G |
|----------|-------|-------|-------|
| Casual/Creative | — | — | — |
| Education | C1 | T1 | G1 |
| Financial advisory | C1 | T2 | G2 |
| Medical diagnosis | C2 | T3 | G3 |
| Autonomous driving | C2 | T3 | G3 |

### 8.2 First Landing: Financial AI

Existing regulatory foundation (MiFID II, Basel), accountability culture, mature audit infrastructure. Then medical AI (FDA/CE), then autonomous driving (SAE J3016 supplement).

### 8.3 Roadmap

| Phase | Goal | Actions |
|-------|------|---------|
| 0-12 months | Establish consensus | Publish whitepaper → Community feedback → Open-source evaluator → Financial AI pilot |
| 1-3 years | T-axis + layered audit as standard | Regulator partnership → Standard Contestor certification → Grey-box spec → EU AI Act mapping |
| 3-5 years | T3+G3 engineering, privacy-traceability resolution | Time-lock engineering → C3a DDI at scale → C3b research → Audit game theory |

---

## Chapter 9: Open Questions

1. **Multi-metric calibration:** Empirical thresholds for adversarial challenge success, counterfactual stability, decision trace coverage.
2. **Domain-specific DDI:** Financial AI vs. content recommendation have different tolerances.
3. **Cross-jurisdictional:** Different legal systems, different privacy-traceability balance points.
4. **Mathematical "responsibility":** Can "lying cost" be encoded in loss functions?
5. **C3a audit methods:** 10⁹ parameter updates need "behavioral drift audit", not parameter-level audit.
6. **Standard Contestor certification:** Cross-domain qualification standards. Reference: CISA cybersecurity auditor certification.
7. **Digital Trust (v3.2):** For C3b — an independent digital entity (quasi-legal person) with compensation reserves bears responsibility. Similar to how limited liability companies solved "natural persons can't bear unlimited commercial risk." Possibly G-axis's institutional solution for the C3b era.
8. **Behavior Envelope calibration (v3.2):** Domain-specific empirical research needed to calibrate DDI envelope parameters for different industries.

---

*This document is an open-source draft. Contributions welcome via GitHub Issues or Pull Requests.*

*"Don't define a framework without boundaries. Define a framework that knows where its boundaries are."*
