# VitalCocoa Theme - Setup Status

**Date:** November 23, 2026  
**Status:** Foundation Complete ✅  
**Next Phase:** Section & Snippet Development

---

## ✅ Completed

### Infrastructure & Configuration
- ✅ Connected to Shopify store (`sjwjsx-uv.myshopify.com`)
- ✅ Development theme created (ID: 190635049205)
- ✅ GitHub repository set up (`samuelmoussa04-byte/VitalCocoa`)
- ✅ Shopify CLI configured
- ✅ `.shopifyignore`, `shopify.app.toml`, `.theme-id.json` created

### Core Files
- ✅ `layout/theme.liquid` - Main layout with header/footer integration
- ✅ `layout/password.liquid` - Coming soon page
- ✅ `config/settings_schema.json` - 30+ configurable settings
- ✅ `config/settings_data.json` - Default values and placeholders
- ✅ `locales/en.default.json` - Localization strings
- ✅ `sections/header.liquid` - Header with customer login & currency switching
- ✅ `sections/footer.liquid` - Footer with all navigation (Support, Learn, Legal, Shop)
- ✅ `sections/announcement-bar.liquid` - Rotating announcements
- ✅ `sections/header-group.json` - Announcement + header
- ✅ `sections/footer-group.json` - Footer group

### Templates (All Created)
- ✅ `templates/index.json` - Home page (sections scaffolded)
- ✅ `templates/product.json` - Product page
- ✅ `templates/page.science.json` - The Science page
- ✅ `templates/page.batch-results.json` - Batch lookup page
- ✅ `templates/page.faq.json` - FAQ page
- ✅ `templates/page.about.json` - About page
- ✅ `templates/page.contact.json` - Contact page
- ✅ `templates/page.advertorial.json` - Advertorial landing page
- ✅ `templates/404.json`, `article.json`, `blog.json`, `cart.json`, `collection.json`, `list-collections.json`, `page.json`, `password.json`, `search.json`
- ✅ `templates/gift_card.liquid` - Gift card

### Design Assets
- ✅ Copied `assets/theme.css` from MyNRG (foundation for theming)
- ✅ Color tokens defined in settings schema (browns, golds, neutrals)

### Documentation
- ✅ Comprehensive `README.md` with setup guide
- ✅ Full setup checklist
- ✅ Feature parity list with MyNRG
- ✅ Configuration instructions
- ✅ Deployment guide

### Git Integration
- ✅ 2 commits with clear messages
- ✅ All files pushed to GitHub

---

## ⏳ To Build Next

### High Priority (Day 1-2)

**Sections (create in order):**
1. `hero.liquid` - Hero banner with CTA
2. `trust-strip.liquid` - 4 icons with trust labels
3. `problem-dutching.liquid` - "Why regular cocoa doesn't work"
4. `verified-not-inflated.liquid` - Proof mechanism (3 cards)
5. `batch-lookup.liquid` - Batch checker form + results
6. `main-product.liquid` - Product gallery + bundle selector + subscription
7. `cart-drawer.liquid` - Slide-out cart
8. `main-cart.liquid` - Full cart page

**Snippets (support above sections):**
1. `price.liquid` - Price display with strike-through
2. `badge-seal.liquid` - Guarantee & savings badges
3. `fda-footnote.liquid` - Compliance disclaimer
4. `cart-line-item.liquid` - Cart item display
5. `free-shipping-bar.liquid` - Free shipping progress
6. `batch-card.liquid` - Batch lookup result card

**Assets:**
1. `assets/theme.js` - Vanilla JS for interactions
   - Menu toggle
   - Cart drawer
   - Bundle selector logic
   - Batch lookup filtering
   - Form handling

### Medium Priority (Day 2-3)

**Sections:**
- `how-it-works-steps.liquid` - 3-step process
- `ritual-gallery.liquid` - 3-4 lifestyle images
- `comparison-table.liquid` - VitalCocoa vs others
- `guarantee.liquid` - 60-day guarantee seal
- `faq-accordion.liquid` - Accordion (6-8 FAQs)
- `reviews-app-slot.liquid` - Reviews app placeholder
- `email-capture.liquid` - Newsletter signup
- `sticky-atc.liquid` - Mobile sticky ATC bar
- `advertorial-body.liquid` - Long-form ad content
- `product-details-accordions.liquid` - Expandable info
- `rich-text.liquid` - Generic rich-text section
- `image-with-text.liquid` - Image + text pairing

**Snippets:**
- `icon.liquid` - Inline SVG icons
- `json-ld-product.liquid` - Structured data
- `json-ld-organization.liquid` - Structured data
- `responsive-image.liquid` - Image with srcset

**Collection & Generic Pages:**
- `main-collection.liquid` - Collection page
- `main-search.liquid` - Search results
- `main-blog.liquid` - Blog listing
- `main-article.liquid` - Single article
- `main-page.liquid` - Generic page
- `main-404.liquid` - 404 page

### Lower Priority (Day 3+)

- Customer account pages (minimal)
- Advanced animations
- Exit-intent email capture modal
- Mobile email capture slide-in
- Advanced SEO
- Performance optimization

---

## 📊 Current Statistics

- **Files Created:** 36
- **Sections Ready:** 2 (announcement-bar, header, footer - groups)
- **Sections Needed:** 24+
- **Snippets Ready:** 0
- **Snippets Needed:** 10+
- **Templates Ready:** 15
- **Template Files Needed:** 0 (all scaffolded)
- **Asset Files:** 1 (theme.css from MyNRG)

---

## 🛒 Shopify Admin Tasks (Pre-Launch)

- [ ] Create product "VitalCocoa High-Flavanol Cocoa"
- [ ] Create 3 variants (Quantity: 1, 3, 6) with prices from supplier
- [ ] Upload product images (tub, nutrition, lab report)
- [ ] Create Shopify Subscriptions selling plan
- [ ] Create all 9 custom pages
- [ ] Assign templates to pages (`.json` files)
- [ ] Create Batch Result metaobjects definition
- [ ] Set up Main Menu in navigation
- [ ] Configure theme settings (colors, prices, copy)
- [ ] Test customer login
- [ ] Test currency switching (US/CA)
- [ ] Review all pages for compliance

---

## 🧪 Testing Checklist

- [ ] `shopify theme check` runs with zero errors
- [ ] `shopify theme dev` starts successfully
- [ ] All pages render (no 500 errors)
- [ ] Mobile preview at 375px works
- [ ] Customer login works
- [ ] Currency switch (US/CA) works
- [ ] Add to cart fires events
- [ ] Cart drawer opens/closes
- [ ] All links are correct
- [ ] Lighthouse mobile performance 85+
- [ ] `prefers-reduced-motion` respected
- [ ] Forms are accessible (labels, inputs)

---

## 📦 Data Placeholders Waiting for User

- **Product prices:** $0.00 → Need from supplier
- **Product images:** Placeholder CSS → Need actual images
- **Flavanol mg:** 500 → Confirm from supplier
- **Caffeine mg:** 12 → Confirm from supplier
- **Servings per tub:** 30 → Confirm from supplier
- **Free shipping threshold:** $150 → Decide with user
- **Subscription discount:** 10% → Decide with user
- **Guarantee days:** 60 → Confirm
- **Batch data:** None yet → Add after launch

---

## 🔗 Important Commands

```bash
# Start development
cd /Users/samuelmoussa/Desktop/vitalcocoa
shopify theme dev

# Check for errors
shopify theme check

# Push changes
shopify theme push

# Publish (make live)
shopify theme publish

# View current status
git log --oneline
```

---

## 📞 Notes for Next Phase

1. **MyNRG features successfully replicated:**
   - Customer account menu (Shopify native)
   - US/CA currency switching
   - Cart drawer with quantity steppers
   - Mobile hamburger menu
   - Sticky header
   - Footer with multi-column navigation

2. **VitalCocoa-specific features ready to build:**
   - Batch lookup interface
   - Lab results display
   - Comparison table (vs competitors, no names)
   - Compliance footer with FDA disclaimer
   - Bundle pricing logic (1/3/6 tubs)
   - Subscription integration

3. **Build order follows Claude's spec:**
   - Start with home page sections
   - Then product page
   - Then supporting pages (science, FAQ, etc.)
   - Then forms and components
   - Finally, collection and generic pages

4. **No breaking changes expected:**
   - All settings are configurable
   - No hard-coded prices or images
   - All copy is in settings or templates
   - Ready for multi-market (US/CA for now)

---

**Ready to begin section development!**
