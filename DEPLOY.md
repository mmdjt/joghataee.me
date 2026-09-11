# Deploy joghataee.me (or whatever .me you buy)

This is a static site. No server, no WordPress, no monthly host fee.

## 0. Files you need on your laptop

```
website/
  index.html
  cv.pdf
  photos/me.jpg
  photos/cat-1.jpg
  photos/cat-2.jpg
  photos/run.jpg
  photos/gym.jpg
```

Download the folder from this chat, add your photos, then follow the steps.

---

## 1. Create a GitHub repo

1. Sign in at https://github.com
2. New repository
3. Name it `joghataee.me` (or `mohammad-joghataee`)
4. Public
5. Do **not** add a README if you will upload these files as the whole site
6. Create

On your computer:

```bash
cd path/to/website
git init
git add .
git commit -m "First version of personal site"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/joghataee.me.git
git push -u origin main
```

Replace `YOUR_GITHUB_USERNAME` and the repo name.

---

## 2. Turn on GitHub Pages

In the repo:

1. Settings → Pages
2. Source: **Deploy from a branch**
3. Branch: `main` / folder: `/ (root)`
4. Save

In a minute the site is live at:

`https://YOUR_GITHUB_USERNAME.github.io/joghataee.me/`

If the repo is named `YOUR_GITHUB_USERNAME.github.io`, the URL is just
`https://YOUR_GITHUB_USERNAME.github.io/`

---

## 3. Buy the .me domain

Good registrars: Namecheap, Porkbun, Spaceship, NameSilo.

Search: `joghataee.me` or `mohammadjoghataee.me`

Students: GitHub Student Pack often includes a free first-year `.me` from Namecheap
(https://education.github.com → pack → Namecheap / nc.me).

Buy **only the domain**. Skip website-builder add-ons.

---

## 4. Point the domain at GitHub Pages

In the GitHub repo:

1. Settings → Pages → Custom domain
2. Type `joghataee.me` (your real domain)
3. Save
4. Check **Enforce HTTPS** after DNS finishes (can take up to 24 hours, often much faster)

Add a file named `CNAME` in the repo root with one line:

```
joghataee.me
```

At your registrar DNS:

**If you use the apex domain (joghataee.me):**

| Type | Name | Value |
|------|------|--------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | YOUR_GITHUB_USERNAME.github.io |

**Simpler option:** use `www.joghataee.me` as CNAME to `YOUR_GITHUB_USERNAME.github.io`
and redirect the apex to www.

Wait for DNS. Then open `https://joghataee.me`.

---

## 5. Update the site later

Change `index.html` or photos, then:

```bash
git add .
git commit -m "Update photos and publications"
git push
```

GitHub Pages rebuilds in about a minute.

---

## Alternative hosts (same files)

- **Cloudflare Pages**: drag the folder, then add the domain. Often the fastest DNS.
- **Netlify**: drag the folder to https://app.netlify.com/drop, then add domain.

Use one host only.
