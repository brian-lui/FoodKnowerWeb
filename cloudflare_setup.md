# Cloudflare + GitHub Pages Setup (foodknower.com)

## Assumptions
- DNS is managed at Namecheap.
- GitHub Pages is already serving the site and a `CNAME` file exists in the repo.
- `www.foodknower.com` currently redirects to `foodknower.com` and that behavior is acceptable.
- No email services or other DNS records need to be preserved.
- We will use Cloudflare **Proxy ON** (orange cloud).

If any of these are wrong, update them before proceeding.

## Proxy Mode: Pros and Cons (Chosen: Proxy ON)

### Cloudflare Proxy ON (orange cloud)
Pros:
- CDN caching and edge performance improvements.
- Security features (WAF, bot mitigation, DDoS protection).
- Better TLS controls and HTTP/2/3.
- More flexible redirect and caching rules.

Cons:
- More moving parts; debugging can be harder.
- Potential caching issues after deploys unless configured.
- Must keep SSL mode correct (usually “Full”).

### DNS-Only (gray cloud)
Pros:
- Simpler; Cloudflare only manages DNS.
- No cache issues or proxy-related debugging.
- GitHub Pages SSL behavior stays standard.

Cons:
- No Cloudflare CDN/security benefits.
- Less control over TLS and traffic behavior.

Decision: Use **Proxy ON**.

## Steps

1. **Collect current DNS records**
   - In Namecheap, export or screenshot all existing records for `foodknower.com`.
   - This preserves any records you might need later.

2. **Add site to Cloudflare**
   - Create or log into a Cloudflare account.
   - Add `foodknower.com`.
   - Choose the Free plan.

3. **Verify DNS records in Cloudflare**
   - Cloudflare will import records from Namecheap.
   - Ensure these are present (or add them):
     - `A` or `CNAME` for apex `foodknower.com` pointing to GitHub Pages.
     - `CNAME` for `www` pointing to your GitHub Pages domain or apex.
   - You can set `www` to redirect to apex later via Cloudflare.

4. **Update Namecheap nameservers**
   - Replace Namecheap nameservers with the Cloudflare-provided nameservers.
   - Wait for propagation (typically minutes to hours).

5. **Configure SSL/TLS**
   - In Cloudflare, set SSL/TLS mode to **Full**.
   - Enable “Always Use HTTPS”.

6. **Set proxy mode**
   - For `foodknower.com` and `www` records, set **Proxy ON** (orange cloud).

7. **Redirect www to apex**
   - If you want `www` to always go to apex:
     - Use Cloudflare Redirect Rules or Page Rules to 301 `www.foodknower.com/*` -> `https://foodknower.com/$1`.

8. **Verify GitHub Pages settings**
   - In GitHub Pages settings, ensure the custom domain is `foodknower.com`.
   - Keep the `CNAME` file committed in the repo.

9. **Test**
   - Confirm `foodknower.com` and `www.foodknower.com` both resolve.
   - Check that HTTPS works and the certificate is valid.
   - Verify content updates after a deploy (may require cache purge).

## Optional: Cache Settings
- If you update frequently, consider a Cache Rule to bypass cache for HTML.
- Use “Purge Everything” after a deploy if you see stale content.

## Rollback Plan
- If anything breaks, switch Cloudflare proxy to DNS-only.
- If still broken, revert Namecheap nameservers to the previous ones.
