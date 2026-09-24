# Tomás Vicente

**AI systems engineer.** I build LLM systems where correctness is enforced in code, not requested in a prompt.

Informatics Engineer (Universidad del Salvador, 2025) · Buenos Aires, Argentina · UTC−3
Argentine & Italian citizenship · English C1 (IELTS Academic 7.0)

---

### What I mean by "enforced in code"

Most agent implementations put the rules in the system prompt and hope the model follows them. In a ten-turn conversation, a model that obeys 95% of the time is wrong in one conversation out of two.

So in the systems I build:

- A **pure function** decides the single move for each turn. The model only phrases it. Behaviour is table-tested in milliseconds instead of depending on the model obeying.
- Directives are a **discriminated union**, so the render switch is exhaustive — a turn cannot end without an instruction.
- A **validator** checks every action the model proposes against the real world *before* anything is sent. Invalid actions are dropped and a corrective reply written by code goes out instead. The model never touches the calendar or the CRM directly.
- A **reply guard** runs over the generated text: prices absent from the catalogue, invented business hours, promises the system can't keep. The expensive violations never send — they regenerate or escalate to a human.

The hard part was never making it answer well. It was making it not answer badly.

---

### Selected work

**Conversational WhatsApp agent for a real-estate brokerage** · Node.js · TypeScript · PostgreSQL · WhatsApp Cloud API
~26k lines of code and ~14k of tests. Nine integrations, twelve cron jobs, sixteen versioned migrations. Three-level test suite: 1,333 unit tests with no network or database, 104 scenarios against the live model validated by the *production* guard at `pass^4`, and scripted end-to-end conversations. Per-call token telemetry with a hard spend ceiling.
→ [Architecture write-up](https://github.com/tivogi) *(update this link)*

**AI booking agent + bilingual revenue site** · n8n · Claude · Square API · Next.js 15 · Cloudflare Workers
Cold inbound message to a confirmed appointment in a live Square calendar, with natural-language dates resolved against real availability. 48-route Next.js app on Cloudflare Workers with a `verify:slugs` prebuild step that fails the build when a page slug drifts from a catalogue ID.

**Static bilingual site, zero-JS performance budget** · Astro 7 · Tailwind 4 · TypeScript
100 / 100 / 100 / 100 Lighthouse desktop on ~1.8 KB of inlined JavaScript. Editorial policy encoded as build-time invariants: the build fails on stale review data, a routed city with no localised copy, or a missing Spanish key. 23-assertion post-build verifier gates every deploy.

---

### Research

**Market Shield — Quantitative Detection of Market Manipulation in Crypto Assets**
First author. Published and presented at **ICDD 2026**, the 10th International Conference on Applied Informatics, Lucian Blaga University of Sibiu, Romania.

Six-stage pipeline over three public market APIs feeding an ensemble of a Z-score baseline, an XGBoost classifier (SMOTE plus tuned `scale_pos_weight` for class imbalance) and a TensorFlow detector. **ROC AUC > 0.94, PR AUC > 0.73** on an imbalanced held-out set, validated retrospectively against four documented fraud events.

Research member, Institute for Research in Art, Architecture & Technology, Universidad del Salvador, since May 2026.

---

### Stack

```
Languages     TypeScript · Python · SQL · Go · Java · Bash
LLM systems   Anthropic & OpenAI SDKs · finite-state conversation design
              tool-call validation gates · reply guards · eval harnesses
Backend       Node.js + Express · webhook APIs (HMAC, idempotency, dedup)
              PostgreSQL / Supabase · migrations · cron · promise queues
Frontend      Next.js 15 · React · Astro · Tailwind · typed EN/ES i18n
Edge & infra  Cloudflare Workers / Pages / KV · Linux · nginx · Docker · pm2
Data & ML     pandas · Polars · NumPy · scikit-learn · XGBoost · TensorFlow
```

---

### Still learning

Boot.dev — **Level 75 (Sage), top 4%**, 1,125 lessons solved across 9 courses and 4 projects.
Most recent: Pandas & Polars. Currently working through Power BI.

---

### Elsewhere

[LinkedIn](https://www.linkedin.com/in/tomasvicente) · [CV](https://github.com/tivogi) · tomasignaciovicente@gmail.com

*Open to remote work with US and EU teams. Full US East Coast overlap, EU work authorisation.*
