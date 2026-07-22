# Fueled by Meesch — Website

A responsive, parallax marketing site for Michelle's nutrition coaching practice, built as a static site for GitHub Pages.

## What's inside
```
index.html          Main page (all sections)
css/styles.css       All styling, design tokens at the top
js/main.js           Parallax, mobile nav, scroll reveal, FAQ accordion
assets/images/       Logo + favicon, exported from your .ai file
CNAME                Custom domain config for GitHub Pages
robots.txt           Search engine crawling rules
sitemap.xml          Search engine sitemap
llms.txt             Plain-text summary for AI answer engines (2026 AEO practice)
```

## 1. Publish to GitHub Pages
1. Create a new GitHub repository (e.g. `fueledbymeesch-site`).
2. Upload all files in this folder to the repository root (keep the folder structure).
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment," set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`.
5. Save. GitHub will give you a `https://<username>.github.io/<repo>` URL within a minute or two.

## 2. Connect your custom domain (fueledbymeesch.com)
1. The `CNAME` file already contains `www.fueledbymeesch.com` — don't delete it.
2. At your domain registrar (wherever you bought fueledbymeesch.com), add these DNS records:
   - **CNAME** record: `www` → `<your-github-username>.github.io`
   - For the root domain (`fueledbymeesch.com` without www) add **A records** pointing to GitHub's IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
3. Back in **Settings → Pages**, enter `www.fueledbymeesch.com` as your custom domain and check **Enforce HTTPS** once it's available (can take up to 24 hrs for DNS to propagate).

## 3. Swap in your real photos
- Replace the placeholder image in the About section: search `index.html` for `placehold.co` and swap the `src` for your own photo path (e.g. `assets/images/michelle.jpg`), and update or remove the `.placeholder-tag` div right below it.
- Drop your photo files into `assets/images/`.

## 4. Connect the contact form (currently a placeholder)
The message form points to Formspree, a free service for static-site forms:
1. Go to https://formspree.io and create a free account.
2. Create a new form, and it will give you an endpoint like `https://formspree.io/f/abcd1234`.
3. In `index.html`, find `action="https://formspree.io/f/yourFormID"` and replace `yourFormID` with your real ID.
4. Submissions will arrive directly in your inbox at michelle@fueledbymeesch.com.

## 5. Connect the newsletter signup (currently a placeholder)
The "Join the list" form needs an email provider endpoint:
1. Sign up for Mailchimp, ConvertKit, or similar (all have free tiers for small lists).
2. Create an embedded/form signup and copy the form's `action` URL and field `name` attributes.
3. In `index.html`, find `<form class="newsletter-form" action="#" method="post">` and replace `action="#"` with your real endpoint, matching field names as needed.

## 6. Add real testimonials
Once you have client quotes, open `index.html`, find the `.proof-grid` section, and replace the placeholder `quote-card` blocks with real quotes and names (only with your clients' permission).

## Notes on design decisions
- Colors and the icon mark are pulled directly from your logo file (gold `#F3C550`, sage `#6D8E71`, cream `#FDE1A0`, charcoal `#231F20`).
- The arc/curve motif in the hero headline and section dividers echoes the curved "Fueled / Meesch" lettering in your logo — this is the site's signature visual detail.
- The "How It Works" section is numbered because it's a real, ordered process. The "Coaching Areas" grid is intentionally unordered since those are parallel categories, not steps.
- Parallax and scroll-reveal motion automatically turn off for visitors with "reduce motion" accessibility settings enabled.
