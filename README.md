# Othman Alshaya — Portfolio Website

A single-page portfolio website built with vanilla HTML + CSS + minimal JS. No build step required. Deploys directly to GitHub Pages.

---

## 📁 Project Structure

```
portfolio/
├── index.html              ← Main site (HTML + embedded CSS + JS)
├── assets/
│   ├── photo.jpg           ← Your professional photo
│   └── Othman_Alshaya_CV.pdf  ← Your CV (linked from Hero + Contact)
└── README.md               ← This file
```

---

## 🚀 Deploy to GitHub Pages (5 minutes)

### Step 1 — Create the repository
1. Sign in to [github.com](https://github.com) (create a free account if needed).
2. Click the **+** icon (top-right) → **New repository**.
3. **Important**: Name the repo exactly `<your-username>.github.io`
   (example: if your GitHub username is `othmanalshaya`, name it `othmanalshaya.github.io`).
4. Set it to **Public**.
5. Do **not** initialize with a README — leave it empty.
6. Click **Create repository**.

### Step 2 — Upload the files
**Option A — Drag & drop (easiest):**
1. On the empty repo page, click **uploading an existing file**.
2. Drag the entire contents of the `portfolio` folder into the browser
   (`index.html`, the `assets/` folder, and this README).
3. Scroll down, write a commit message like "initial site", and click **Commit changes**.

**Option B — Git command line:**
```bash
cd portfolio
git init
git add .
git commit -m "initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. In your repo, go to **Settings** (top tab) → **Pages** (left sidebar).
2. Under **Build and deployment** → **Source**, select **Deploy from a branch**.
3. Branch: **`main`**, folder: **`/ (root)`**.
4. Click **Save**.
5. Wait ~1–2 minutes. Refresh the Settings → Pages screen.

### Step 4 — Visit your site
Your site is live at:
```
https://<your-username>.github.io
```

---

## 🔧 Customize Content

All content lives inside `index.html`. Open it in any text editor (VS Code, Sublime, even Notepad) and use **Find** (Ctrl/Cmd + F) to locate sections.

### Common edits:

| What to change | Search for | Notes |
|---|---|---|
| Page title (browser tab) | `<title>` | Line ~6 |
| Meta description (SEO) | `<meta name="description"` | Line ~7 |
| Hero headline | `Operations<br>that` | Big rotating headline |
| Hero subtitle | `I'm Othman` | The 2-line intro under the headline |
| Stats numbers | `12<span class="plus"` | Numbers in the stats band |
| About paragraphs | `id="about"` | Long-form about copy |
| Experience entries | `id="experience"` | Each `<div class="exp-item">` is one job |
| Skills cards | `id="expertise"` | Each `<div class="skill-card">` is one skill |
| Achievement cards | `id="achievements"` | Each `<article class="project-card">` |
| Certifications | `id="certifications"` | Two lists: completed + in progress |
| Contact info | `oalshaya@hotmail.com` | Email, phone, LinkedIn URL |

---

## 💬 Enable Testimonials (LinkedIn Recommendations)

The testimonials section is built but hidden until you have content. To enable:

1. Open `index.html` and find:
   ```html
   <section id="testimonials" style="display: none;">
   ```
2. Remove `style="display: none;"` so it becomes just `<section id="testimonials">`.
3. Inside, find the `<article class="testimonial">` blocks and replace the bracketed `[…]` placeholders with real LinkedIn recommendation text.
4. Duplicate the `<article>` block for each additional recommendation.
5. Update the avatar initials (e.g. `AB`) and the name/role lines.

Optionally, also add a nav link by adding this `<li>` to the `<ul class="nav-links">` near the top:
```html
<li><a href="#testimonials">Testimonials</a></li>
```

---

## ✍️ Enable Medium Blog Feed

The Insights section auto-pulls your Medium posts via RSS. To activate:

1. Open `index.html` and find:
   ```html
   <section id="insights" style="display: none;">
   ```
   Remove `style="display: none;"`.
2. Near the bottom of the file, find the `OPTIONAL: Medium RSS integration` comment block.
3. **Uncomment the JavaScript block** (remove `/*` and `*/` surrounding it).
4. Change `YOUR_MEDIUM_HANDLE` to your actual Medium username (without the `@`).
5. Save & redeploy. Your latest 4 Medium posts will auto-load.

---

## 🎨 Change the Color Theme

The entire palette is controlled by CSS variables at the top of the `<style>` block. Search for `:root {` and modify:

```css
--bg:           #0A1410;   /* page background */
--teal:         #5EEAD4;   /* primary accent */
--amber:        #FCD34D;   /* secondary accent */
--text:         #E8F0EE;   /* primary text */
```

### Pre-built alternatives:

**AWS-style (blue + orange):**
```css
--bg:    #0F172A;
--teal:  #FF9900;   /* AWS orange */
--amber: #00A4EF;   /* AWS blue */
```

**Light editorial (white + ink):**
```css
--bg:        #FAFAF7;
--bg-elev:   #FFFFFF;
--bg-card:   #FFFFFF;
--border:    rgba(0,0,0,0.08);
--border-strong: rgba(0,0,0,0.18);
--teal:      #0D3B66;
--text:      #1A1A1A;
--text-dim:  #555555;
--text-muted:#888888;
```

**Royal navy + gold:**
```css
--bg:    #0A1628;
--teal:  #D4AF37;
--amber: #C8A951;
```

---

## 📸 Replace Your Photo

Drop a new image into `assets/` and name it `photo.jpg` (or update the `<img src=…>` reference inside `index.html`).

**Recommended specs:**
- Square aspect ratio (1:1) — the site crops to circle
- 800×800 px minimum
- < 200 KB for fast loading

---

## 🌐 Use a Custom Domain (Optional)

1. Buy a domain (Namecheap, Cloudflare, GoDaddy).
2. In your repo → **Settings** → **Pages** → **Custom domain**, enter `yourdomain.com`.
3. At your domain registrar, set DNS:
   - `A` records pointing to: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Optional `CNAME` (`www`) → `<your-username>.github.io`
4. Wait for DNS to propagate (~15 min to 24 hr), then enable **Enforce HTTPS**.

---

## 🛠 Local Preview (Optional)

Before deploying, you can preview the site locally:

**Easiest** — Just double-click `index.html`. It opens in your browser.

**Better** — Use any local server:
```bash
# Python (built-in on Mac/Linux)
cd portfolio
python3 -m http.server 8000
# Then visit http://localhost:8000

# Or with Node
npx serve .
```

---

## ✅ Pre-launch Checklist

- [ ] All `[bracketed placeholders]` replaced with real content
- [ ] Email + phone + LinkedIn URLs correct in Contact section
- [ ] Photo loads correctly
- [ ] CV download link works
- [ ] Site tested on mobile (use Chrome DevTools mobile view)
- [ ] Page title and meta description match your brand
- [ ] LinkedIn profile URL up-to-date

---

## 📞 Need help?

This site was structured to be edited by anyone — no framework, no build step, no dependencies. If something breaks, the worst case is reverting `index.html` to the original version from this folder.

Built single-file by design. Designed to last.
