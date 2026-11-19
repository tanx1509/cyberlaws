# CyberAtlas prototype

This is a buildless, mobile-first front-end prototype for the cybercrime-law project described in the attached brief. It intentionally simulates a product backend for academic/demo use: authentication, case workspaces, evidence locker, saved research, incident creation, and an admin command center all run in the browser.

Run locally from this folder with any static server, for example:

```bash
python3 -m http.server 4173 --directory dist
```

The research terminal will call `POST /api/research` when a backend exists; otherwise it stays in demo mode. The legal content is intentionally framed as a research starting point and needs a human verification pass before formal use.

## Frontend-only demo behavior

- Demo sign-in opens an authenticated-looking workspace without creating a real account.
- Incident creation generates a local case record style response.
- Evidence, saved research, and admin review states are represented with curated demo data.
- No Render service, database, secret, or API key is required for the current demo.

The next production step would be to replace these local states with Supabase Auth, Postgres, and Storage without redesigning the interface.

## Current interactive experience

- English is the default language; the `EN / हिंदी` control switches the main navigation, intro copy, help prompt, and quick-help labels into Hindi.
- The sun/moon control switches between light and dark themes and remembers the choice in the browser.
- The quick-help rail includes Money gone, Phone lost, Account hack, Fake profile, Threats, Other issue, and Data leak.
- AI-harm cards flip on hover and remain keyboard/click accessible, revealing a field note with practical evidence and response guidance.
- Country cards select into a structured comparison view and link to official reporting or cyber-safety resources.
- The incident matcher accepts plain English, Hinglish, common typos, and aliases such as `phone stole`, `mobile chori`, and `UPI fraud`.

## What I need to take it to production

1. The source repository or deployment access for the current Render app.
2. Target launch scope: India only, or a multi-country first release.
3. The backend/API contract and credentials for Tavily/Groq (or the preferred search + LLM stack).
4. The authoritative source list you want to trust: government gazettes, police portals, regulators, and legislation databases.
5. Branding preferences, owner/team name, and whether the site should include a disclaimer/contact page.
