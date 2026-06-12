# Gopikashree — Data Analyst Portfolio

A premium, recruiter-focused single-page portfolio website.

---

## Folder Structure

```
gopikashree-portfolio/
├── index.html              ← Complete website (all-in-one file)
├── assets/
│   ├── gopikashree.jpg     ← Your professional photo (replace placeholder)
│   ├── gopikashree-resume.pdf ← Your resume PDF
│   └── og-cover.png        ← 1200×630px Open Graph preview image
└── README.md
```

---

## Quick Setup

### 1. Add your photo
Replace the avatar placeholder in `index.html`:

Find this block:
```html
<div class="avatar-placeholder" ...>GK</div>
```

Replace with:
```html
<img class="avatar-img" src="assets/gopikashree.jpg" alt="Gopikashree, Data Analyst" />
```

### 2. Add your resume
Drop `gopikashree-resume.pdf` into the `assets/` folder.
The download button already points to `assets/gopikashree-resume.pdf`.

### 3. Update contact details
Search for `gopikashree@email.com` and `gopikashree` in the LinkedIn/GitHub URLs and replace with your actual details.

### 4. Set up the contact form (free options)
The form currently shows a browser alert. Connect it to a real email service:

**Option A — Formspree (easiest, free):**
1. Sign up at https://formspree.io
2. Get your form endpoint (e.g. `https://formspree.io/f/xrgjabc`)
3. Replace `handleFormSubmit()` in the script with:

```js
async function handleFormSubmit() {
  const data = {
    name: document.getElementById('name').value,
    email: document.getElementById('email').value,
    subject: document.getElementById('subject').value,
    message: document.getElementById('message').value
  };
  const res = await fetch('https://formspree.io/f/YOUR_ID', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(data)
  });
  if (res.ok) alert('Message sent! I\'ll reply within 24 hours.');
}
```

---

## Deploy to GitHub Pages (Free)

1. Create a GitHub repository named `yourusername.github.io`
2. Upload all files from this folder to the repository root
3. Go to **Settings → Pages → Source: main branch / root**
4. Your site is live at `https://yourusername.github.io`

**Custom domain (optional):**
- Buy a domain (Namecheap, ~$10/yr)
- In GitHub Pages settings, add your custom domain
- Create a `CNAME` file in your repo with your domain name

---

## SEO Checklist

- [ ] Update `<title>` with your full name and target role
- [ ] Update `<meta name="description">` — keep it under 155 characters
- [ ] Replace `og:url` and `og:image` with real values
- [ ] Add Google Analytics (free): paste the GA4 snippet before `</head>`
- [ ] Submit your URL to Google Search Console

---

## Favicon (Recommended)

1. Go to https://favicon.io
2. Generate from text: "GK", color `#38BDF8`, background `#0F172A`
3. Download and place `favicon.ico` in the root folder
4. Replace the `<link rel="icon">` tag with:
```html
<link rel="icon" href="favicon.ico" />
```

---

## Continuous Improvement Plan

**Month 1**
- Add 2-3 real project screenshots to the project thumbnails
- Replace placeholder stats with real numbers
- Write 1 detailed case study as a separate page

**Month 2**
- Add Google Analytics to track visitor sources
- Connect LinkedIn to show endorsements/testimonials
- Write a short "data story" blog post and link from the portfolio

**Month 3**
- Add a "Hire Me for Freelance" services page with pricing
- Add a testimonials section once you receive feedback
- Apply to 5 freelance platforms (Upwork, Toptal, Contra) and link this portfolio

---

## Performance Notes

This site is built for speed:
- Single HTML file — zero extra network requests for layout
- Google Fonts loaded with `font-display: swap` via preconnect
- IntersectionObserver used instead of scroll event listeners
- No jQuery, no heavy libraries
- Estimated Lighthouse scores: Performance 95+, Accessibility 95+, SEO 95+
