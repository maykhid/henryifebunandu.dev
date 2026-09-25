# Henry Ifebunandu: portfolio site

This is a static site (plain HTML/CSS/JS in one file) built around one line: *I build Flutter apps that stay calm when the signal doesn't.*

## Files

- `index.html` is the whole site. Its `<head>` holds the SEO description, the Open Graph tags for link previews, and a JSON-LD `Person` record with your real profile links.
- `favicon.svg` is a placeholder "HI" icon.
- `img/` holds the FunZ screens (home, FunZ Business, and the two Scan-to-Pay screens). The customer name and account number on the home screen are blurred. `henry.webp` is your portrait, cropped to 4:5 with photo metadata removed. `ladder-*.webp` are screenshots from Ladder's public App Store listing.

## Before you publish

All the "To fill in" boxes are done. What's left:

| What | Notes |
|---|---|
| CV link | Add your CV as `henry-ifebunandu-cv.pdf` next to `index.html`, then uncomment the CV link in the contact section (search for `CV: add when ready`). |
| Ladder rewrite: trade-offs | Removed for now. When you know why you rewrote instead of refactoring, add a Trade-offs box back. |
| Ladder rating numbers | The outcome says the store rating went up. A before/after figure (e.g. 3.9 to 4.5) would make it much stronger. |
| Ladder listing stats | The Ladder outcome quotes the listing's "27K+ active users, $2M+ saved." Check these are still what the listing says before you publish. |
| FX volume | Add cross-border purchase counts once the rollout settles. |

`og-image.png` (1200×630) is the picture that shows when your link is shared. Your domain, henryifebunandu.dev, is already set in the canonical link, the Open Graph tags and the JSON-LD.

Also check:
- **Confidentiality.** The FunZ and Scan-to-Pay case studies use real app screens, and the Scan-to-Pay text names the OpenRouter model pipeline. Get FunZ's OK on both before the site goes live. Ladder visuals come from its public App Store listing and are labelled that way; only the FX flow is an illustrative mockup.
- **Your own account details.** The Scan-to-Pay screens show your name, Zenith account number and handwriting. That's your call, but blur the middle digits if you'd rather not publish them.
- **Ladder.** The Ladder studies describe internal details (FX layer, typed error codes, feature flags, analytics vendors). Get Ladder's OK, and never publish code, `env*.json` files or the Kochava trace logs from the repo.
- **GitHub.** Visitors will click github.com/maykhid. Pin `liveness_flutter` and refresh the other pinned repos.
- **liveness_flutter, quick wins.** It scores 150/160 because the `google_mlkit_face_detection: ^0.14.0` constraint doesn't allow 0.15.x. Bump it to reach 160/160. A verified publisher (via henryifebunandu.dev) would also replace "Unverified uploader" on pub.dev. The page shows pub points, not likes or downloads, which are still low.
- **What I left out on purpose:** the unverified figures (NGN 1.6B volume, 40% cold start, 30% repayment reliability, 50% payroll automation), any testing or TDD claims, skill bars, and your phone number. Only add a number back once you can back it up.

## The hero demo

The phone in the hero is a small HTML wallet. It shows your thesis in action:
- **Drop the network**: the live connection indicator falls back to exponential backoff (1s, 2s, 4s, 8s, 16s), and the last-synced balance stays on screen.
- **Fund wallet**: shows Mobile Money verification by polling. If the connection drops mid-payment, it offers a manual **Retry check**.
- **₦80,000**: gets blocked before the payment starts, because it's over the Tier 1 KYC limit.

To replace it with a real Flutter build:

```bash
flutter build web --release --base-href /demos/wallet/
cp -r build/web/ ../henry-portfolio/demos/wallet/
```

Then find the `LIVE DEMO SLOT` comment and swap the `.screen` contents for the `<iframe>` shown there. Keep the HTML version as the default, and load the Flutter build when someone taps it, so the first page load stays fast.

## Deploy (free)

Use **Cloudflare Pages**, **Netlify**, **Vercel** or **GitHub Pages**: drag and drop the folder, or connect a repo. Add your domain, then submit it in Google Search Console.

## Next step

Once the gaps above are filled, give each case study its own page (for example `/work/ladder-v2/`) with its own `<title>` and description. Separate pages rank much better in search than one long page.
