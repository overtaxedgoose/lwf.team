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
- Contact + newsletter are mailto links (trishcurrie@lwf.team); TODO comments in index.html and
  contact.html mark where to embed Google Forms when created
- Coach referral emails: grace@/joel@thebreakthroughpeople.com, trishcurrie@lwf.team;
  schools pricing: keithcurrie@lwf.team; corporate: patrick@jajehgroup.com

## Rules
- Every legacy URL path must keep working: /coaches /trips /schools /corporate /resources
  /contact /donate /blog /blog/f/<slug> /trishcurrie /trish-currie /family
- /family and /trishcurrie are unlisted (not in nav) on purpose.
- DNS at GoDaddy; email on Google Workspace — never change NS/MX/TXT records.
