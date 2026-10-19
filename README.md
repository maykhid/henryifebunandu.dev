# henryifebunandu.dev

Source for [henryifebunandu.dev](https://henryifebunandu.dev), the portfolio of Henry Ifebunandu, a senior mobile engineer in Lagos who builds Flutter apps for finance in Nigeria and Ghana.

## What's here

- **`index.html`**: the whole site in one file, with HTML, CSS and JavaScript inline and no framework or build step. The `<head>` carries the SEO description, Open Graph tags for link previews and a JSON-LD `Person` record.
- **`img/`**: WebP images (app screenshots and a portrait), compressed and stripped of metadata.
- **`og-image.png`**: the 1200×630 preview image shown when the link is shared.
- **`CNAME`**, **`robots.txt`** and **`sitemap.xml`**: the custom domain and search-engine basics.

## The interactive demo

The phone in the hero is a small, fictional finance app written in plain JavaScript. Every name, account and amount in it is made up, and no real money moves. Each flow is a pocket version of a feature from the case studies:

- **Send**: a transfer over the account's limit is stopped before it starts.
- **Scan to pay**: bank details are read from a handwritten slip and filled in for you.
- **Buy IPO**: naira-priced units paid in cedis at a locked rate, and the user re-confirms if the quote expires.
- **Business**: business transfers wait for a second signatory, and whoever starts a payment can't approve it.

## Running it locally

There is nothing to install. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## Hosting and analytics

The site is hosted on GitHub Pages under a custom domain. Analytics run on [Umami](https://umami.is), which is cookieless, so there's no consent banner, and it only counts visits on the live domain.

## Usage

The code is here to read and learn from. The writing, the portrait and the app screenshots aren't for reuse: the Ladder and FunZ screenshots belong to their respective companies.
