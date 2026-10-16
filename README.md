# IoT Practice Lab

A zero-dependency static MCQ quiz website. Includes 1,049 questions extracted from the supplied PDFs, arranged in 72 year/week sets.

## Run locally

In the folder with `index.html` and `questions.json`:

```bash
python -m http.server 8000
```

Open http://localhost:8000. Do not just double-click `index.html` because browsers can block loading the local JSON file.

## Deploy to Vercel

1. Extract this zip to a folder.
2. Install [Vercel CLI](https://vercel.com/docs/cli) or create a project on the Vercel dashboard.
3. Via CLI, run `npx vercel --prod` in this folder, or upload the folder into a GitHub repository and import that repo at Vercel.
4. Framework preset: `Other`; output directory: leave empty (project root).
5. Open the Vercel-provided URL.

Works on Netlify or GitHub Pages too. No account/login/database required for the quiz itself. Attempt history is saved in the browser using localStorage.

## Question bank schema

`questions.json` is an array of objects:

```json
[{"id":"set1","name":"My Set · Week 1","year":"2026","week":1,"questions":[{"id":"q1","question":"Question?","options":{"A":"Option 1","B":"Option 2","C":"Option 3","D":"Option 4"},"answers":["B"],"solution":"Explanation...","source":"My document","week":1}]}]
```

Multiple correct answers are supported by adding more than one letter in `answers`.

## Extraction caveats

Question bank extracted automatically from PDFs. Some PDF sources are duplicates and question extraction can have text artifacts. Diagram-dependent questions were skipped. Review source keys when in doubt. This build includes year-week question sets based on 2022, 2023, 2024, 2024 July, 2025 July and weekly 2025 documents; the other provided papers include overlaps, practice material without confidently paired answer keys, or scanned pages and were not merged automatically.
