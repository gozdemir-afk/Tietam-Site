# Tietam's Summer Helpers

A single-file static website advertising Tietam's summer **dog-walking ($10/walk)** and
**plant-watering ($10/visit)** services for neighbors in Westfield, Indiana.

Contact is by **text only** to her mom at **317-445-3198** (no phone calls).

The entire site is one file: [`index.html`](index.html). Plain HTML/CSS with a little
inline SVG — no framework, no build step.

> **Privacy note (please keep in mind before editing):** This is a public website for a
> minor. A couple of details were left off on purpose vs. the printed flyer — her actual
> **photo** (a friendly dog/plant illustration is used instead) and the **name of her
> school** (the page just says "Westfield"). Please keep those out by default.

---

## Run it locally (live reload)

You need [Node.js](https://nodejs.org/) installed (v18+).

```bash
# one-time, installs the dev server
npm install

# start the live-reload dev server
npm run dev
```

This opens <http://localhost:5173> in your browser. Any time you save `index.html`, the
page reloads automatically so you see changes instantly.

To stop the server, press `Ctrl + C` in the terminal.

> No-install alternative: `npx live-server --port=5173` does the same thing without a
> `package.json`.

---

## Deploy it for free

Because it's a single static file, hosting is easy. Three good options:

### Railway (recommended)

Railway can serve a static site directly.

1. Push this folder to a GitHub repo (see below).
2. Go to <https://railway.app> → **New Project** → **Deploy from GitHub repo** → pick this repo.
3. Railway auto-detects a static site. If it asks for a start command, use:
   ```
   npx live-server --port=$PORT --no-browser --host=0.0.0.0
   ```
   (For a production-grade static server you can instead use `npx serve -l $PORT .`.)
4. Railway gives you a public URL. Done.

### Netlify (easiest — drag and drop)

1. Go to <https://app.netlify.com/drop>.
2. Drag this whole folder onto the page.
3. Netlify gives you a live URL instantly. No account or build step required.

### GitHub Pages

1. Push to a GitHub repo (see below).
2. Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**.
3. Choose branch `main` and folder `/ (root)`, then **Save**.
4. Your site appears at `https://<username>.github.io/<repo>/` within a minute or two.

---

## Push to GitHub

```bash
# create an empty repo on github.com first, then:
git remote add origin https://github.com/<username>/tietam-site.git
git push -u origin main
```

---

## Project structure

```
tietam-site/
├── index.html      # the entire website
├── package.json    # dev server script
├── .gitignore
└── README.md
```
