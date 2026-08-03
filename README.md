# AurinkoTech — Corporate Website

A static one-page corporate profile for **AurinkoTech UG (haftungsbeschränkt)**, a German
technology company working across hardware distribution/development and in-house software.
Built to the company's Canva brochure design (deep navy + silver + light-grey, alternating
dark/light sections).

No build step, no framework — plain HTML/CSS/JS, ready for **GitHub Pages**.

## Structure

```
.
├── index.html          # Single-page site (Hero, About, Leadership, What We Do, Developments, Contact)
├── impressum.html      # Legal Notice (Impressum)
├── css/styles.css      # All styling
├── js/main.js          # Nav, mobile menu, scroll reveals
├── assets/             # Logo, founder photos, StudyShorts robot
├── design-source/      # Original design exports (1–7.svg) — reference only, not served
├── .nojekyll           # Tell Pages to serve files as-is
└── .github/workflows/deploy.yml   # Auto-deploy to Pages
```

## Preview locally

Any static file server works. For example:

```bash
# Python
python -m http.server 8000
# or Node
npx serve .
```

Then open <http://localhost:8000>.

## Deploy to GitHub Pages

1. Create a GitHub repository and push this folder as the repo root:

   ```bash
   git init
   git add .
   git commit -m "Initial AurinkoTech website"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```

2. In the repo: **Settings → Pages → Build and deployment → Source → "GitHub Actions"**.
   The included workflow (`.github/workflows/deploy.yml`) publishes on every push to `main`.

   *Alternative:* Source → "Deploy from a branch" → `main` / `/ (root)` also works, since
   the site is plain static files at the repo root.

3. Your site goes live at `https://<you>.github.io/<repo>/`.
   For a `<you>.github.io` user/org repo it serves at the root domain.

### Custom domain (optional)

Add a `CNAME` file at the repo root containing your domain (e.g. `aurinkotech.com`) and
configure DNS per GitHub's docs.

## Notes / TODO for the client

- **Email** `info@aurinkotech.com` is taken from the brochure and marked "to be confirmed"
  there — verify before launch.
- Replace `assets/logo.png` with an SVG logo if a vector version becomes available (sharper).
- All copy is transcribed verbatim from the design; edit in `index.html`.
