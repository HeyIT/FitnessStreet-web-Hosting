# Moving The Domain From Wix To Cloudflare

This document explains the domain move at a high level. It is separate from the website publishing guide because domain changes affect email, DNS, and the existing Wix setup.

## Important Before Starting

Before changing anything, confirm where these are managed:

- Domain registration: probably Wix, but confirm in the Wix account.
- Website hosting: currently Wix.
- Email hosting: could be Microsoft 365, Google Workspace, Wix, or another provider.
- Existing DNS records: these may include email records, verification records, and redirects.

Do not change nameservers until the current DNS records have been copied or understood.

## Option A: Keep The Domain Registered At Wix, Use Cloudflare For DNS And Hosting

This is usually the practical option.

What happens:

- The owner still pays Wix for the domain registration if the domain is registered there.
- Cloudflare becomes the DNS provider.
- Cloudflare Pages hosts the new website.
- Wix no longer hosts the main website.

Steps:

1. Log in to Cloudflare.
2. Add the domain `fitness-street.co.uk`.
3. Cloudflare will scan existing DNS records.
4. Carefully check the imported DNS records, especially email records.
5. In Wix, find the domain settings.
6. Replace the Wix nameservers with the two Cloudflare nameservers.
7. Wait for DNS to update. This can take minutes, but allow up to 24-48 hours.
8. In Cloudflare Pages, add the custom domain `www.fitness-street.co.uk`.
9. Add `fitness-street.co.uk` too if the root domain should work.
10. Set the preferred redirect, usually root domain to `www`.

Pros:

- Cloudflare Pages can host this site for free.
- The site becomes faster and easier to maintain.
- GitHub deployments can be automatic.

Cons:

- DNS must be handled carefully.
- Email records must not be lost.
- Wix may still charge for domain registration unless the domain is transferred away later.

## Option B: Transfer The Domain Registration Away From Wix

This is a bigger move.

What happens:

- The domain registration is moved from Wix to another registrar.
- Cloudflare can be used for DNS and hosting.
- Wix is no longer involved with the website or the domain.

Steps at a high level:

1. Unlock the domain in Wix.
2. Get the transfer authorisation code from Wix.
3. Start the transfer with the new registrar.
4. Approve the transfer.
5. Recreate or confirm all DNS records in Cloudflare.
6. Connect Cloudflare Pages to the domain.

Pros:

- Cleaner long-term setup.
- Less dependence on Wix.

Cons:

- More admin.
- Domain transfers can take several days.
- Mistakes can affect email or website availability.

## Email Warning

The main risk is not the website. The website is simple.

The main risk is email. If the domain uses Microsoft 365, the DNS records must include Microsoft records such as MX, SPF, DKIM, DMARC, and verification records.

Before switching nameservers, take screenshots or export the current DNS records from Wix.

## Recommended Approach

For a small business handover, the safest route is:

1. Publish the site to Cloudflare Pages first using the temporary `.pages.dev` URL.
2. Confirm the site works.
3. Add the domain to Cloudflare.
4. Copy/check all existing DNS records.
5. Change nameservers at Wix.
6. Add the custom domain to Cloudflare Pages.
7. Test the website and email.

This avoids doing the website build, hosting setup, and domain move all at once.

## Useful References

- Cloudflare Pages custom domains: `https://developers.cloudflare.com/pages/configuration/custom-domains/`
- Cloudflare nameserver changes: `https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/`
- Wix domain transfer guidance: `https://support.wix.com/`
