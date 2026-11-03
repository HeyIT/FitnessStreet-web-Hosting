# Fitness Street Edinburgh Static Website

This repository contains the static HTML version of the Fitness Street Edinburgh landing page.

The site is intentionally simple: it is a single `index.html` file with embedded CSS, plus the logo and SEO files. There is no React build step, no backend, no database, and no paid hosting requirement for the basic site.

## What Is Included

- `index.html` - the full landing page and styling.
- `logo.png` - the Fitness Street logo used at the top of the page and for SEO/social previews.
- `assets/` - bundled placeholder images used in the space section.
- `robots.txt` - tells search engines the site can be indexed.
- `sitemap.xml` - tells search engines the main page URL.
- `_headers` - basic Cloudflare security headers.
- `.gitignore` - keeps local computer files out of Git.

## Main Site Details

- Business name: Fitness Street Edinburgh
- Website: `https://www.fitness-street.co.uk/`
- Email: `info@fitness-street.co.uk`
- Address: `545-551 Gorgie Road, Edinburgh`
- Instagram: `https://www.instagram.com/fitness_street_edinburgh`
- Join link: `https://fitnessstreet.clubright.co.uk/MemberArea/SelectMembership`

## How To Edit The Site

For simple text changes, open `index.html` and search for the text you want to change.

Common things to update:

- Hero headline: search for `Edinburgh’s New Standard in Fitness`
- Join button link: search for `fitnessstreet.clubright.co.uk`
- Email address: search for `info@fitness-street.co.uk`
- Google map: search for `google.com/maps`
- Brand links: search for `ecpgym.com`, `endangeredfightwear.com`, or `theecpcharity.com`
- Space section images: replace the files in `assets/` and keep the same file names, or update the image paths in `index.html`

After editing, open `index.html` in a browser to check the page before publishing.

## Image Notes

The current space section images are bundled locally in `assets/` so the site does not depend on remote placeholder URLs.

They are placeholder images sourced from Unsplash under the Unsplash License. Unsplash allows free commercial and non-commercial use without required attribution, but the owner should replace these with real Fitness Street photos when available.

## Publishing To Cloudflare Pages With GitHub

This is the recommended setup once the site is in GitHub. Cloudflare will automatically publish the site whenever changes are pushed to the main branch.

1. Log in to Cloudflare.
2. Go to `Workers & Pages`.
3. Choose `Create application`.
4. Choose `Pages`.
5. Choose `Connect to Git`.
6. Connect the GitHub account that owns this repository.
7. Select this repository.
8. Use these build settings:
   - Framework preset: `None`
   - Build command: leave blank
   - Build output directory: `/`
9. Click `Save and Deploy`.
10. After deployment, Cloudflare will provide a temporary `.pages.dev` URL.

## Adding The Real Domain In Cloudflare

Once the site is deployed:

1. Open the Cloudflare Pages project.
2. Go to `Custom domains`.
3. Add `www.fitness-street.co.uk`.
4. Follow Cloudflare's DNS instructions.
5. Add the root domain `fitness-street.co.uk` as well if the owner wants both versions to work.

Recommended final setup:

- `https://www.fitness-street.co.uk/` shows the site.
- `https://fitness-street.co.uk/` redirects to `https://www.fitness-street.co.uk/`.

## Publishing By Manual Upload

Manual upload is useful if the owner does not want GitHub connected.

1. Log in to Cloudflare.
2. Go to `Workers & Pages`.
3. Choose `Create application`.
4. Choose `Pages`.
5. Choose `Upload assets`.
6. Upload the contents of this folder, not the folder itself.
7. Deploy the site.

If changes are made later, repeat the upload with the updated files.

## SEO Notes

The page includes:

- SEO title and meta description.
- Canonical URL.
- Open Graph tags for Facebook, WhatsApp, LinkedIn, and other previews.
- Twitter/X preview tags.
- Local business structured data using `HealthClub`.
- `robots.txt`.
- `sitemap.xml`.

If the final domain changes, update these files:

- `index.html`
- `robots.txt`
- `sitemap.xml`

Search for `https://www.fitness-street.co.uk/` and replace it with the final domain.

## Cloudflare References

- Cloudflare Pages Git setup: `https://developers.cloudflare.com/pages/get-started/git-integration/`
- Cloudflare Pages Direct Upload: `https://developers.cloudflare.com/pages/get-started/direct-upload/`
- Cloudflare custom domains: `https://developers.cloudflare.com/pages/configuration/custom-domains/`
