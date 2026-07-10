# Lotus Path AI — Intake & Action Plan Assistant (Phase 1 prototype)

A working prototype of Phase 1 from the Lotus Path AI proposal: a resident completes
an intake questionnaire, and Claude generates the five outputs described in the
proposal — client summary, priority needs score, resource recommendations, a
personalized action plan, and suggested next steps for staff.

## What this demonstrates

- End-to-end flow: form → AI call → structured, formatted output
- The exact intake categories from the proposal (basic info, housing, employment &
  education, transportation, financial info, immediate needs, goals)
- The exact five AI outputs from the proposal, generated live, not hardcoded
- A single, dependency-free HTML file — no build step, no framework

## Running it

Open `index.html` directly in a browser, fill out the intake form, and click
**Generate action plan**.

**Note on the API call:** this file calls Claude's API directly from the browser
(`api.anthropic.com/v1/messages`). That works as-is inside Claude.ai, where the
request is authenticated automatically. If you host this file elsewhere (GitHub
Pages, Netlify, etc.), the call will need one of:

- a lightweight backend/serverless function that holds your Anthropic API key and
  proxies the request (recommended for anything beyond a demo — never put a real
  API key in client-side JS), or
- for a quick personal demo only, a key pasted in locally while testing (still not
  safe to publish that way).

For a portfolio submission, the cleanest path is: keep this repo as the source code
demonstrating the working concept, and link to a short screen recording or the live
version running inside a Claude artifact.

## Files

- `index.html` — the full prototype (markup, styling, and logic in one file)

## Roadmap (from the proposal)

Phase 1 (this prototype) is the foundation for later phases: an AI Career Coach,
Housing Action Planner, Volunteer Matching System, Donation Matching System, and
Resource Navigator.
