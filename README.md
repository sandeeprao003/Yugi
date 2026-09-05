# Yugi

A single-file web app for grade-level (and Olympiad-style) math practice, built for kids ages 8–16 (grades 3–10+).

No backend, no build step, no dependencies — `index.html` is the entire app. It runs 100% client-side and stores all progress in the browser's `localStorage`.

## How to use it

### Option A — just open the file
Double-click `index.html` (or open it in any modern browser: Chrome, Safari, Edge, Firefox). That's it — the app runs immediately, no install needed.

### Option B — host it online (recommended for daily use on a phone/tablet)
Because the file is named `index.html`, it works out of the box with **GitHub Pages**:

1. Push this repo to GitHub (see below).
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. GitHub publishes it at `https://<your-username>.github.io/<repo-name>/` within a minute or two.
5. On your kid's phone, open that URL in the browser, then use **Add to Home Screen** (Safari on iOS, or the "Install app" option in Chrome on Android) to get an app-like icon with no browser bar.

Any other static host works too (Netlify, Vercel, Cloudflare Pages) — just upload `index.html`.

## Using the app itself

1. **Pick or add a learner.** On first open, add a name, choose a grade (3rd–10th+), and pick an avatar.
2. **Do the day's 3 sessions.** Each day has three 20-minute sessions (Number & Operations / Algebra, Fractions–Ratios–Percent / Geometry–Trig, and Geometry & Measurement / Number Theory — the exact three depend on grade band). A day only advances to the next one once all three sessions for the current day are complete — there's no calendar lock, so a day can be finished whenever, even days later.
3. **Ask for a hint.** Every problem has a "💡 Need a hint?" button. If the AI capability is available (only when opened as a Claude Artifact on claude.ai) it asks Claude live for a hint tailored to that exact problem, with a follow-up question box underneath. Outside that environment (e.g. hosted here on GitHub Pages), it automatically falls back to a built-in written hint for each topic — nothing breaks either way.
4. **Review past answers.** After finishing a session, or later from the dashboard / Roadmap screen, "📋 Review answers" shows every question, your answer, the correct one, and the explanation.
5. **Track progress.** The "🏆 Roadmap & progress" screen shows a 16-week Olympiad-style syllabus (harder enrichment topics unlock from week 5), mastery per topic, and a streak counter.

## What's inside

- **80 problem generators** across 4 grade bands (3–4, 5–6, 7–8, 9–10+), each with grade-appropriate core topics plus Olympiad-style enrichment topics (styled after MOEMS, Math Kangaroo, MATHCOUNTS, and AMC 8/10/12 — original questions matched to those exams' topics and difficulty, not reproductions of real past questions).
- **Diagrams** for geometry and fraction/ratio/percent questions (hand-drawn inline SVG, generated from each problem's own numbers).
- **A day-pointer progress model**: Day N stays active until all 3 sessions are done, so nothing is ever lost to a missed calendar day.
- **A review log** of the last 30 days of completed questions and answers.

## Data & privacy

Everything (profiles, scores, streaks, question history) is stored only in the browser's `localStorage` on the device it's used on. Nothing is sent to any server. Clearing browser data / site data for this page will erase progress, so avoid "Clear browsing data" if you want to keep it. There's no login system beyond picking a name from a local list — this is designed for a single family's own device(s), not multi-device sync.
