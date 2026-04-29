# Study Hub

A personal study guide website. Every guide is a single self-contained HTML file. Adding a new guide takes about 60 seconds.

---

## File Structure

```
your-repo/
├── index.html          ← Landing page — edit this to add new guides
├── guides/
│   ├── audit407.html   ← Audit & Assurance study guide
│   └── ...             ← Add new guides here
└── README.md
```

---

## How to Add a New Guide

### Step 1 — Drop the HTML file into `guides/`

```
guides/yourcourse.html
```

### Step 2 — Add one object to the `guides` array in `index.html`

Open `index.html` and find the `const guides = [...]` array (it has a big comment above it). Add your entry:

```js
{
  id:       "finc341",          // unique slug — no spaces
  course:   "FINC 341",         // course code shown on card
  title:    "Corporate Finance", // guide title
  desc:     "Capital budgeting, WACC, capital structure, and valuation.",
  file:     "guides/finc341.html",  // path relative to index.html
  icon:     "📈",               // single emoji
  color:    "teal",             // purple | teal | gold | coral | blue | green
  tags:     ["10 sections", "20 questions"],
  subject:  "Finance",          // used for the filter pills
  sections: 10,
  updated:  "May 2025",
},
```

That's it. Save, push to GitHub, and Netlify auto-deploys in ~30 seconds.

---

## Card Color Options

| Value    | Best for           |
|----------|--------------------|
| `purple` | Accounting / Audit |
| `teal`   | Finance / Economics|
| `gold`   | Business / Strategy|
| `coral`  | Law / Ethics       |
| `blue`   | Stats / Math       |
| `green`  | Science / Other    |

---

## Creating a New Guide from the Template

Every guide should be a single self-contained `.html` file (no external dependencies except Google Fonts). 

The easiest workflow:
1. Copy `guides/audit407.html` as a starting point
2. Clear out the content sections and replace with your course material
3. Update the `<title>` tag and header text
4. Update the sidebar nav buttons and section IDs
5. Replace the quiz questions array with your own questions

The quiz question format:
```js
{
  cat: 'ch1',           // category tag for filter buttons
  q:   "Question text",
  opts: ["A option", "B option", "C option", "D option"],
  ans: 0,               // index of correct answer (0 = A)
  exp: "Explanation shown after answering."
}
```

---

## Deploying

This site is hosted on Netlify connected to this GitHub repo.

1. Make your changes locally
2. `git add . && git commit -m "add FINC 341 guide"` 
3. `git push`
4. Netlify auto-deploys — usually live in under 1 minute

No build step, no npm, no config. Just HTML files.
