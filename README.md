## Deployment log

Created: 2026-05-19
Project folder: ~/Downloads/Projects/dvocean-site
GitHub repo: https://github.com/WaltBuilder/dvocean-site
Target domain: dvocean.com (DNS at Cloudflare)
Host: Vercel

### Files
- index.html (42 KB) — full site, single file, WebGL background
- vercel.json — security headers + cache-control
- azul-art.png (7.5 MB) — EP cover art
- DEPLOY.md — deployment walkthrough
- README.md — project readme
- .gitignore — standard ignores

### Build configuration
- No build step. Static HTML.
- Vercel framework preset: Other
- Output directory: ./

### Tasks completed (this session)
- [x] Design system from album art (deep blue + koi orange palette, Cormorant + Inter type)
- [x] WebGL atmospheric background (caustic noise shader, ~60fps, pauses when tab hidden)
- [x] Hero with animated entrance + scroll cue
- [x] Music section with EP cover, tracklist, streaming buttons (placeholders)
- [x] Booking inquiry form (mailto bookings@dvocean.com)
- [x] Footer with Instagram link (@wearedvocean)
- [x] Responsive down to mobile, reduced-motion fallback
- [x] HTML syntax validated
- [x] Project folder organized at ~/Downloads/Projects/dvocean-site
- [x] Album art wired to azul-art.png

### Pending (require user action)
- [ ] git init + push to github.com/WaltBuilder/dvocean-site
- [ ] Connect Vercel to repo + first deploy
- [ ] Attach dvocean.com domain in Vercel
- [ ] Configure DNS A record (76.76.21.21) + CNAME for www at Cloudflare
- [ ] Replace placeholder streaming URLs with real Spotify/Apple/Bandcamp/SoundCloud links
- [ ] Replace placeholder tracklist with real titles + durations
- [ ] Optional: swap mailto form for Formspree once dvocean.com email is configured
