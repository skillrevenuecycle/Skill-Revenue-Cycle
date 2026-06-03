# Skill Revenue Cycle — Website

A fast, professional, fully static website for a healthcare Revenue Cycle Management (RCM) company. No build step, no frameworks — just HTML, CSS, and a little JavaScript. Perfect for **GitHub + Cloudflare Pages (free)**.

## Pages
| File | Page |
|------|------|
| `index.html` | Home |
| `services.html` | Services |
| `who-we-serve.html` | Who We Serve |
| `about.html` | About |
| `contact.html` | Contact (with form) |
| `404.html` | Not-found page |
| `css/styles.css` | All styling |
| `js/main.js` | Menu, animations, slider, form |

---

## ⚠️ First: fix the domain spelling (1 minute)
Your title said **skillrevenuecycle.com** (with an "e") but your email is **contact@skillrevenucycle.com** (no "e"). They should match. Pick the correct one, then find-and-replace across all files. On your computer you can open the folder in a text editor (VS Code etc.) and use "Replace in Files":

- Replace `skillrevenuecycle.com` → your real domain
- Replace `contact@skillrevenucycle.com` → your real email

These appear in the page `<title>`/meta tags, the footer, the contact page, `robots.txt`, and `sitemap.xml`.

---

## Step-by-step: put it on GitHub
1. Create a free account at https://github.com if you don't have one.
2. Click **New repository**. Name it e.g. `skillrevenuecycle` and make it **Public**. Click **Create repository**.
3. On the new repo page, click **uploading an existing file**.
4. Drag in **all the files and folders** from this project (the `index.html`, the other `.html` files, the `css` folder, and the `js` folder). Keep the folder structure intact.
5. Click **Commit changes**.

(If you prefer the command line:)
```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/skillrevenuecycle.git
git push -u origin main
```

---

## Step-by-step: deploy free on Cloudflare Pages
1. Create a free account at https://dash.cloudflare.com .
2. In the left menu go to **Workers & Pages** → **Create** → **Pages** tab → **Connect to Git**.
3. Authorize GitHub and select your `skillrevenuecycle` repository.
4. On the build settings screen:
   - **Framework preset:** `None`
   - **Build command:** *leave empty*
   - **Build output directory:** `/`  (just a slash — the files are at the repo root)
5. Click **Save and Deploy**. In under a minute you'll get a live URL like `skillrevenuecycle.pages.dev`.

Every time you push a change to GitHub, Cloudflare redeploys automatically.

---

## Connect your custom domain (skillrevenuecycle.com)
1. In Cloudflare Pages → your project → **Custom domains** → **Set up a custom domain**.
2. Enter your domain and follow the prompts.
   - If your domain is already on Cloudflare, it's added automatically.
   - If not, Cloudflare shows you the DNS records (or nameservers) to add at your domain registrar (GoDaddy, Namecheap, etc.).
3. HTTPS/SSL is automatic and free. Done.

---

## Make the contact form actually email you
The form works out of the box (it validates and shows a thank-you message) but doesn't send email until you connect an endpoint. Easiest free option is **Formspree**:

1. Sign up at https://formspree.io (free tier).
2. Create a form; you'll get an endpoint like `https://formspree.io/f/abcdwxyz`.
3. Open `js/main.js`, find this line near the bottom:
   ```js
   const FORM_ENDPOINT = ""; // e.g. "https://formspree.io/f/xxxxxxx"
   ```
   Put your endpoint in the quotes:
   ```js
   const FORM_ENDPOINT = "https://formspree.io/f/abcdwxyz";
   ```
4. Commit + push. Submissions now arrive in your Formspree inbox (and forward to your email).

---

## How to edit content
- **Text:** open any `.html` file and edit the words between the tags.
- **Colors / fonts:** open `css/styles.css` — the palette and fonts are at the very top under `:root`. Change `--brand`, `--accent`, etc. and the whole site updates.
- **Logo:** the "SkillRC" wordmark is in the header/footer of each page. Swap the inline `<svg>` for your own logo image if you have one.
- **Stats / testimonials:** edit directly in `index.html`.

No special tools needed — any text editor works, and you can even edit files directly on GitHub in the browser.
