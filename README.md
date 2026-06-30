# Nagar Seva — Hyperlocal AI Civic Agent

**See. Think. Act. Resolve.**

Nagar Seva is an AI-powered civic complaint agent built for the **Vibe2Ship Hackathon** (Coding Ninjas × Google for Developers) under **Problem Statement 2 — Community Hero: Hyperlocal Problem Solver**.

Citizens in Hyderabad face daily issues — potholes, broken streetlights, water leaks, garbage piling up — but reporting them is fragmented, slow, and rarely tracked. Nagar Seva turns a single photo into a fully drafted official government complaint in seconds, using Gemini AI to see, think, and act on the user's behalf.

🔗 **Live App:** https://vijaynivasssabasu-dev.github.io/Nagar-Seva/

---

## The Problem

Reporting a civic issue in India today usually means one of two things: a complaint that disappears into a government portal with no tracking, or no complaint at all because the process feels like too much effort. There is no system that understands the issue, knows which department is responsible, and helps the citizen act immediately.

## The Solution

Nagar Seva acts as an autonomous civic agent rather than a passive form. A citizen uploads a photo of the issue, and from there the AI agent takes over:

1. **Sees** — Gemini Vision analyzes the photo and identifies the issue, severity, and risk
2. **Confirms** — asks the citizen to confirm the detected category before proceeding, so the AI stays accurate and trustworthy
3. **Thinks** — calculates a Priority Score out of 100 based on severity, proximity to schools/hospitals, and number of citizens affected
4. **Routes** — automatically detects whether the location is in Telangana or Andhra Pradesh from GPS coordinates, and identifies the correct government department (GHMC, TSSPDCL, HMWSSB, CPGRAMS, etc.) using verified real government email addresses
5. **Acts** — drafts a complete, formal complaint email addressed to the right authority, with the user's GPS location, AI-generated description, and a unique tracking ticket — the citizen just clicks one button and Gmail opens fully pre-filled
6. **Follows up** — 14 days after filing, Nagar Seva proactively asks the citizen whether the issue was resolved, in progress, or ignored, and automatically drafts an escalation email (CC'd to the national CPGRAMS portal) if no action was taken

## Why This Is an AI Agent, Not Just a Chatbot

Most hackathon submissions in this category build a report-and-forget form. Nagar Seva is built around an agentic loop — it doesn't just classify an image, it reasons about context (is this near a school? how many people are affected?), takes a real action (drafting and opening an email), and follows up over time to hold the process accountable. The agent workflow is visualized step by step in the UI so the reasoning is transparent to the user.

---

## Key Features

- **Real Gemini 2.5 Flash Vision** — actual image analysis, not a simulated response
- **AI category confirmation loop** — user can correct the AI's detection before it proceeds, building trust instead of blind automation
- **Priority Score engine** — severity + school/hospital proximity + citizens affected, computed transparently with a visible breakdown
- **State-aware government routing** — GPS coordinates determine Telangana vs Andhra Pradesh and route to the correct, verified official department email
- **One-click official complaint email** — fully auto-drafted formal letter, opens directly in the citizen's own Gmail, zero typing required
- **14-day automated follow-up** — re-engages the citizen and auto-escalates unresolved complaints
- **Downloadable PDF complaint record** — printable official document with ticket number, AI analysis, and government routing details
- **Live hotspot map** — Leaflet.js map of real Hyderabad locations with severity-coded markers
- **Community leaderboard & gamification** — civic points, badges, and city-wide contributor rankings
- **4 full UI themes** — Default, Bright, Dark, and Dusk
- **Honest UX** — clearly distinguishes what is fully automated (the drafted email) from government portals that require the citizen's own login, instead of overclaiming automatic filing

---

## Tech Stack

| Layer | Technology |
|---|---|
| AI Engine | Google Gemini 2.5 Flash (Vision + Text) via Google AI Studio |
| Frontend | HTML5, CSS3 (custom theme system), Vanilla JavaScript |
| Maps | Leaflet.js + OpenStreetMap |
| Location | Browser Geolocation API |
| Hosting | GitHub Pages (static, HTTPS) |

This is a single self-contained `index.html` file by design — no build step, no server, no database required. It runs entirely in the browser and was built this way to be deployable in minutes on free static hosting, which matched both the hackathon's tight timeline and Google AI Studio's role as the core build tool.

---

## How to Run Locally

1. Clone this repository
2. Open `index.html` directly in any modern browser, **or** serve it locally for full GPS/camera support:
   ```bash
   python -m http.server 8080
   ```
   then visit `http://localhost:8080`
3. Get a free Gemini API key from [aistudio.google.com/apikey](https://aistudio.google.com/apikey) and paste it in-app to activate the AI features

---

## Government Portals Referenced

All department emails and portal links were manually verified against official government sources at the time of submission (GHMC Integrated Grievance System, TSSPDCL, HMWSSB, CPGRAMS). Where a portal requires citizen login to file directly, the app is explicit about that rather than claiming automatic submission — only the AI-drafted email step is genuinely one-click.

---

## Team

Built solo by Vijay Nivas for Vibe2Ship 2026 — Coding Ninjas × Google for Developers.

## Hackathon Submission

- **Problem Statement:** PS2 — Community Hero: Hyperlocal Problem Solver
- **Core tool used:** Google AI Studio (Gemini 2.5 Flash)
- **Submission deadline:** 29 June 2026
