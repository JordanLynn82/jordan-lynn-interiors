# Jordan Lynn Interiors — Website

A static HTML site for Jordan Lynn Interiors — a solo interior design studio on Long Beach Island, NJ.

## File structure

```
jordan-lynn-interiors/
├── index.html          Home page
├── about.html          About Jordan
├── services.html       Full services breakdown
├── process.html        Deep-dive on the 8-step process
├── contact.html        Contact form (Netlify-enabled)
├── thanks.html         Post-form-submission page
├── 404.html            Custom 404 page
├── netlify.toml        Netlify build + security config
├── css/
│   └── styles.css      All styling. Single source of truth.
└── images/             Drop Jordan's project photos here
```

## Brand system (in `styles.css` :root)

```
Ink Black    #141414   Primary text, nav, CTAs
Off-White    #faf8f4   Primary background
Cream        #f4f1ea   Secondary surface (services, alt sections)
Sand         #c9b89d   Accent (trade bar, dividers, hovers)
Tan          #8a7556   Labels, secondary accents
Stone Gray   #6b6b6b   Body text
Hair         #e8e4dc   Subtle borders
```

Fonts: Cormorant Garamond (display) + Jost (body). Loaded from Google Fonts.

## Running locally

Just open any `.html` file in your browser. Or for a proper local server:

```bash
# Python 3
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying to Netlify (via GitHub)

### 1. Put this folder on GitHub

1. Create a free account at github.com
2. New repo → name it `jordan-lynn-interiors` → make it private if you want
3. Upload the entire folder (drag-and-drop works on GitHub's web interface)

### 2. Connect to Netlify

1. Sign up at netlify.com using GitHub
2. "Add new site" → "Import an existing project" → "Deploy with GitHub"
3. Pick the `jordan-lynn-interiors` repo
4. Leave all defaults (no build command, publish dir `.`)
5. Deploy. Your site is live on a `.netlify.app` URL in ~60 seconds.

### 3. Connect the domain

In Netlify → Site → Domain management → Add custom domain → `jordanlynninteriors.com`.

Netlify will show you DNS instructions. Two options:

- **Easy (recommended if no email on the domain):** Change nameservers at Squarespace Domains to Netlify's. Netlify handles DNS, SSL, and www redirect automatically.
- **Preserve email (if `@jordanlynninteriors.com` has a mailbox anywhere):** Keep Squarespace nameservers and add only the A record + CNAME Netlify tells you to. Your MX records stay untouched.

⚠️ Screenshot DNS records before changing anything. If MX records disappear, email goes dark.

DNS propagates in 15 min – 2 hours. SSL auto-provisions.

### 4. Enable the contact form

Netlify form detection is automatic — the `data-netlify="true"` attribute on the form tells Netlify to catch submissions. After your first deploy:

1. Submit a test message through the live site
2. Netlify dashboard → Forms → you'll see the submission
3. Set up email notifications: Forms → Settings → Notifications → add Jordan's email

Free tier: 100 submissions/month.

## Editing content

All copy is in the `.html` files. All styling is in `css/styles.css`. There is no build step — save the file, commit to GitHub, Netlify redeploys in 10 seconds.

### Swapping placeholder images for real photos

Current images are Unsplash URLs embedded in either inline `style` attributes or `css/styles.css`.

Search `styles.css` and the HTML files for `unsplash.com` — every placeholder is easy to spot. To replace:

1. Drop the real photo in `/images/` (e.g. `images/kitchen-01.jpg`)
2. Replace the Unsplash URL with `images/kitchen-01.jpg`
3. Commit. Done.

Recommended: compress images to under 400KB before uploading. Tools like tinypng.com or squoosh.app work great.

## Common edits cheatsheet

| Change | File |
|---|---|
| Colors, fonts, spacing | `css/styles.css` top (`:root`) |
| Hero headline | `index.html` – `<h1>` inside `.hero` |
| Bio copy | `about.html` |
| Services copy | `services.html` |
| Process copy | `process.html` |
| Form fields | `contact.html` |
| Footer | all 5 pages (keep in sync — or pull into a JS include later) |

## Future improvements (when ready)

- [ ] Portfolio page with before/after case studies (once afters exist)
- [ ] Journal/blog for SEO + sharing
- [ ] Testimonials section
- [ ] Trade vendor list page (client-facing, linked from services)
- [ ] Analytics (Plausible recommended — privacy-friendly, $9/mo)
- [ ] Favicon + social share image

## Contact for site questions

Built with Claude. Re-open any conversation in Claude to request edits, new pages, or changes.
