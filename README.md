# Waldo Legal Site

A small static site that hosts Waldo's Privacy Policy, Terms of Service, and
Support page. These pages provide the public URLs that Apple requires for
TestFlight External Testing and App Store submission.

## Pages

- `index.html` — landing page
- `privacy.html` — Privacy Policy (required by Apple)
- `terms.html` — Terms of Service
- `support.html` — Support / contact (used as Marketing URL or Support URL)

## Deploying to GitHub Pages

You have two clean options. Pick the one that matches your repo setup.

### Option A — Dedicated repo (recommended)

This keeps the legal site cleanly separated from the app source.

1. Create a new public repo named `waldo-legal` on GitHub under the same
   account (e.g. `kirbmart/waldo-legal`).
2. Copy the contents of this `legal/` folder into the new repo.

   ```bash
   cd /tmp
   git clone https://github.com/kirbmart/waldo-legal.git
   cp -R /Users/bradleybecker/waldo/legal/. waldo-legal/
   cd waldo-legal
   git add . && git commit -m "Initial legal site"
   git push origin main
   ```

3. In GitHub: **Settings → Pages → Source: `main` / `/ (root)`**.
4. After ~1 minute, your URLs will be:

   - Privacy: `https://kirbmart.github.io/waldo-legal/privacy.html`
   - Terms:   `https://kirbmart.github.io/waldo-legal/terms.html`
   - Support: `https://kirbmart.github.io/waldo-legal/support.html`

### Option B — `gh-pages` branch on the app repo

If you don't want a separate repo, push this folder as the root of a
`gh-pages` branch in the existing `oioi` repo.

```bash
cd /Users/bradleybecker/waldo
git checkout --orphan gh-pages
git rm -rf .
cp -R legal/. .
git add .
git commit -m "Legal site for TestFlight external testing"
git push origin gh-pages
git checkout -    # back to your previous branch
```

Then in GitHub: **Settings → Pages → Source: `gh-pages` / `/ (root)`**.

URLs:
- `https://kirbmart.github.io/oioi/privacy.html`
- `https://kirbmart.github.io/oioi/terms.html`
- `https://kirbmart.github.io/oioi/support.html`

## Customizing

Update the contact email (`brady@goodlunch.com`) in `privacy.html`,
`terms.html`, and `support.html` if you'd prefer a different address.
