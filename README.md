# Adeyemi Opeyemi Emmanuel — Portfolio Website

A single-page portfolio site for **Adeyemi Opeyemi Emmanuel**, Christian nonfiction book editor, built to showcase editing services, portfolio, and contact info to prospective Upwork/direct clients.

Live design: manuscript/editorial theme in deep teal (`#004643`) and cream (`#f0ede5`), with a red-ink "track changes" accent tying the visuals to the book-editing niche.

---

## 📁 What's in this repo

```
├── index.html          ← the entire website (self-contained, image embedded)
├── robots.txt           ← tells search engines to crawl the site
├── sitemap.xml           ← sitemap for search engines
└── assets/
    └── og-image.jpg      ← preview image used when the site is shared on social media
```

`index.html` is fully self-contained — the hero photo is embedded directly as base64, so there is no broken-image risk even if `assets/` isn't set up correctly. The only reason `assets/og-image.jpg` exists separately is that social media preview cards (Open Graph/Twitter) require a real image URL, not embedded data.

---

## 🚀 Deploy to GitHub Pages (step by step)

1. **Create a new repository** on GitHub (e.g. `adeyemi-editorial`). It can be public or private — GitHub Pages needs it to be public, or you need GitHub Pro for a private Pages site.
2. **Upload the files** from this folder into the root of that repository, keeping the same structure (`index.html`, `robots.txt`, `sitemap.xml`, and the `assets/` folder with `og-image.jpg` inside it).
3. In your repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Under **Branch**, choose `main` (or `master`) and `/ (root)`, then **Save**.
6. Wait 1–2 minutes. GitHub will give you a live URL that looks like:
   `https://your-username.github.io/your-repo/`

That's it — the site is live.

---

## ✏️ One thing to update before you publish

Three files reference a placeholder URL: `https://your-username.github.io/your-repo/`. This is used for SEO tags (canonical link, Open Graph, Twitter card) and the sitemap. Once you know your real GitHub Pages URL:

1. Open `index.html` and use Find & Replace to swap every instance of `your-username.github.io/your-repo` for your real address.
2. Do the same in `robots.txt` and `sitemap.xml`.

(There are about 6 instances in `index.html` — they're all in the `<head>` section near the top of the file.)

---

## 🛠 Making changes later

Everything is in one file (`index.html`), organized top to bottom in the order it appears on the page:

| Section | What it covers |
|---|---|
| `<head>` | Page title, meta description, SEO/social tags, structured data (JSON-LD) |
| `<style>` | All the site's design — colors are defined once at the top under `:root` |
| Header/nav | Logo, menu links, WhatsApp button |
| `#top` (hero) | Headline, intro, photo, credentials |
| `#services` | Developmental / line / copy editing |
| `#fit` | Who you work best with / what you don't do |
| `#process` | The 4-step working process |
| `#portfolio` | Sample manuscripts/projects |
| `.proof` | Stats band (Job Success, Top Rated, etc.) |
| `#faq` | Accordion FAQ |
| `#contact` | WhatsApp/email contact card |
| Footer | Copyright and repeated nav links |

**To change your colors:** edit the values inside `:root { ... }` near the top of the `<style>` block — `--ink` (teal) and `--page` (cream) control almost everything.

**To update contact info:** search for `2349036422332` (WhatsApp) and `adeyemiope34@gmail.com` (email) — each appears a few times across buttons and the contact card.

**To add a new FAQ:** copy one `<details class="faq-item">...</details>` block in the FAQ section and edit the question/answer. If you do, also add a matching entry to the `FAQPage` JSON-LD block in `<head>` so search engines and AI answer engines pick it up too.

**To add a new portfolio piece:** copy one `.folio-card` block inside `#portfolio` and edit the tags, title, description, and status.

No build tools, frameworks, or `npm install` needed — it's plain HTML, CSS, and a small amount of vanilla JavaScript (for the mobile menu, scroll-spy, and back-to-top button).

---

## 📌 Notes

- The site works fully without JavaScript for its core content (FAQ accordion uses native `<details>`); JS only adds the mobile menu toggle, active nav highlighting, and back-to-top button.
- No contact form is included, since GitHub Pages can't run a backend — the WhatsApp and email buttons open pre-filled messages instead, which works reliably with zero setup.
- If you ever want a custom domain (e.g. `adeyemiedits.com`) instead of the `github.io` address, GitHub Pages supports that under **Settings → Pages → Custom domain**.
