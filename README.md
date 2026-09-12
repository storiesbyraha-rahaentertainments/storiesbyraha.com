# [Your Studio Name] — Website

A single-page site built with plain HTML/CSS/JS — no build step, no framework. Files:

- `index.html` — all page content
- `styles.css` — all styling (colors/fonts are set as CSS variables at the top)
- `script.js` — nav scroll effect + mobile menu
- `CNAME` — your custom domain (edit this before you go live)

## 1. Customize the content

Open `index.html` and replace every `[Bracketed Placeholder]` — your studio name, bio, services, pricing, testimonials, email, phone, and social links.

Photo/portfolio blocks are placeholders (dashed pattern with a label). To swap in real photos:
1. Create an `assets/` folder next to `index.html`.
2. Drop your images in there (compress them first — aim under 300KB each; use [squoosh.app](https://squoosh.app) if needed).
3. Replace a placeholder `<div class="hero__frame">` or `<div class="portfolio__item">` with an `<img src="assets/your-photo.jpg" alt="...">` tag.

## 2. Set up the contact form

The form currently posts to Formspree (a free static-form service):
1. Go to [formspree.io](https://formspree.io) and create a free account.
2. Create a new form — it gives you an endpoint URL like `https://formspree.io/f/abc123`.
3. In `index.html`, replace `https://formspree.io/f/YOUR_FORM_ID` with your real endpoint.

## 3. Push to GitHub

```bash
cd wedding-site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

(Create the empty repo on GitHub first via "New repository" — don't initialize it with a README there, to avoid a merge conflict.)

## 4. Turn on GitHub Pages

1. In your repo on GitHub, go to **Settings → Pages**.
2. Under "Build and deployment," set **Source** to `Deploy from a branch`.
3. Set **Branch** to `main` and folder to `/ (root)`. Save.
4. GitHub will give you a URL like `https://YOUR_USERNAME.github.io/YOUR_REPO/` — wait a minute or two for the first deploy.

## 5. Connect your custom domain

**If your domain is the root, e.g. `yourstudio.com`:**
1. Open the `CNAME` file in this repo and replace its contents with your domain, e.g. `yourstudio.com` (just the domain, nothing else).
2. At your domain registrar (GoDaddy, Namecheap, Google Domains, etc.), add these DNS **A records** for `@`, pointing to GitHub's IPs:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
3. Also add a **CNAME record** for `www` pointing to `YOUR_USERNAME.github.io`.

**If you're using a subdomain, e.g. `www.yourstudio.com` only:**
1. Set the `CNAME` file to `www.yourstudio.com`.
2. Add a **CNAME record** for `www` pointing to `YOUR_USERNAME.github.io`.

4. Back in **Settings → Pages** on GitHub, enter your custom domain in the "Custom domain" field and save. Check "Enforce HTTPS" once it becomes available (can take up to 24 hours for the SSL certificate to issue).

DNS changes can take anywhere from a few minutes to 24–48 hours to propagate.

## Notes

- The site is fully static — no server, no database, no dependencies beyond Google Fonts.
- It's responsive down to mobile and respects reduced-motion preferences.
- Feel free to duplicate `index.html` into `about.html`, `portfolio.html`, etc. if you outgrow a single page — just copy the `<nav>` and `<footer>` blocks and update the CSS link path.
