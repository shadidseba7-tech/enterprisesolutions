# Enterprise Solutions — static website repair

This is a replacement for the custom dynamic `x-dc` site in the public GitHub repo `shadidseba7-tech/enterprisesolutions`. It preserves the public pages and the `.dc.html` route names, but renders plain HTML without the `support.js` runtime.

## Deploy to Vercel
1. Back up the existing repository first.
2. Copy all generated files into the repository root. Overwrite the matching `.dc.html` files and `index.html`.
3. You can delete `support.js`, `Nav.dc.html`, `Footer.dc.html` if nothing else references them; the new pages do not use these files. You can retain the original logo images if desired, but these pages use a CSS wordmark so they are not required.
4. Commit and push to the `main` branch. Vercel's connected GitHub deployment should rebuild the site if automatic deployment is enabled.
5. In Vercel > Project > Settings > Domains, make sure both `enterprise-company.com` and `www.enterprise-company.com` are configured, with `www` the primary destination if preferred. Confirm the redirect yourself.
6. Verify all pages, mobile navigation, contact email, WhatsApp link, and SEO metadata on the deployed URL. Submit `/sitemap.xml` through Google Search Console.

## IMPORTANT: email and forms
The contact form opens the visitor's local email client using `mailto:`. It does NOT silently deliver messages. The visitor must press Send in their email application. This is intentionally honest and prevents the old fake success message.
To accept submissions directly on the page, provision an email provider/backend (e.g. Vercel function with secret server-side credentials or an approved form provider), configure anti-spam, a privacy notice and recipient inbox, and test end-to-end. Do not store SMTP credentials or API tokens in client-side JavaScript.

The old careers form also simulated success without sending data, and its drag/drop CV upload wasn't functional. This version uses a direct career-enquiry email link and asks applicants to attach CVs manually. The old newsletter forms were removed because they had no verified subscriber storage.

## Content approval
The original source contained placeholder image blocks, an asserted testimonials section, project metrics and example leadership titles without names. These were removed or reframed as illustrative topics, rather than publishing unverified claims. Before publishing, the business owner should review all text and confirm services, email, WhatsApp telephone, office hours and claims about capabilities.

## SEO & accessibility
Plain rendered HTML, unique meta descriptions, canonical URL, basic Organization JSON-LD, valid internal navigation, sitemap, robots.txt, accessibility labels and mobile CSS are included. SEO results are not guaranteed; hosting domain, redirects, Google indexing and actual performance still need post-deployment checks.