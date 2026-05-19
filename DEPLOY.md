# D'vocean — Deploy to dvocean.com via Vercel

You have everything you need. Vercel is a perfect fit for this site — it's a single static HTML file, will deploy in ~30 seconds, and Vercel handles the SSL cert + custom domain for free.

## Folder contents

- `index.html` — the site
- `vercel.json` — security headers + asset caching (already configured)
- `azul-art.jpg` — **you add this** (the AZUL album art, square, ~1500×1500px or larger). When this file is present the site uses it automatically; if missing, a styled placeholder shows in its place.

## Step 1 — Add your album art

Drop your `azul-art.jpg` (or `.png`) into this same folder. The site looks for that filename. If you want to rename it, edit one line in `index.html`:

```html
<img id="azul-art" src="azul-art.jpg" ...
```

## Step 2 — Deploy to Vercel

The easiest path (no terminal needed):

1. Go to **vercel.com** and sign in (use GitHub, GitLab, or email).
2. Click **Add New… → Project**.
3. Choose **"Deploy without a Git repo"** OR drag-and-drop this folder into the Vercel dashboard.
   - If Vercel asks for build settings, leave them empty. Framework Preset: **Other**. Output directory: **./** (this folder). No build command.
4. Click **Deploy**. In ~20 seconds you'll get a live URL like `dvocean-xyz.vercel.app`.

Alternative — Vercel CLI (faster for future updates):

```bash
npm install -g vercel
cd "this folder"
vercel              # first-time: links the project
vercel --prod       # ships a production deploy
```

## Step 3 — Point dvocean.com at Vercel

1. In Vercel: open your project → **Settings → Domains**.
2. Type `dvocean.com` and click **Add**. Add `www.dvocean.com` too.
3. Vercel will show you two DNS records to add at your registrar (wherever you bought the domain — Namecheap, GoDaddy, Cloudflare, etc.):
   - An **A record** for `@` (root domain) pointing to `76.76.21.21`
   - A **CNAME** for `www` pointing to `cname.vercel-dns.com`
4. Save those at your registrar. DNS usually propagates within minutes (sometimes up to an hour).
5. Vercel auto-issues an SSL cert. Once it's green, you're live at **https://dvocean.com**.

## Step 4 — Booking form

The form currently uses `mailto:bookings@dvocean.com`, which opens the visitor's email client when they submit. This works, but isn't ideal — many people don't have a desktop mail client set up.

When you're ready to upgrade, swap to **Formspree** (free tier):

1. Create a form at formspree.io with the email `bookings@dvocean.com`.
2. They give you a URL like `https://formspree.io/f/xxxxxx`.
3. In `index.html`, find the `<form class="booking-form" ...>` tag and change:
   - `action="mailto:bookings@dvocean.com"` → `action="https://formspree.io/f/xxxxxx"`
   - `method="post"` → keep as is
   - Remove `enctype="text/plain"`

Inquiries will land in your inbox directly, no mail client required.

## Step 5 — Replace placeholder content

In `index.html`, search for `#` in the streaming buttons and replace with your real URLs:

- Spotify artist page
- Apple Music page
- Bandcamp
- SoundCloud

The tracklist titles in the EP section (`Tideline`, `Saltwater Reverie`, etc.) are placeholders — swap them for your real track titles and durations.

## Quick checklist before launch

- [ ] `azul-art.jpg` added to the folder
- [ ] Real track titles + durations in tracklist
- [ ] Real streaming URLs in the four Spotify/Apple/Bandcamp/SoundCloud buttons
- [ ] Email working (mailto OR Formspree)
- [ ] Site deployed and `dvocean.com` resolving

That's it — the site is ready to ship.
