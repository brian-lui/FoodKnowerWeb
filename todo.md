# FoodKnower Website — TODO

## Assets Needed
- [x] Add `images/icon.png` (app logo)
- [ ] Replace phone mockup placeholders with real screenshots (scan in action, score results, nutrition breakdown, scan history, share card)

## Links to Update
- [ ] Update Play Store link once published (currently `#` with "Coming Soon" badge)

## GitHub Pages Setup
- [ ] Go to repo on GitHub → Settings → Pages
- [ ] Under "Source", select **Deploy from a branch**
- [ ] Set branch to `main` and folder to `/ (root)`, click Save
- [ ] Wait a few minutes — site will be live at `https://<username>.github.io/FoodKnowerWeb/`

## Custom Domain (foodknower.com)
- [ ] In GitHub repo → Settings → Pages → Custom domain, enter `foodknower.com` and save
- [ ] Go to your domain registrar (where you bought foodknower.com)
- [ ] Add DNS records pointing to GitHub Pages:
  - A records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
  - CNAME record: `www` → `<username>.github.io`
- [ ] Wait for DNS to propagate (can take up to 24–48 hours)
- [ ] Back in GitHub Pages settings, check **Enforce HTTPS** once it becomes available
- [ ] Verify site loads at `https://foodknower.com`

## Optional / Future
- [ ] Add Founder's Message section to landing page
- [ ] Add EXIF/metadata stripping confirmation to privacy policy security section
- [x] Add favicon
