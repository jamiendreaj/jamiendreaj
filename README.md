## Jamie Ndreaj

I build AI products and ship them — prompt architecture, guardrails, evaluation, backend, and App Store submission.

Self-taught. Four Claude-powered apps designed and built solo, plus six open-source agents built around a single question: what must a model be structurally unable to do? Most recently a software support intern at a car-rental software company in Italy (Dec 2025 – May 2026), working live production tickets against PostgreSQL. Before tech, nine years in real estate across New York and Las Vegas.

US & Italian (EU) dual citizen — can be hired in the United States or anywhere in the EU, no sponsorship required.

Shipped

Tutto AI — An AI assistant in one app. Chat, translation across 12 languages, PDF summarising, image analysis and hands-free voice. The backend is a Cloudflare Worker that keeps API credentials server-side, with explicit consent before anything reaches an AI provider. React Native Claude API Cloudflare Workers

NourishMe — Nutrition tracking with AI food recognition. Point the camera at a plate or scan a barcode and it works out what you're eating — macros, micronutrients, meal plans and HealthKit sync, in English, Italian and Spanish. React Native Expo Claude Vision HealthKit RevenueCat

LunaRest — Sleep, for the whole night. Soundscapes for falling asleep, a recorder that captures snoring and night sounds, and wind-down tools. React Native Expo Audio HealthKit

Alter: AI Chief of Staff — submitted, in App Store review. An alarm that wakes you, reads your day aloud in a real voice, then lets you talk back. Claude writes the briefing from your calendar and your private notes on the people in it — interruptible speech, voice-driven calendar edits with confirmation before anything destructive, notes encrypted on-device. Claude API ElevenLabs AlarmKit Cloudflare Workers SQLCipher

Agents

Six repositories, tests and CI on every one. 226 tests, all offline against an injected client — a suite that needs an API key is a suite that gets skipped in CI, and a guardrail nobody runs is a comment.

grounded-agents — The shared agent loop, in TypeScript. Tool handlers are typed from the tool's own JSON Schema, so an enum narrows to a union and a required field stays required at compile time. Extracted after the same loop turned up in two agents with 149 of 171 lines identical. Three behaviours exist in it because they were bugs first: a clean finish that returns no text is named rather than crashed on, the token budget is checked before tools run, and a grave failure is reported differently from a typo. TypeScript Claude API

document-extraction-agent — Contract fields, each carrying the exact span it was read from. The contract says thirty days' notice in clause 11 and sixty in Schedule 2; the agent reports both and refuses to choose, because applying a precedence the contract never stated is interpretation. A field whose quotation is not in the document is deleted, not flagged — a value with a warning attached still travels downstream. Three states, no confidence score: found, absent, ambiguous. TypeScript

property-enquiry-agent — Structurally unable to screen on a protected characteristic. US Fair Housing and EU/GDPR are modelled as separate axes, because who you may treat differently and what you may collect are different questions with different law behind them. Sourced in LEGAL.md so a compliance function can say where it's wrong.

insurance-enquiry-agent — Quotes the policy wording or escalates, and never paraphrases. A paraphrase of a clause is a new policy term nobody underwrote, and a 2024 tribunal held a firm responsible for what its chatbot told a customer. There is deliberately no tool for quoting, binding, or deciding a claim — each is a licensed act, and a tool the model can reach for is one it will eventually use.

direct-booking-agent — Pre-booking enquiries for independent hotels, answered in the guest's own language and grounded in the property's own dossier.

agent-evals — Code graders, a calibrated model judge, and a baseline comparison that answers whether a change actually helped.

Engineering notes

llm-production-patterns — Evaluation harnesses, reliability patterns and encrypted local storage extracted from the four apps. Each pattern exists because something failed in production first: silent truncation against the token ceiling, a shared secret that drifted between two files, a retry that should never have retried.

mobile-api-proxy — Keeping third-party API keys off the device: a small Cloudflare Worker that holds the secret server-side.

Experience

Software Support Intern — Dogma Systems, Italy · Dec 2025 – May 2026. Client-facing support on a production fleet-management system: worked incoming tickets, read production logs to trace failures, and wrote SQL against PostgreSQL for retrieval and reporting. Jira, sprint coordination, Slack.

Certifications

Anthropic — Claude Certified Architect path, 2026: Claude 101 · Building with the Claude API · Introduction to Model Context Protocol · AI Fluency · Claude on Google Cloud · Claude Code 101 · Claude Code in Action

Google Cybersecurity Professional Certificate · CompTIA Security+ (SY0-701) · Splunk Search Expert 101

Working with

TypeScript React Native Expo Node.js Cloudflare Workers PostgreSQL SQLCipher Claude API MCP Git Jira

Languages: English · Italian · Spanish · Albanian

Elsewhere

Portfolio · jxnstudioapp@gmail.com
