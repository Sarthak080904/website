# Urban Threads — Shopify Theme

This theme is built on top of Shopify's open-source **Dawn** base, customized for a
print-on-demand / dropshipping store selling apparel, accessories, and customizable
print products.

## What's already done
- Theme renamed and rebranded (placeholder name: "Urban Threads" — change any time)
- Homepage rebuilt with:
  - Hero banner ("Wear it. Print it. Make it yours.")
  - **Shop by Category** grid (6 slots — see setup step 2)
  - Best sellers grid
  - "Why shop with us" trust badges (made to order, customizable, pan-India shipping)

## Setup steps (do these in Shopify Admin, not in code)

### 1. Connect this repo to your Shopify theme
In Shopify Admin → **Online Store → Themes → Add theme → Connect from GitHub**,
select this repository (`Sarthak080904/website`) and branch `main`. Every push here
will then sync as a new theme version you can preview and publish.

### 2. Create your collections
Based on the category screenshots you shared, create these collections in
**Products → Collections** (name them exactly, so linking is easy):
- T-Shirts & Apparel (regular, oversized, boxy, acid wash, polos, hoodies, sweatshirts)
- Bottomwear (sweatpants, shorts)
- Customized / AOP Apparel
- Accessories & Headwear
- Bags & Drinkware
- Print & Marketing Materials (business cards, banners, flyers, stickers, etc.)
- Home Decor & Pet-Wear
- Kids Clothing

Then in **Online Store → Customize → Shop by Category** section, assign each of
the 6 grid blocks to a collection.

### 3. Create the navigation menu
**Online Store → Navigation → Main menu** — add links matching the collections
above. This isn't stored in theme code; it's a live Shopify setting.

### 4. Create the "Custom Orders" page
The hero button links to `pages/custom-orders`. Create this page under
**Online Store → Pages** to explain your customization process (upload art,
choose product, etc.), or update/remove the button in the theme customizer.

### 5. Products & suppliers
You mentioned sourcing from PrintOnDemandIndia, Qikink, YouPrint, and Blinkstore.
None of these currently have official Shopify app integrations — you'll need to
either:
- Import products via CSV (**Products → Import**) and fulfill orders manually
  by placing them with each supplier, or
- Check if any of them offer a Shopify API/app in your account dashboard
  (worth asking their support directly)

This theme doesn't handle supplier integration — that's a backend/ops decision,
not a theme change.

## Product templates
Three alternate product templates are included — assign them per-product in
Shopify Admin under **Product → Theme template** (right-hand sidebar):

| Template | Use for | Key features |
|---|---|---|
| `product.apparel.json` | Regular T-shirts, hoodies, sweatshirts, etc. | Size/color swatches, size guide popup, fabric & fit tab |
| `product.customizable.json` | AOP apparel, custom-print clothing | Required design upload, print/proofing info tab |
| `product.print.json` | Business cards, banners, flyers, etc. | Required artwork upload, quantity-tier variants, paper specs tab |
| *(default)* `product.json` | Anything else (accessories, drinkware, bags) | Standard Dawn layout |

For the size guide popup on the apparel template, create a "Size Guide" page
under **Online Store → Pages** and link it in the theme customizer (the block
is already added, just needs a page selected).

## Product import (CSV)
`product-import-templates/` has two starter CSVs matching your category
structure — edit them with your real SKUs, prices, and image URLs, then import
via **Products → Import** in Shopify Admin:
- `apparel-with-variants.csv` — Size + Color variant structure (T-shirts, hoodies)
- `print-products.csv` — Quantity-tier variant structure (business cards, flyers)

After import, remember to manually set each product's **Theme template** to
match (apparel vs. customizable vs. print) — CSV import doesn't carry that over.

## Custom design upload (new)
Products can now accept a customer-uploaded design file (for AOP apparel, custom
prints, etc.) with zero apps required:

1. Go to **Online Store → Customize**, open any product page
2. In the product template, click **Add block → Custom design upload**
3. Configure the field label, help text, whether a file is required, and
   whether to show a "special instructions" notes box
4. Save

The uploaded file becomes a line-item property, visible as a clickable link
to you (the merchant) on the order page, in the cart, and at checkout.

**Important:** file uploads only work with a **page-style cart** (not a drawer
or popup) — this theme is already configured for that
(`cart_type: page` in `config/settings_data.json`). If this ever gets changed
in the theme editor's cart settings, uploads will silently stop reaching orders.

Also note: Shopify does not enforce file size/type limits beyond the browser's
`accept` attribute set on the input (currently JPG/PNG/PDF) — a user could
still bypass this client-side restriction, so don't rely on it for strict
validation of what customers send you.

## Making further changes
Ask for changes here and pushes will land in this repo — pull the latest theme
version in Shopify Admin to preview/publish after each push.
