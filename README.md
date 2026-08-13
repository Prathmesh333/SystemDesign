# SystemDesign

Interactive visual explanations of system design concepts.

**Live site:** [prathmesh333.github.io/SystemDesign](https://prathmesh333.github.io/SystemDesign/)

## Current questions

01. [Machine Learning at Scale](questions/ml-at-scale.html)
02. [URL Shortener](questions/url-shortener.html)
03. [YouTube](questions/youtube.html)
04. [WhatsApp](questions/whatsapp.html)
05. [Netflix](questions/netflix.html)
06. [Uber Nearby Drivers](questions/uber-nearby.html)
07. [Web Search Engine](questions/google-search.html)

Open `index.html` directly, or serve the folder with any static HTTP server.

For local development:

```bash
python -m http.server 4173
```

Then open `http://127.0.0.1:4173/`.

## GitHub Pages deployment

The repository includes `.github/workflows/pages.yml`. A push to `main` or `master` deploys the complete static site through the official GitHub Pages Actions workflow.

For the first deployment, open the repository on GitHub and select:

```text
Settings → Pages → Build and deployment → Source → GitHub Actions
```

The production base URL is:

```text
https://prathmesh333.github.io/SystemDesign/
```

All internal links and assets are relative, so lesson pages work under the `/SystemDesign/` project subpath. `.nojekyll` ensures GitHub Pages serves the static files without Jekyll processing.

## Architecture

- `index.html` is the platform homepage and question index.
- `.github/workflows/pages.yml` deploys the static site to GitHub Pages.
- `404.html`, `robots.txt`, `sitemap.xml`, and `site.webmanifest` provide production hosting metadata.
- `questions/` contains one semantic HTML lesson per system design question.
- `css/global.css` owns platform tokens, navigation, and shared primitives.
- `css/lesson.css` owns the original ML lesson, diagram, simulator, and metric patterns.
- `css/detailed-question.css` owns the reusable detailed-question shell and component microscope.
- `js/app.js` contains shared platform behavior.
- `js/questions/question-data.js` is the structured content catalog for Questions 02–07.
- `js/questions/detailed-question.js` renders requirements, evolution, components, traces, failures, tradeoffs, and quizzes from that catalog.
- `js/questions/ml-at-scale.js` contains the custom simulation-heavy behavior for Question 01.

## Adding future questions

Copy one of the small detailed-question HTML shells, set its `data-question` slug, and add a matching entry to `question-data.js`. The shared renderer supplies requirements, scale estimates, architecture evolution, component-level explanations, hard-part deep dives, request traces, failure modes, final tradeoffs, interview prompts, and quizzes. Add the numbered entry to the homepage without changing existing URLs.
