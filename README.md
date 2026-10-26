## Jamie Ndreaj

I build AI products and ship them — prompt architecture, guardrails, evaluation,
backend, and App Store submission.

Self-taught. Four Claude-powered apps designed and built solo, plus six open-source
agents built around one question: **what must a model be structurally unable to do?**
Most recently a software support intern at a car-rental software company in Italy
(Dec 2025 – May 2026), working live production tickets against PostgreSQL. Before
tech, nine years in real estate across New York and Las Vegas.

**US & Italian (EU) dual citizen — can be hired in the United States or anywhere
in the EU, no sponsorship required.**

---

### Shipped

**[Tutto AI](https://apps.apple.com/us/app/tutto-ai/id6776184829)** — An AI assistant in one app
Chat, translation across 12 languages, PDF summarising, image analysis and hands-free
voice. The backend is a Cloudflare Worker that keeps API credentials server-side, with
explicit consent before anything reaches an AI provider.
`React Native` `Claude API` `Cloudflare Workers`

**[NourishMe](https://apps.apple.com/us/app/nourishme-ai-nutrition/id6766461839)** — Nutrition tracking with AI food recognition
Point the camera at a plate or scan a barcode and it works out what you're eating —
macros, micronutrients, meal plans and HealthKit sync, in English, Italian and Spanish.
`React Native` `Expo` `Claude Vision` `HealthKit` `RevenueCat`

**[LunaRest](https://apps.apple.com/us/app/lunarest/id6769334639)** — Sleep, for the whole night
Soundscapes for falling asleep, a recorder that captures snoring and night sounds,
and wind-down tools.
`React Native` `Expo` `Audio` `HealthKit`

**Alter: AI Chief of Staff** — *submitted, in App Store review*
An alarm that wakes you, reads your day aloud in a real voice, then lets you talk
back. Claude writes the briefing from your calendar and your private notes on the
people in it — interruptible speech, voice-driven calendar edits with confirmation
before anything destructive, notes encrypted on-device.
`Claude API` `ElevenLabs` `AlarmKit` `Cloudflare Workers` `SQLCipher`

---

### Agents

Six repositories. **226 tests, every one offline** against an injected client — a suite
that needs an API key is a suite that gets skipped in CI, and a guardrail nobody runs
is a comment. CI on all six.

| | What it will not do | Tests |
| --- | --- | --- |
| **[grounded-agents](https://github.com/jamiendreaj/grounded-agents)** | Call anything sendable unless the model finished *and* every guard passed | 17 |
| **[document-extraction-agent](https://github.com/jamiendreaj/document-extraction-agent)** | Keep a field whose quotation is not in the document, or choose between two clauses that disagree | 58 |
| **[property-enquiry-agent](https://github.com/jamiendreaj/property-enquiry-agent)** | Screen on a protected characteristic, or collect what the jurisdiction forbids | 37 |
| **[insurance-enquiry-agent](https://github.com/jamiendreaj/insurance-enquiry-agent)** | Paraphrase policy wording, quote a price, bind cover, or decide a claim | 38 |
| **[direct-booking-agent](https://github.com/jamiendreaj/direct-booking-agent)** | Answer a guest from anything but the property's own dossier | 41 |
| **[agent-evals](https://github.com/jamiendreaj/agent-evals)** | Call a change an improvement without a baseline to compare it to | 35 |

**The two that explain the rest:**

**[grounded-agents](https://github.com/jamiendreaj/grounded-agents)** — the shared agent
loop, in TypeScript. Tool handlers are typed from the tool's own JSON Schema, so an
enum narrows to a union and a required field stays required at compile time. Extracted
after the same loop turned up in two agents with **149 of 171 lines identical**. Three
behaviours are in it because they were bugs first: a clean finish that returns no text
is named rather than crashed on, the token budget is checked *before* tools run, and a
grave failure is reported differently from a typo.

**[document-extraction-agent](https://github.com/jamiendreaj/document-extraction-agent)** —
contract fields, each carrying the exact span it was read from. The contract says
thirty days' notice in clause 11 and sixty in Schedule 2; the agent reports both and
**refuses to choose**, because applying a precedence the contract never stated is
interpretation. A field whose quotation is not in the document is *deleted, not
flagged* — a value with a warning attached still travels downstream. Three states, no
confidence score: found, absent, ambiguous.

---

### Engineering notes

**[llm-production-patterns](https://github.com/jamiendreaj/llm-production-patterns)** —
Evaluation harnesses, reliability patterns and encrypted local storage extracted from
the four apps. Each pattern exists because something failed in production first:
silent truncation against the token ceiling, a shared secret that drifted between two
files, a retry that should never have retried.

**[mobile-api-proxy](https://github.com/jamiendreaj/mobile-api-proxy)** —
Keeping third-party API keys off the device: a small Cloudflare Worker that holds the
secret server-side.

---

### Experience

**Software Support Intern** — Dogma Systems, Italy · Dec 2025 – May 2026
Client-facing support on a production fleet-management system: worked incoming tickets,
read production logs to trace failures, and wrote SQL against PostgreSQL for retrieval
and reporting. Jira, sprint coordination, Slack.

### Certifications

**Anthropic** — Claude Certified Architect path, 2026
Claude 101 · Building with the Claude API · Introduction to Model Context Protocol ·
AI Fluency · Claude on Google Cloud · Claude Code 101 · Claude Code in Action

[Google Cybersecurity Professional Certificate](https://coursera.org/verify/professional-cert/4X8EIUP3CHTA) ·
CompTIA Security+ (SY0-701) · Splunk Search Expert 101

### Working with

`TypeScript` `React Native` `Expo` `Node.js` `Cloudflare Workers` `PostgreSQL`
`SQLCipher` `Claude API` `MCP` `Git` `Jira`

Languages: English · Italian · Spanish · Albanian

### Elsewhere

[Portfolio](https://jamiendreaj.github.io) · jxnstudioapp@gmail.com
