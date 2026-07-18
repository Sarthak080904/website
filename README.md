# Urban Threads - Shopify Theme

This is a Shopify theme for a print-on-demand / dropshipping store selling apparel,
accessories, gifts, custom products, and print materials. It is built on Shopify's
Dawn base and customized for a modern, design-led storefront.

## What Is Built

- Modern homepage with:
  - Animated POD hero.
  - Original generated product mockup image.
  - Product universe/category section.
  - Featured products grid with quick add enabled.
  - Fulfillment process explanation.
  - Trust badges.
  - FAQ.
  - Newsletter capture.
- Reusable custom sections:
  - `pod-showcase`
  - `pod-product-universe`
  - `pod-process`
  - `pod-faq`
  - `pod-page-hero`
- Complete page templates:
  - `page.custom-orders.json`
  - `page.artwork-guide.json`
  - `page.shipping-returns.json`
  - `page.about.json`
  - `page.faq.json`
  - `page.size-guide.json`
- Product templates:
  - `product.apparel.json`
  - `product.customizable.json`
  - `product.print.json`
  - default `product.json`
- Product upload support for eligible custom products.
- Page-style cart preserved so custom upload line-item properties work.
- Starter product CSV templates in `product-import-templates/`.

## Shopify Admin Setup

Theme code cannot create Shopify products, collections, menus, or page records by
itself. Create these in Shopify Admin after the theme is connected.

### 1. Connect The Repository

In Shopify Admin > **Online Store > Themes > Add theme > Connect from GitHub**,
select `Sarthak080904/website` and the branch you want to preview or publish.

### 2. Create Collections

Recommended collections:

- T-Shirts & Apparel
- Bottomwear
- Customized / AOP Apparel
- Accessories & Headwear
- Bags & Drinkware
- Print & Marketing Materials
- Home Decor & Pet-Wear
- Kids Clothing

Then update homepage links in **Online Store > Customize**.

### 3. Create Pages

Create these pages under **Online Store > Pages** and assign the matching theme
template:

| Page title | Handle | Theme template |
|---|---|---|
| Custom Orders | `custom-orders` | `page.custom-orders` |
| Artwork Guide | `artwork-guide` | `page.artwork-guide` |
| Shipping & Returns | `shipping-returns` | `page.shipping-returns` |
| About | `about` | `page.about` |
| FAQ | `faq` | `page.faq` |
| Size Guide | `size-guide` | `page.size-guide` |
| Contact | `contact` | `page.contact` |

### 4. Create Menus

Recommended main menu:

- Shop
- Custom Orders
- Artwork Guide
- Shipping & Returns
- FAQ
- Contact

Recommended footer menu:

- About
- Size Guide
- Shipping & Returns
- FAQ
- Contact

### 5. Add Products

Use the starter CSV files in `product-import-templates/`, or add products manually.
After import, assign the correct product template:

| Template | Use for |
|---|---|
| `product.apparel` | T-shirts, hoodies, sweatshirts, polos |
| `product.customizable` | Products needing customer design upload |
| `product.print` | Business cards, flyers, stickers, banners |
| default `product` | Accessories, drinkware, bags, standard items |

### 6. Choose Fulfillment Model

Best path:

- Use a supplier with a Shopify app if available.
- If no app exists, start manually by placing paid orders with the supplier.
- Move to CSV/API automation after sales volume proves the catalog.

Before launch, order samples and confirm:

- Print quality.
- Size accuracy.
- Production time.
- Shipping time.
- Replacement rules.
- Tracking behavior.

## Important Upload Note

Custom design uploads use Shopify line-item properties. File uploads require a
page-style cart, not a drawer cart. This theme is already configured with
`cart_type: page` in `config/settings_data.json`.

## Launch Checklist

- Add real logo and favicon.
- Replace starter policy text with final legal/business wording.
- Add real supplier timelines.
- Import real products and images.
- Assign product templates.
- Create all pages and navigation menus.
- Test custom upload from product page to cart to checkout.
- Place one real sample order before publishing publicly.
