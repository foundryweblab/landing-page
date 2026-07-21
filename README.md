# Ironclad Plumbing Co. — Landing Page

A single-page, static landing page for a local plumbing company. Traditional/classic
styling (parchment cream, deep hunter green, brass accents), fully responsive,
no build tools required.

## Files

```
plumbing-landing/
├── index.html      ← all page content and structure
├── css/styles.css  ← all styling
├── js/main.js      ← mobile nav toggle + contact form handling
└── README.md
```

## 1. Put this on GitHub

```bash
cd plumbing-landing
git init
git add .
git commit -m "Initial landing page"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

## 2. Turn on GitHub Pages

1. Go to your repo on GitHub → **Settings** → **Pages**.
2. Under "Build and deployment," set **Source** to `Deploy from a branch`.
3. Set branch to `main`, folder to `/ (root)`, then **Save**.
4. Stay on (or come back to) that same **Settings → Pages** screen — after a minute or two,
   a banner appears near the top saying "Your site is live at ...". That link is your URL,
   usually in the form:
   `https://YOUR-USERNAME.github.io/YOUR-REPO/`
   If it doesn't show up right away, refresh the page.

Every time you `git push`, the live site updates automatically.

## 3. Replace placeholder content

Everything here is a placeholder — search `index.html` for these and swap in real info:

- **Business name**: currently "Ironclad Plumbing Co." (appears in header, hero, footer, `<title>`)
- **Phone number**: `(860) 555-0142` / `tel:+18605550142` — appears in header, hero, and contact section
- **Address, email, license numbers**: in the `.contact-details` block near the bottom of `index.html`
- **Testimonials**: three placeholder quotes in the Testimonials section
- **Service area towns**: currently lists Connecticut and Westchester County, NY towns
- **Photo**: the About section has an SVG placeholder silhouette — swap it for a real team/owner photo (`<img src="...">`)

## 4. Connect the service area map

The map currently points to a placeholder Google My Maps embed. To use your own:

1. Go to [Google My Maps](https://www.google.com/maps/d/), create a map, and draw/mark your
   Connecticut + Westchester County service area.
2. Click **Share** → get the embed link, or use **Embed on my site** from the map's menu.
3. Replace the `src` attribute on the `<iframe>` inside the `#service-area` section in `index.html`.

## 5. Connect the contact form

Right now the form only shows a placeholder message — it does **not** send an email yet.
Easiest free option is [Formspree](https://formspree.io):

1. Sign up and create a new form, copy your form endpoint (looks like
   `https://formspree.io/f/xxxxxxx`).
2. In `index.html`, change:
   ```html
   <form id="quote-form" novalidate>
   ```
   to:
   ```html
   <form id="quote-form" action="https://formspree.io/f/xxxxxxx" method="POST">
   ```
3. Remove the `e.preventDefault()` block in `js/main.js` (or just delete the form's
   `id="quote-form"` handling there) so the browser submits normally to Formspree.

Alternatives: Netlify Forms (if you host on Netlify instead), or a simple
Google Form embedded/linked from the Contact section.

## 6. Custom domain (optional)

In repo **Settings → Pages**, add your domain under "Custom domain" and follow GitHub's
DNS instructions (usually a CNAME record pointing to `YOUR-USERNAME.github.io`).

## Notes

- No build step, no dependencies beyond Google Fonts (loaded via `<link>` in `<head>`).
- All icons are inline SVG — no image files to manage.
- Mobile menu and form validation are handled in `js/main.js`.

