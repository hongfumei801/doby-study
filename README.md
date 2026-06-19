# 🦉 Doby 的期末考複習樂園 (Doby's G5 Final Exam Study Playground)

An interactive, bilingual (English + 繁體中文) study site for a Grade 5 final exam.
Single self-contained `index.html` — works **offline** (double-click) and hosts anywhere static.

## Features
- 5 sections: Home · Science · Reading · Grammar & Writing · Math
- Every English block has a 「中」button → reveals Chinese (hidden by default, fail-safe)
- 🔊 pronunciation on vocabulary words (Web Speech API, offline)
- Quizzes with instant feedback, explanations, scoring + celebration
- Games: vocabulary match, sort-into-buckets, typed math practice

## How to extend (可擴充)
All content lives in JavaScript `CONTENT.<subject>` objects inside `index.html`.
The rendering engine is **data-driven**, so adding material is just adding data — no new code.

| Want to add… | Edit |
|---|---|
| A new note / fact | add a block `{type:'fact', en:'…', zh:'…'}` to a section |
| A table | `{type:'table', cols:[…], rows:[[…]]}` |
| A vocabulary word | add to `CONTENT.<subject>.vocab` (gets 🔊 automatically) |
| A quiz question | add to `CONTENT.<subject>.quiz` |
| A matching game | set `CONTENT.<subject>.match.pairs` |
| A sort game | add to `CONTENT.<subject>.sorts` |
| Typed practice | add to `CONTENT.<subject>.mathSets` |
| A whole new subject | add a `CONTENT.<key>` object + an entry in `TAB_ORDER` |

Each text field is `{en, zh}` — the engine builds the 中 toggle for you.

## Run locally
Just open `index.html`. (Or `python -m http.server` in this folder.)

## Hosting
Static — deployable to GitHub Pages, Netlify, Cloudflare Pages, or any web server.
Currently published via GitHub Pages.
