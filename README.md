# Tab Six Studios Site

Small static studio site for **Tab Six Studios** and **Piecebreaker**.

The goal is credibility, clarity, and low maintenance while Piecebreaker is in
active development. This is intentionally a narrow, professional placeholder
site with a "coming soon" posture rather than a large marketing site.

## Stack

- Plain HTML and CSS
- No framework
- No build step
- GitHub Pages deployment from the repository root on `main`
- Canonical domain: `https://www.tabsix.studio`

## File Layout

```text
/
├── index.html
├── 404.html
├── styles.css
├── robots.txt
├── sitemap.xml
├── CNAME
├── README.md
├── .gitignore
└── assets/
    ├── fonts/
    ├── icons/
    └── images/
```

## What The Site Is For

- Provide a real, public-facing studio presence for Tab Six Studios
- Confirm that Piecebreaker is a real game in development
- Give artists, contractors, collaborators, and other professional contacts a
  clean place to verify the studio and reach out
- Stay simple enough that the site does not go stale quickly

## Editing Text

- Main site copy lives in `index.html`
- Global visual styles live in `styles.css`
- The most likely sections to update later are:
  - hero text
  - studio paragraph
  - Piecebreaker summary and status card
  - contact details

Recommended workflow:

1. Edit `index.html`
2. Preview locally
3. Commit and push to `main`

## Updating Media

The live site now avoids gameplay screenshots and image-led backgrounds.

Current live media files:

- `assets/images/og-piecebreaker-site.png`

Exploratory image assets from earlier passes still remain in `assets/images/`,
but they are not referenced by the live page.

When replacing media later:

1. Only add imagery when it genuinely improves the page
2. Prefer a small number of strong, intentional assets over a larger gallery
3. Keep the live page readable and current rather than turning it into a half-finished pitch
4. Update `index.html`, `404.html`, and any OG references if filenames change

## Icons And Social Preview

- Favicon source is the current app icon from the game repo
- Open Graph image is `assets/images/og-piecebreaker-site.png`

If you replace the app icon or want a different social card, regenerate those
assets and keep the same filenames.

## Local Preview

From this repository:

```bash
python3 -m http.server 4173
```

Then open:

- `http://localhost:4173/`

## Deployment

This site is meant to deploy directly from GitHub Pages.

Preferred configuration:

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/ (root)`

Deployment is automatic after pushing changes to `main`.

## GitHub Pages Configuration

Repository:

- `elehrer123-arch/tabsix-studio-site`

Required GitHub Pages settings:

- GitHub Pages enabled
- Source set to `main` / root
- Custom domain set to `www.tabsix.studio`
- HTTPS enforced once DNS resolves correctly

The checked-in `CNAME` file should contain:

```text
www.tabsix.studio
```

## Canonical Domain

Canonical host:

- `https://www.tabsix.studio`

Alias host:

- `https://tabsix.studio`

Reason:

- `www` is the cleaner long-term GitHub Pages setup
- GitHub Pages handles the custom domain path more predictably with `www`
- The apex domain can point at GitHub Pages and redirect to the canonical `www`
  host

## Squarespace DNS Records

In Squarespace DNS, create these records:

| Type | Host | Value |
| --- | --- | --- |
| `CNAME` | `www` | `elehrer123-arch.github.io` |
| `A` | `@` | `185.199.108.153` |
| `A` | `@` | `185.199.109.153` |
| `A` | `@` | `185.199.110.153` |
| `A` | `@` | `185.199.111.153` |
| `AAAA` | `@` | `2606:50c0:8000::153` |
| `AAAA` | `@` | `2606:50c0:8001::153` |
| `AAAA` | `@` | `2606:50c0:8002::153` |
| `AAAA` | `@` | `2606:50c0:8003::153` |

Notes:

- Do not use wildcard DNS records for this setup
- After DNS propagates, GitHub Pages should serve `www.tabsix.studio`
- The apex `tabsix.studio` should resolve and then redirect to `www`

## Design Rationale

- The site uses a dark, restrained palette derived from the current game UI so
  it feels specific to Piecebreaker instead of generic studio boilerplate
- Large typography and generous spacing make the studio feel deliberate and
  professional without sounding inflated
- The page is now intentionally text-led so it can feel polished without
  leaning on half-ready promotional art
- The current tone is "coming soon" rather than a hard game pitch, which makes
  the site more honest at this stage of development
- The hero uses abstract CSS atmosphere instead of screenshot backgrounds, which
  keeps the site cleaner and more durable while public materials are still sparse
- The structure stays small so future upkeep is easy and stale sections do not
  accumulate

## Asset Selection Notes

- The favicon and brand mark come from the current game app icon
- Headline typography uses the local `Cinzel` and `Crimson Pro` fonts already
  present in the game repo
- The live Open Graph card is now a text-only social image so external previews
  match the quieter direction of the site
- Earlier exploratory hero and gameplay composites remain in `assets/images/`
  for possible future use, but they are no longer part of the live page
- Outdated Steam storefront assets and anything with the old project branding
  were intentionally not used verbatim

## Intentional Omissions

The site deliberately leaves out:

- fake press quotes
- fake awards
- unsupported release timing on the homepage
- team-size or funding claims
- dead social links
- blog or news sections
- platform claims not required for this placeholder

## Remaining Manual Steps

If GitHub Pages and DNS are not already configured in the account, finish these:

1. Push the final site to `main`
2. Enable GitHub Pages on the repository root
3. Set the custom domain to `www.tabsix.studio`
4. Add the DNS records above in Squarespace
5. Wait for DNS propagation
6. Turn on `Enforce HTTPS` in GitHub Pages once the certificate is ready
