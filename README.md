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

## Making further changes
Ask for changes here and pushes will land in this repo — pull the latest theme
version in Shopify Admin to preview/publish after each push.
