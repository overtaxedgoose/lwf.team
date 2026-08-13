# lwf.team

Static site for Leaders Worth Following (501(c)3 nonprofit), hosted on GitHub Pages
(repo: overtaxedgoose/lwf.team). Migrated from GoDaddy Websites+Marketing in August 2026.

## Structure
- Plain HTML/CSS, no build step. Pushing to `main` deploys via GitHub Pages.
- Top-level pages: index, coaches, trips, schools, corporate, resources, contact, donate,
  trish-currie, family (unlisted), trishcurrie (redirect → /trish-currie)
- Blog: `blog/index.html` (/blog) and `blog/f/<slug>.html` (must keep the /blog/f/ path — it is
  the GoDaddy blog URL scheme and is linked/indexed externally)
- `assets/css/style.css` — fonts: Poppins (headings) + Nunito Sans (body); navy + blue→teal gradient from the LWF logo

## External integrations
- Donations: Givebutter — /donate embeds https://givebutter.com/embed/c/lwf;
  /trips uses the Givebutter widget (acct WLHKoUOW9ZEzMINM, widget id j1Xdv5)
- Several Google Forms already owned by the team are linked from /schools and /resources
- Contact + newsletter are NATIVE forms styled to the site that POST silently (fetch no-cors)
  to private Google Forms — do not replace with iframes, they look bulky:
  - "LWF Get a Coach" on /contact: /d/e/1FAIpQLScEg5l8jsZ2nyHcnkPVvxTx6Yb9D_2xAIkAr9GwGTCXqerQ7Q
    fields: emailAddress, entry.1873403862 (Your Name), entry.1935784512 (Phone)
  - "LWF Newsletter" on home: /d/e/1FAIpQLSeVkGFbYw2uEzGu57V3dZ8wBdSlFuAIHmBQaAV0Bn9Tawet4A
    fields: emailAddress (localStorage lwf-newsletter-done prevents dupes)
  Both owned by patrick@jajehgroup.com with email notifications on. If form questions ever
  change, re-extract entry IDs from the viewform data-params attributes.
- Coach referral emails: grace@/joel@thebreakthroughpeople.com, trishcurrie@lwf.team;
  schools pricing: keithcurrie@lwf.team; corporate: patrick@jajehgroup.com

## Rules
- NEVER publish an email address anywhere on this site — all contact routes to /contact
  (the native form). This includes coach emails and thebreakthroughpeople.com addresses.
- pk@lwf.team is in charge of LWF (not Trish — she is one of the coaches). Don't present
  Trish as the org contact.
- /trips is hidden (redirects home) because the South Asia 2026 trip is past — restore the
  page from git history and re-add nav links/sitemap entry when a new trip is planned.
- Every legacy URL path must keep working: /coaches /trips /schools /corporate /resources
  /contact /donate /blog /blog/f/<slug> /trishcurrie /trish-currie /family
- /family and /trishcurrie are unlisted (not in nav) on purpose.
- DNS at GoDaddy; email on Google Workspace — never change NS/MX/TXT records.
