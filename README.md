# Daihn Kim — Deployment Strategist Portfolio

Live portfolio site: **[daihnkim.github.io/portfolio](https://daihnkim.github.io/portfolio)**

## Deploy to GitHub Pages

### Step 1 — Create a GitHub repo
1. Go to [github.com/new](https://github.com/new)
2. Name it `portfolio` (gives URL: `daihnkim.github.io/portfolio`)
3. Set to **Public**, leave everything else unchecked, click **Create repository**

### Step 2 — Push this folder
Open a terminal inside the `portfolio-web/` folder and run:

```bash
git init
git add .
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/daihnkim/portfolio.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Go to your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)` → **Save**
4. Wait ~60 seconds, then visit: `https://daihnkim.github.io/portfolio`

## Folder Structure

```
portfolio-web/
  index.html                    ← Single-file portfolio (HTML + CSS + JS)
  .nojekyll                     ← Tells GitHub Pages to skip Jekyll processing
  assets/
    screenshots/
      eval/                     ← Evaluation system screenshots (eval-1.png … eval-14.png)
```

## Updating Content

All content is in `index.html`. Search for:
- `TODO_LINKEDIN` → replace with your actual LinkedIn URL handle
- `daihnkim@gmail.com` → confirm email is correct
- Project dates/metrics → update as needed

## Notes
- No build step required — pure HTML/CSS/JS
- All screenshots are in `assets/screenshots/eval/`
- LinkedIn URL is set to `linkedin.com/in/daihnkim` — update if your handle is different
