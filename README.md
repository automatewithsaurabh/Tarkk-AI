# TARKK AI — Stack Intelligence Engine

> Describe what you want to build. Get the exact no-code stack to ship it.

**Live demo:** [tarkk-ai.vercel.app](https://tarkk-ai.vercel.app)

---

## What is TARKK?

TARKK is an AI-powered tool for vibe coders — builders who ship products using no-code and AI tools instead of writing raw code.

You describe your idea in plain English. TARKK returns the exact stack to build it: which tools to use, in what order, how they connect, how long it takes, and a day-by-day weekend build plan.

Think of it as a senior technical co-founder in a text box.

---

## What you get

For every idea you submit, TARKK returns:

- **Stack** — 4 to 7 tools, picked specifically for your idea
- **Scope** — what the MVP includes, what the full product looks like, what is out of scope
- **Timeline** — realistic MVP and full build estimates
- **Difficulty** — Beginner, Intermediate, or Advanced
- **Cost estimate** — monthly running cost to start
- **Tool connections** — exactly how each tool talks to the next
- **Build steps** — ordered, actionable steps with actual tool names
- **Weekend plan** — Day 1 and Day 2 breakdown
- **First step today** — the one thing to do in the next 30 minutes

---

## Built with

- **Claude API** (claude-sonnet-4-20250514) for stack intelligence
- **Cloudflare Workers** as a secure API proxy
- **Vanilla HTML, CSS, JS** — single file, no framework
- **Vercel** for deployment

---

## How it works

```
User describes idea
        |
        v
TARKK sends to Claude API via Cloudflare Worker
        |
        v
Claude returns structured JSON stack recommendation
        |
        v
TARKK renders it as a clean, readable response card
```

The Cloudflare Worker sits between the frontend and Anthropic's API so the API key is never exposed in the browser.

---

## Run locally

No build step. No dependencies. Just open the file.

```bash
git clone https://github.com/automatewithsaurabh/Tarkk-AI.git
cd Tarkk-AI
open index.html
```

To use the AI features locally, you need to either:
- Point the fetch URL to your own Cloudflare Worker
- Or temporarily replace the Worker URL with a direct Anthropic API call and add your own key for local testing only

---

## Project structure

```
Tarkk-AI/
├── index.html       # Entire app — UI, logic, styles in one file
└── README.md
```

---

## Sections

**Hero** — Animated terminal mockup showing live stack output. Cycles through 3 different product ideas automatically.

**Problem** — Addresses the core frustration of vibe coders: too many tools, no clear answer on which to use.

**How it works** — Three step breakdown: describe, analyze, get stack.

**Chat interface** — Full Claude-style chat overlay with sidebar history, warm beige aesthetic, and structured response cards.

---

## API response structure

TARKK instructs Claude to return a strict JSON schema on every call:

```json
{
  "summary": "string",
  "scope": { "mvp": "string", "fullProduct": "string", "notIncluded": "string" },
  "timeline": { "mvp": "string", "fullProduct": "string" },
  "difficulty": "Beginner | Intermediate | Advanced",
  "estimatedCost": { "monthly": "string", "oneTime": "string" },
  "targetUser": "string",
  "tools": [{ "name": "string", "role": "string", "why": "string", "freeTier": true }],
  "connections": [{ "from": "string", "to": "string", "how": "string" }],
  "buildSteps": ["string"],
  "weekendPlan": { "day1": "string", "day2": "string" },
  "firstStepToday": "string"
}
```

---

## Deploy your own

1. Fork this repo
2. Set up a Cloudflare Worker with your Anthropic API key as a secret
3. Replace the Worker URL in `index.html` with your own Worker URL
4. Import the repo to Vercel and deploy

Full setup guide in the repo wiki.

---

## About

Built by **Saurabh Ahire** — Founding GTM Engineer at Commerceflo.

I build the way vibe coders build: AI-first, no unnecessary complexity, ship fast. TARKK is a tool I wanted to exist, so I built it in a weekend.

- Portfolio: [saurabhahire.com]
- LinkedIn: [linkedin.com/in/saurabhahire03](https://linkedin.com/in/saurabhahire03)
- X: [@automatewithsaurabh](https://x.com/automatewithsaurabh)

---

## License

MIT — use it, fork it, build on it.
