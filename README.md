# Link-hub site

One page that links every product, hosted free on GitHub Pages. It does two jobs:

1. A single link for the Pinterest profile, Reddit profile, and anywhere else that allows one link.
2. **Hosting for the pin images**, which is what makes Pinterest's bulk upload possible: `pins-bulk-upload.csv` points at `https://fairdraftstudio.github.io/pins/<key>.png`.

## Contents
- `index.html` — the page. No build step, no external JS, works in light and dark.
- `pins/` — the 24 pin PNGs, copied from `../01-pinterest/out/`.

Re-copy the pins after re-rendering them:
```bash
cd repos/fairdraftstudio.github.io && cp ../../marketing/01-pinterest/out/*.png pins/
```

## Deploying (needs GitHub access, which is blocked until the Google appeal succeeds)

GitHub Pages serves a repo named `<username>.github.io` at that address, from the root of the default branch.

```bash
cd repos/fairdraftstudio.github.io
git init -b main
git add .
git commit -m "Fairdraft Studio link hub"
gh repo create FairdraftStudio/fairdraftstudio.github.io --public --source=. --push
```

Then in the repo: Settings → Pages → Source "Deploy from a branch", branch `main`, folder `/ (root)`. The site appears at **https://fairdraftstudio.github.io** within a few minutes.

Commits need the no-reply identity, since no git identity is set on this machine:
```bash
git -c user.name=FairdraftStudio -c user.email=327933373+FairdraftStudio@users.noreply.github.com commit -m "..."
```

## After it is live
1. Set it as the website on the Pinterest profile, and claim it there (Settings → Claimed accounts) so pins show your brand.
2. Add it to the GitHub profile, the Gumroad profile, and the Reddit profile.
3. The Pinterest bulk CSV then works as-is.

## Keep it honest
Update the page whenever something changes state:
- Social Media Manager Kit: currently "Coming soon", swap in the real Etsy and Gumroad links once listed.
- Client Onboarding Checklist: currently "Coming soon", link it once the free Gumroad product is published.
- Add a bundle card when the bundle goes live.
