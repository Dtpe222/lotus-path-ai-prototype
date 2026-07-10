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
request is authenticated automatically. Hosted elsewhere (GitHub Pages, Netlify,
etc.), that request has no credentials and will fail — by design, since a real API
key should never live in public client-side JS.

To keep the hosted demo functional for anyone clicking the link, the app tries the
live call first and, if it fails, falls back to a clearly labeled sample output
("Sample output · demo mode") built from whatever the visitor typed into the form.
This shows the exact format and content structure Claude would generate, without
exposing a key.

For a real deployment, replace the direct `fetch` to `api.anthropic.com` with a
call to a small backend or serverless function that holds the API key server-side
and proxies the request.

## Files

- `index.html` — the full prototype (markup, styling, and logic in one file)

## Roadmap (from the proposal)

Phase 1 (this prototype) is the foundation for later phases: an AI Career Coach,
Housing Action Planner, Volunteer Matching System, Donation Matching System, and
Resource Navigator.
