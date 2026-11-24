# VitalCocoa Shopify Theme - Build Guide

**Store:** sjwjsx-uv.myshopify.com  
**Development Theme ID:** 190635049205  
**Repository:** samuelmoussa04-byte/VitalCocoa

This is a launch-ready Shopify Online Store 2.0 theme for VitalCocoa, a high-flavanol cocoa drink. The theme is based on MyNRG's proven structure with VitalCocoa's compliance and marketing requirements.

## 🚀 Quick Start

### Prerequisites
- Shopify CLI installed (`npm install -g @shopify/cli`)
- Authenticated with Shopify account

### Start Development
```bash
cd /Users/samuelmoussa/Desktop/vitalcocoa
shopify theme dev
```

This will watch for changes and sync to your dev theme in real-time.

### Preview
- **Store preview:** https://sjwjsx-uv.myshopify.com?preview_theme_id=190635049205
- **Theme editor:** https://sjwjsx-uv.myshopify.com/admin/themes/190635049205/editor

### Check for Errors
```bash
shopify theme check
```

## 📋 Setup Instructions

See **FULL SETUP CHECKLIST** below for detailed steps on:
1. Creating product variants and bundles
2. Setting up subscriptions
3. Creating custom pages
4. Creating batch metaobjects
5. Configuring theme settings

## 📁 Theme Structure

- **`config/`** - Settings schema and default values
- **`layout/`** - Main theme layout and password page
- **`sections/`** - All customizable sections
- **`snippets/`** - Reusable components
- **`templates/`** - Page templates (home, product, collection, etc.)
- **`assets/`** - CSS, JS, images
- **`locales/`** - Translation strings
- **`refrence/`** - Design reference (not uploaded to Shopify)

---

# 📋 FULL SETUP CHECKLIST

## 1. Product Setup in Shopify Admin

### Create the main product:
- **Title:** VitalCocoa High-Flavanol Cocoa
- **Description:** Use the HTML from the product page template
- **Images:**
  - Image 1: Product tub
  - Image 2: Nutrition/Supplement Facts panel
  - Image 3: Sample lab report (COA)

### Create product variants for bundles:
1. **Quantity 1**
   - Option: Quantity: 1
   - Price: ${{ PRICE_1 }} (from supplier)
   
2. **Quantity 3** (pre-selected)
   - Option: Quantity: 3
   - Price: ${{ PRICE_3 }}
   
3. **Quantity 6**
   - Option: Quantity: 6
   - Price: ${{ PRICE_6 }}

## 2. Enable Subscriptions (Shopify Native)

1. Apps > Subscriptions
2. Create a selling plan:
   - Name: Subscribe & Save
   - Discount: {{ SUB_DISCOUNT }}% (default 10%)
   - Frequency: Monthly

## 3. Create Custom Pages

Create these in Shopify Admin → Pages:

| Page | URL | Template |
|------|-----|----------|
| Track Your Order | `/pages/track-your-order` | Default |
| The Science | `/pages/science` | `page.science.json` |
| Batch Results | `/pages/batch-results` | `page.batch-results.json` |
| FAQ | `/pages/faq` | `page.faq.json` |
| About | `/pages/about` | `page.about.json` |
| Advertorial | `/pages/advertorial` | `page.advertorial.json` |
| Contact Us | `/pages/contact-1` | `page.contact.json` |
| Order Cancellation | `/pages/order-cancellation` | Default |
| Subscription Policy | `/pages/subscription-policy` | Default |

## 4. Create Metaobjects for Batch Tracking

**In Shopify Admin:**
Settings → Data Model → Metaobjects → Create definition

**Name:** Batch Result  
**API ID:** `batch_result`

**Fields:**
- `batch_number` - Single line text (required)
- `production_date` - Date
- `flavanols_mg_per_serving` - Number
- `epicatechin_mg_per_serving` - Number (optional)
- `lead_mcg_per_serving` - Number
- `cadmium_mcg_per_serving` - Number
- `caffeine_mg_per_serving` - Number
- `lab_name` - Single line text
- `test_date` - Date
- `coa_file` - File reference (PDF)

## 5. Set Up Navigation Menus

**Main Menu (header):**
1. Shop → `/products/vitalcocoa-high-flavanol-cocoa`
2. The Science → `/pages/science`
3. Batch Results → `/pages/batch-results`
4. FAQ → `/pages/faq`

**Customer Account Menu:** Use default "customer-account-main-menu"

## 6. Configure Theme Settings

**In Shopify Admin → Customize theme:**

### Colors:
- Accent: `#7A3E26`
- Accent Deep: `#45271D`
- Text: `#2B1A14`
- Text Muted: `#6E5A4C`
- Page Background: `#F7F1E8`
- Surface: `#FFFCF7`
- Savings/Gold: `#C2A15A`

### Product Info (from supplier):
- Flavanols per serving: `500` mg
- Caffeine per serving: `12` mg
- Servings per tub: `30`

### Pricing (from supplier):
- Price 1 tub: $0.00
- Price 3 tubs: $0.00
- Price 6 tubs: $0.00

### Shipping & Returns:
- Free shipping threshold: $150
- Guarantee days: 60
- Guarantee text: (default provided)

### Subscriptions:
- Subscribe & save discount: 10%

## Deployment

Your theme is currently in **development mode**. To make it live:

```bash
shopify theme publish
```

---

## 🎨 Features Inherited from MyNRG

✅ Customer login with account dashboard  
✅ US/CA currency switching  
✅ Cart drawer (slide-out)  
✅ Mobile hamburger menu  
✅ Sticky header on scroll  
✅ Order tracking and subscription pages  
✅ Legal pages (Privacy, Terms, Refund, Shipping)  
✅ Email capture / newsletter  

---

## 🎯 VitalCocoa-Specific Features

✅ Batch lookup (metaobjects)  
✅ Flavanol comparison chart  
✅ Compliance footer with FDA disclaimer  
✅ Subscription selling plans  
✅ Bundle tier pricing (1/3/6 tubs)  
✅ Proof-driven messaging  

---

## 📝 Still to Build

The following sections need to be created following Claude's prompt:

**Sections:**
- hero, trust-strip, problem-dutching, verified-not-inflated, batch-lookup, how-it-works-steps, ritual-gallery, comparison-table, guarantee, faq-accordion, reviews-app-slot, email-capture, main-product, product-details-accordions, sticky-atc, cart-drawer, main-cart, advertorial-body, rich-text, image-with-text, main-page, main-404, main-search, main-collection, main-blog, main-article

**Snippets:**
- price, icon, badge-seal, fda-footnote, cart-line-item, free-shipping-bar, json-ld-product, json-ld-organization, responsive-image, batch-card

**Assets:**
- theme.css (extend from MyNRG)
- theme.js (vanilla JS for interactions)

---

## 🔗 Important Links

- **Shopify Admin:** https://admin.shopify.com/store/t0fzsp-sa
- **Dev Theme:** https://sjwjsx-uv.myshopify.com?preview_theme_id=190635049205
- **GitHub:** https://github.com/samuelmoussa04-byte/VitalCocoa
- **MyNRG Reference:** https://github.com/samuelmoussa04-byte/myNRG

---

**Last updated:** November 23, 2026  
**Version:** 0.1 (Foundation)
