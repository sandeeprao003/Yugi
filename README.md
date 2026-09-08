# Yuji

A single-file web app for grade-level Math **and** Science Olympiad-style practice, built for kids ages 8–16 (grades 3–10+). Math and Science are tracked completely independently — a learner can be on a different grade for each subject at the same time.

No backend, no build step, no dependencies — `index.html` is the entire app. It runs 100% client-side and stores all progress in the browser's `localStorage`.

## How to use it

### Option A — just open the file
Double-click `index.html` (or open it in any modern browser: Chrome, Safari, Edge, Firefox). That's it — the app runs immediately, no install needed.

### Option B — host it online (recommended for daily use on a phone/tablet)
Because the file is named `index.html`, it works out of the box with **GitHub Pages**:

1. Push this repo to GitHub (already done if you're reading this here).
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. GitHub publishes it at `https://<your-username>.github.io/<repo-name>/` within a minute or two.
5. On your kid's phone, open that URL in the browser, then use **Add to Home Screen** (Safari on iOS, or the "Install app" option in Chrome on Android) to get an app-like icon with no browser bar.

Any other static host works too (Netlify, Vercel, Cloudflare Pages) — just upload `index.html`.

## Using the app itself

1. **Pick or add a learner.** On first open, add a name and pick an avatar.
2. **Pick a grade per subject.** The dashboard has a Math tab and a Science tab. The first time you switch to a subject, you'll pick its grade (3rd–10th+) — Math and Science can be different grades for the same learner.
3. **Study before testing.** Every topic card has a "📚 Learn this topic" button — a plain-language explanation plus a worked example (with a "🔄 Try another example" button) — before the "🎯 Take the assessment" button starts the real 10-question practice session.
4. **Do the day's 3 sessions.** A day only advances to the next one once all three subject-strand sessions for the current day are complete — there's no calendar lock, so a day can be finished whenever, even days later.
5. **Ask questions any time.** Every problem, and every Learn example, has both a "💡 Need a hint?" and a "❓ Ask a question" button. When the AI capability is available (as a Claude Artifact on claude.ai, or with your own Anthropic API key — see below) it asks Claude live, and can attach a simple diagram to its answer when that helps. Each answer ends with a "Did that make sense?" check so you can see whether the explanation actually landed. Outside that environment, it automatically falls back to a built-in written hint for each topic — nothing breaks either way.
6. **Review past answers.** After finishing a session, or later from the Daily Learning Log, "📋 Review" shows every question, your answer, the correct one, the explanation, and any doubts asked about it.
7. **Daily Learning Log.** The dashboard's sidebar lists every day (scroll for up to 30), what was studied vs. assessed per topic, active time spent per topic, and a "💬 N asked" button showing exactly what was asked and answered that day.
8. **Track progress.** The "📈 Progress" section on the dashboard shows a mastery badge, trend charts, and topic-by-topic mastery bars. "🏆 Roadmap & progress" shows the longer-term Olympiad-style syllabus and where to find real past exams for that grade.
9. **Pick a look.** The "🎨 Theme" button offers 6 color themes: Classic, Neon Arcade, Candy Pop, Galaxy Explorer, Blocky Craft, and Cyber Mint.

## Optional: your own Anthropic API key

The "⚙️ AI hint settings" link (on the login screen) lets you add your own [console.anthropic.com](https://console.anthropic.com) API key. This is only needed when the app is opened outside claude.ai (e.g. hosted here on GitHub Pages) and you still want live AI hints — without a key, hints and questions automatically use the built-in written explanations instead. The key is stored only in that browser's `localStorage`, in plain readable form, and each hint makes a small paid API call — read the in-app warning before adding one.

## What's inside

- **~116 problem topics** across Math and Science, spanning 4 grade bands (3–4, 5–6, 7–8, 9–10+). Math topics are procedurally generated (fresh numbers every time); Science topics draw from curated fact banks aligned to real Science Olympiad divisions and general grade-level science standards.
- Each question is tagged with a "Style" — the real competition (MOEMS, Math Kangaroo, MATHCOUNTS, AMC 8/10/12, Science Olympiad, etc.) its topic and difficulty is modeled after. These are original practice questions, not reproductions of real past exam questions.
- **Diagrams** for geometry, fraction/ratio/percent, and science visualization questions (inline SVG, generated from each problem's own numbers) — Claude's live hints can also attach one of these diagrams when it helps explain an answer.
- **A day-pointer progress model, per subject**: Day N stays active until that subject's sessions are done, so nothing is ever lost to a missed calendar day, and Math/Science advance independently.
- **A Daily Learning Log**: per-day, per-topic record of what was studied, assessed, asked about, and how long was spent on it.
- **A review log** of the last 30 days of completed questions, answers, and any doubts asked.

## Data & privacy

Everything (profiles, scores, streaks, question history, theme choice) is stored only in the browser's `localStorage` on the device it's used on. Nothing is sent to any server except Anthropic's API when a hint or question is asked (either via claude.ai's built-in capability, or your own API key). Clearing browser data / site data for this page will erase progress, so avoid "Clear browsing data" if you want to keep it. There's no login system beyond picking a name from a local list — this is designed for a single family's own device(s), not multi-device sync.
