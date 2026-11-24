# VitalCocoa — Shopify Theme Build Prompt (for GitHub Copilot, Agent mode)

Paste everything below the line into Copilot Chat in **Agent mode**, with the `VitalCocoa` folder open in VS Code. Fill the `{{PLACEHOLDERS}}` in section 11 first, or leave them; the theme will show them as settings you can edit in the Shopify theme editor later.

---

## 0. YOUR ROLE

You are a senior Shopify theme developer and direct-response conversion designer. You are building the complete, launch-ready Online Store 2.0 theme for **VitalCocoa**, a premium high-flavanol cocoa drink, in this repository. When you finish, the owner should be able to run `shopify theme dev`, see a finished store, and publish it.

Work in small steps. After each step, run `shopify theme check` and fix every error before moving on. Do not ask me questions you can answer from this prompt or the repo. If something is missing, use a clearly named theme setting or placeholder and keep going.

## 1. WHAT IS IN THE REPO RIGHT NOW

- The repo is connected to Shopify via Shopify CLI (store `sjwjsx-uv.myshopify.com`, dev theme in `.theme-id.json`). Keep `README.md`, `.shopifyignore`, `shopify.app.toml` and `.theme-id.json` as they are.
- `layout/`, `sections/`, `snippets/`, `templates/`, `config/`, `locales/` exist but are **empty**. Shopify will not render the theme until they are filled. Building them is the job.
- `assets/theme.css` is the **design system and source of truth** for colors, type, radius and spacing. Keep its tokens and class names. Extend it; don't replace it.
- `assets/index.html` and `refrence/` are a static design preview. Use them as the visual reference for header, hero, cards, steps, forms and footer. `refrence/` is ignored by Shopify; don't delete it.
- `VitalCocoa-Website-Template.html` is an older draft. Its layout is useful; its copy is NOT. Replace all of its copy with the copy in this prompt. In particular, never ship "Feel the difference: boost to your energy, mood", "sourced from the finest farms", "Ethically sourced" or "Rich in antioxidants" unless the owner later supplies proof.
- Remove `assets/index.html` from the final theme (move it into `refrence/`), so it isn't uploaded as a stray asset.

## 2. THE BUSINESS IN ONE PARAGRAPH

VitalCocoa sells one hero product: a high-flavanol cocoa drink powder made from **non-alkalized** cocoa, with **{{FLAVANOL_MG}} mg of cocoa flavanols per serving, verified by an independent lab**, and **lead and cadmium results published for every batch**. The market is full of tubs that claim "1200 mg", "600 mg epicatechin" and "10X stronger" by adding flavanols and flavonoids together, and that say "heavy metal tested" without ever showing a result. VitalCocoa wins by being the cocoa you can **check**. The core promise is: **"The cocoa flavanol drink you can check."** The brand mechanism is **"Verified, Not Inflated."**

## 3. WHO WE SELL TO

Write every page for these three people. The first one is the priority.

1. **The Heart Watcher (main buyer).** 55–70, men and women. Their numbers at check-ups are creeping up. They've heard cocoa is "good for the heart" and have tried dark chocolate or regular cocoa. Quiet worry, not panic. They think most supplements are hype. They need plain words, a clear reason past cocoa didn't help, and proof.
2. **The Label Reader.** 45–65, longevity-minded, listens to health podcasts, has read about cadmium in cocoa. Assumes every label is padded. Converts on lab numbers, not adjectives.
3. **The Cocoa Ritualist.** 40–65, leans female, often not a coffee drinker. Wants a warm, calm drink that's good for her and doesn't taste fake-sweet. Stays because she enjoys it.

Real things buyers of competing products have said (use for tone and FAQ content, never as VitalCocoa reviews):
- "I can't get past the artificial sweetener flavor."
- "knowing that most other forms of supplementation (nibs, powder) tend to be rather high in cadmium"
- "The delivery took way too long."
- "I can't say whether it has improved my cognitive function, but I enjoy it as a beverage"
- "I made the mistake of adding to coffee and I had the jitters"

## 4. TONE AND ATTITUDE

**Attitude:** a quietly confident chocolatier who also runs a lab. Calm, exact, a little dry. We don't shout because we can show our numbers. We never mock the buyer; we gently show them what the industry didn't tell them.

**Voice rules:**
- Plain, everyday words. Aim for a 5th–7th grade reading level. Prefer short, concrete, Germanic words ("keeps", "shows", "drink") over Latin ones ("utilizes", "facilitates", "optimal").
- Full, natural sentences that flow like someone talking. No choppy fragments like "Pure. Tested. Proven." and no "That's not X. That's Y." pairs.
- Numbers instead of adjectives: "500 mg, checked by a lab" beats "powerful dose".
- Warm but never cute. No exclamation marks in body copy. No emojis.
- Never use: "revolutionary", "miracle", "game-changer", "superfood", "detox", "clinically proven" (about our product), "doctor recommended", "#1", "best".
- Luxury cues come from restraint: lots of white space, few words per screen, the gold used sparingly.

## 5. COMPLIANCE RULES — HARD LIMITS

This is a dietary supplement sold in the US. Every page must follow FDA/FTC rules. If a line of copy conflicts with these rules, the rules win.

**Allowed (structure/function claims, each followed by an asterisk):**
- "Supports healthy blood flow and circulation.*"
- "Supports healthy blood vessel function.*"
- "{{FLAVANOL_MG}} mg cocoa flavanols per serving, verified by an independent lab."
- "The same daily amount of cocoa flavanols used in COSMOS, the largest cocoa study ever run." (We match its dose. Never say our product was tested in COSMOS.)
- "Made with non-alkalized cocoa to keep its natural flavanols."
- "Lead and cadmium results published for every batch."
- "No added sugar. Nothing artificial." (Only if the final formula supports it — keep as a theme setting.)

**Required:** on every page that shows a starred claim, render this footnote in the footer area in small text: "*These statements have not been evaluated by the Food and Drug Administration. This product is not intended to diagnose, treat, cure, or prevent any disease." Also add: "Consult your doctor before use if you are pregnant, nursing, taking medication (especially blood thinners or blood pressure medication), or have a medical condition."

**Never write, anywhere (including alt text, meta descriptions and FAQ):**
- "lowers blood pressure", "lowers cholesterol", "prevents heart disease/heart attacks/stroke", "treats", "cures", "reverses aging"
- "replace your medication", "better than [any drug]"
- "clinically proven" or "doctor recommended" about VitalCocoa
- "results in X minutes/days" or any timed promise
- "zero heavy metals" or "no heavy metals" (cocoa always has trace amounts; say "tested, results published")
- Fake urgency: no countdown timers, no "only X left", no "sale ends tonight" unless a real, dated sale exists (then it's a setting with a real end date)
- Fake reviews, fake testimonials, fake "as seen in" logos, fake customer counts, fake star ratings. Leave review areas as app blocks that show nothing until a review app is installed.

## 6. DESIGN SYSTEM

Use the tokens in `assets/theme.css`. Key values:

| Token | Hex | Use |
|---|---|---|
| `--page` | #F7F1E8 | Page background (Parchment) |
| `--surface` | #FFFCF7 | Cards, drawers |
| `--text` | #2B1A14 | All headings and body (Cacao Noir) |
| `--text-muted` | #6E5A4C | Secondary text, struck-through prices |
| `--accent` | #7A3E26 | Buttons, links, selected states (Roasted Bean) |
| `--accent-deep` | #45271D | Footer, dark bands, button hover |
| `--savings` | #C2A15A | Savings pills and seals ONLY (Champagne Gold) |
| `--savings-text` | #2B1A14 | Text on gold. **Never white on gold** (fails contrast) |

- Font: Figtree (already loaded) for everything. For H1/H2 only, add **Cormorant Garamond 500/600** as a display face via a theme setting (default on). Keep body in Figtree.
- Fix in the old draft: `.savings-label` used white text on gold. It must use `var(--savings-text)`.
- Buttons: Roasted Bean fill, white label, `--radius-pill`. One primary button per screen.
- Generous spacing (`--section-space`). Max 2 short paragraphs per section on desktop.
- Every color is flat hex. No new colors except tints already in `theme.css`.
- WCAG AA: 4.5:1 for text, 3:1 for UI borders. Visible keyboard focus. Respect `prefers-reduced-motion`.
- Mobile first. Test at 375 px. Most buyers will come from Meta ads on a phone.

## 7. THEME ARCHITECTURE TO BUILD

Build a standard Online Store 2.0 theme. Every section has a `{% schema %}` with editable text, images and toggles, and presets so the owner can rearrange in the theme editor.

**Core files**
- `layout/theme.liquid` (head, fonts, `theme.css`, `{{ content_for_header }}`, header/footer groups, cart drawer, skip link, JSON-LD)
- `config/settings_schema.json` (colors from tokens, display font toggle, announcement text, free-shipping threshold, guarantee days and text, flavanol mg, caffeine mg, servings per tub, social links, FDA footnote toggle)
- `config/settings_data.json`
- `locales/en.default.json` (all UI strings) and `locales/en.default.schema.json`
- `sections/header-group.json`, `sections/footer-group.json`
- Templates (JSON): `index`, `product`, `product.landing` (ad landing variant), `collection`, `cart`, `page`, `page.science`, `page.batch-results`, `page.faq`, `page.about`, `page.contact`, `page.advertorial`, `search`, `404`, `blog`, `article`, `password`, plus `customers/*` minimal templates.

**Sections (each its own file)**
`announcement-bar`, `header`, `footer`, `hero`, `trust-strip`, `problem-dutching`, `verified-not-inflated`, `batch-lookup`, `how-it-works-steps`, `ritual-gallery`, `comparison-table`, `guarantee`, `faq-accordion`, `email-capture`, `main-product`, `product-details-accordions`, `sticky-atc`, `cart-drawer` (snippet-driven), `main-cart`, `advertorial-body`, `rich-text`, `image-with-text`, `reviews-app-slot`, `main-page`, `main-404`, `main-search`, `main-collection`, `main-blog`, `main-article`.

**Snippets**
`price`, `icon` (inline SVGs), `badge-seal`, `fda-footnote`, `cart-line-item`, `free-shipping-bar`, `json-ld-product`, `json-ld-organization`, `responsive-image`, `batch-card`.

## 8. PAGE-BY-PAGE CONTENT AND ORDER

Use this copy as the default value in each section's schema. Keep it word for word unless it breaks a compliance rule.

### 8.1 Announcement bar
"Every batch lab-tested. Results printed on every tub." Second rotating message (setting): "Free US shipping on orders over ${{FREE_SHIP_THRESHOLD}}."

### 8.2 Header
Logo left (wordmark "VitalCocoa", or image setting). Nav: Shop · The Science · Batch Results · FAQ. Right: search, account, cart (opens the drawer, shows count). Sticky, slim on scroll. Mobile: hamburger drawer.

### 8.3 Home page (`index.json`), in this order
1. **Hero**
   - Eyebrow: "High-flavanol cocoa"
   - H1: "The cocoa flavanol drink you can check."
   - Lede: "{{FLAVANOL_MG}} mg of cocoa flavanols in every serving, checked by an outside lab. Lead and cadmium results for your batch, printed on the tub. And it still tastes like real hot chocolate."
   - Primary button: "Shop VitalCocoa" → product. Secondary text link: "See this month's lab results" → Batch Results.
   - Image: product tub on parchment with a mug (image picker; until uploaded, keep the CSS tub placeholder from the draft).
   - Under the button, small line: "60-day guarantee · Ships in 48 hours · No added sugar"
2. **Trust strip** (4 icons with short text): "Lab-verified dose" · "Metals tested, results published" · "Non-alkalized cocoa" · "Nothing artificial". No fake press logos.
3. **Problem: why your cocoa isn't doing much** (`problem-dutching`)
   - H2: "Your hot chocolate isn't doing what you think."
   - Body: "Most cocoa is "Dutched." It gets washed in an alkali to make it darker and smoother, and that strips out most of the flavanols, the part researchers actually study. A spoonful of regular cocoa gives you somewhere between 37 and 130 mg. The largest cocoa study ever run used 500 mg a day."
   - Small visual: two bars, "Regular cocoa: 37–130 mg" vs "VitalCocoa: {{FLAVANOL_MG}} mg" (simple CSS bars, no chart library).
4. **Verified, Not Inflated** (`verified-not-inflated`)
   - H2: "The number on our label is the number in the tub."
   - Body: "A lot of tubs add flavanols and flavonoids together so the number on the front looks bigger. We don't. Our label shows cocoa flavanols only, measured by an independent lab, and we publish the result for every batch."
   - Three cards: "Flavanols only, never stacked" / "Tested by a third-party lab" / "Results you can look up".
5. **Batch lookup teaser** (`batch-lookup`, compact mode)
   - H2: "Check your batch."
   - Body: "Type the batch number from the bottom of your tub and see its flavanol count, lead and cadmium levels, and the lab report."
   - Input + button → goes to Batch Results page with `?batch=` prefilled.
6. **How to drink it** (`how-it-works-steps`)
   - 01 "One scoop" — "Mix one level scoop into hot or cold milk, coffee, a smoothie or oats."
   - 02 "Make it yours" — "It's unsweetened dark chocolate. Add honey, maple or monk fruit if you like it sweeter."
   - 03 "Once a day" — "Flavanols work best as a daily habit, so pick the moment you'll keep: a morning mug or an evening wind-down."
7. **Ritual gallery** (`ritual-gallery`): 3–4 lifestyle images with one-line captions ("A calmer morning mug", "Stirred into a smoothie", "An evening cup without the sugar"). Image pickers; placeholder blocks until images are uploaded.
8. **Comparison table** (`comparison-table`)
   - H2: "What you should be able to see on any cocoa tub."
   - Columns: "VitalCocoa" vs "Typical flavanol tub". Do NOT name competitors.
   - Rows: Flavanols measured by an outside lab (✓ / rarely) · Flavanol number not stacked with flavonoids (✓ / often stacked) · Lead and cadmium results published (✓ / "tested", no numbers) · Caffeine per serving on the label (✓ / often missing) · Artificial sweeteners (None / common) · Non-alkalized cocoa (✓ / varies).
9. **Guarantee** (`guarantee`)
   - Gold seal snippet with "{{GUARANTEE_DAYS}}-day guarantee".
   - Text (setting): "{{GUARANTEE_TEXT}}". Default: "If VitalCocoa isn't for you, send back any unopened tubs within 60 days for a full refund."
10. **FAQ accordion** (6 top questions, full list on FAQ page)
11. **Reviews app slot** (`reviews-app-slot`): supports `@app` blocks. Hidden entirely if no app block is added. Never ship sample reviews.
12. **Email capture** (`email-capture`)
   - H2: "Get the lab results first."
   - Body: "Join for new batch results, recipes and the occasional member offer. No spam, unsubscribe anytime."
   - Shopify `{% form 'customer' %}` with `contact[tags]=newsletter`. Offer text is a setting (default empty, so no discount is promised until the owner creates one).

### 8.4 Product page (`product.json`) — the money page
Above the fold on mobile, in this order:
1. Image gallery (swipe on mobile, thumbnails on desktop; first image is the tub, second the nutrition/supplement facts panel, third a sample lab report).
2. Rating slot (app block, hidden if empty).
3. Title: "VitalCocoa High-Flavanol Cocoa"
4. Sub-line: "{{FLAVANOL_MG}} mg lab-verified cocoa flavanols · {{SERVINGS}} servings · {{CAFFEINE_MG}} mg natural caffeine per serving"
5. **Bundle selector:** add an `@app` block slot here for **Kaching Bundles** (it renders the quantity tiers). ALSO build a native fallback tier selector (radio cards) used when no app block is present, so the page works on day one:
   - Tier 1: "1 Tub" — {{PRICE_1}} each
   - Tier 2: "3 Tubs" — {{PRICE_3}} each — label "SAVE {{SAVE_3}}%" — **preselected**
   - Tier 3: "6 Tubs" — {{PRICE_6}} each — label "SAVE {{SAVE_6}}%" — badge "BEST VALUE"
   - Each tier shows unit price large, struck-through full price in `--text-muted`, and "Total: $X" as a small italic line. Savings pills use gold with dark text. Badge uses `--text` background with white text. Selected card: white fill, `--accent` border; unselected: `--accent-soft` fill.
   - Tiers map to product variants (Quantity: 1, 3, 6). Read prices from variants; never hardcode.
6. **Subscribe & save** option: support Shopify selling plans (`product.selling_plan_groups`) with a radio "One-time purchase" / "Subscribe & save {{SUB_DISCOUNT}}% — skip or cancel anytime". Keep the subscribe row visually calm (no loud colors). If no selling plan exists, hide it.
7. Add to cart button (full width): "Add to cart — $[live total]". Below it, small: "Ships in 48 hours · {{GUARANTEE_DAYS}}-day guarantee · Secure checkout". Show dynamic checkout buttons (Shop Pay, Apple Pay).
8. Trust row: 3 small icons (Lab-verified · Batch results online · Non-alkalized).
9. Accordions: "What's inside" (supplement facts, flavanols, caffeine, allergens) · "How to use" · "Lab results" (link to Batch Results) · "Shipping and returns" · "Safety" (the doctor-consult line).

Below the fold (reuse home sections): Problem: Dutching → Verified, Not Inflated → Batch lookup → How to drink → Comparison → Guarantee → Reviews slot → Full FAQ.

**Sticky add-to-cart bar** on mobile once the main button scrolls out of view: product name, selected tier, price, "Add to cart".

### 8.5 Ad landing product page (`product.landing.json`)
Same product, built for cold Meta traffic: no header nav links (logo and cart only), and the sections reordered to tell the story before the buy box: Hero (problem headline "Your hot chocolate isn't doing what you think.") → Problem: Dutching → Verified, Not Inflated → Buy box (main-product) → Batch lookup → Comparison → Guarantee → FAQ → Sticky ATC. The owner assigns this template in Shopify admin and points ads at `?view=landing`.

### 8.6 The Science page (`page.science.json`)
Plain-English explainer. Sections:
- "What flavanols are": "Flavanols are natural plant compounds. Cocoa beans are one of the richest sources. The one researchers study most in cocoa is called epicatechin."
- "What they do": "Flavanols support your body's own production of nitric oxide, the signal that helps blood vessels relax and open. That's why they're studied for blood flow and blood vessel health.*"
- "Why the dose matters": the COSMOS facts, stated carefully: "COSMOS followed 21,442 US adults and gave them 500 mg of cocoa flavanols a day. We match that daily amount. Our product was not part of that study." Link to the published paper (`https://pmc.ncbi.nlm.nih.gov/articles/PMC9170467`).
- "Why most cocoa falls short": Dutching explanation.
- "Why we test for metals": "Cocoa naturally picks up cadmium from the soil and lead while the beans dry outdoors. Consumer Reports found both in all 48 cocoa products it tested. We can't change the soil, so we test every batch and show you the numbers."
- Render the FDA footnote.

### 8.7 Batch Results page (`page.batch-results.json`) — the brand's proof engine
Build with a **metaobject** definition `batch_result` (document in README how to create it in Shopify admin: Settings → Custom data → Metaobjects) with fields:
`batch_number` (single line text), `production_date` (date), `flavanols_mg_per_serving` (number), `epicatechin_mg_per_serving` (number, optional), `lead_mcg_per_serving` (number), `cadmium_mcg_per_serving` (number), `caffeine_mg_per_serving` (number), `lab_name` (single line text), `test_date` (date), `coa_file` (file reference, PDF).

The section loops over `shop.metaobjects.batch_result.values`, renders a search box that filters by batch number client-side (also reads `?batch=` from the URL), and shows a `batch-card` per result with every number, the lab name, test date and a "Download lab report (PDF)" link. If no metaobjects exist yet, show: "Our first batch results will be posted here before launch." Never render sample numbers on the live site.

### 8.8 FAQ page (`page.faq.json`)
Use these answers (edit numbers via settings):
- **Is this just cocoa powder?** "It's cocoa made to keep its flavanols. Regular cocoa is usually alkalized, which strips most of them out. VitalCocoa is non-alkalized and standardized to {{FLAVANOL_MG}} mg of flavanols per serving."
- **Why do other brands say 1200 mg?** "Many add flavanols and flavonoids together to show a bigger number. We list cocoa flavanols only, measured by an independent lab."
- **Does cocoa have lead or cadmium in it?** "All cocoa contains trace amounts, because cadmium comes from the soil and lead from drying the beans outdoors. We test every batch and publish the numbers so you can decide for yourself."
- **How much caffeine is in it?** "About {{CAFFEINE_MG}} mg per serving, from the cocoa itself. If you're sensitive to caffeine, try it earlier in the day."
- **What does it taste like?** "Like rich, unsweetened dark chocolate. It's a little bitter, because the flavanols are the bitter part. Most people add milk and a little honey or monk fruit."
- **When will I feel something?** "We can't promise a feeling or a timeline, and we're wary of brands that do. Studies used daily intake over months. Most people treat it as a daily habit."
- **Can I take it with medication?** "Talk to your doctor first, especially if you take blood thinners or blood pressure medication."
- **What's your guarantee?** setting text.
- **How fast do you ship?** "Orders ship within 48 hours on business days from the US, with tracking."
- **Can I subscribe?** "Yes. Subscribe and save {{SUB_DISCOUNT}}%. Skip, change or cancel anytime from your account."

### 8.9 About page (`page.about.json`)
Title: "Our standard." Short story: "We started VitalCocoa because buying cocoa flavanols meant trusting numbers nobody would show us. So we set three rules: measure the flavanols with an outside lab, test every batch for lead and cadmium, and publish everything. If we can't show it, we don't claim it."

### 8.10 Advertorial page (`page.advertorial.json`)
Long-form, editorial-looking page for cold ads (no header nav, narrow 680 px column, serif display headings). Headline: "Why your hot chocolate isn't doing what you think, and what to look for instead." Structure: the Dutching story → the label-maths problem → the metals question → what to look for on any tub (the comparison checklist) → introduce VitalCocoa as one product that meets all of it → guarantee → button to `product?view=landing`. Body text lives in a rich-text setting so the owner can edit it. Clearly mark it as an advertisement at the top in small text: "Advertorial".

### 8.11 Cart drawer and cart page
- Slide-out cart drawer on add to cart (no page redirect). Line items, quantity steppers, remove.
- Free-shipping progress bar: "You're $X away from free shipping" → "You've unlocked free shipping." Threshold from settings.
- One quiet upsell block (setting, product picker; default empty).
- Checkout button + small trust line. No countdown timers.

### 8.12 Footer
Columns: Shop · Learn (The Science, Batch Results, FAQ) · Help (Contact, Shipping, Returns, Privacy, Terms) · Email signup. Then the FDA footnote and the doctor line in small text. Wordmark and "© 2026 VitalCocoa".

## 9. CONVERSION AND MARKETING BUILT INTO THE SITE

Build these so the site sells on its own and works with paid ads:
1. **One clear path:** every page ends in a single primary button to the product page.
2. **Preselect the 3-tub tier.** That's the average order value lever.
3. **Proof before price on landing pages** (`product.landing`, advertorial).
4. **Sticky mobile add to cart** and **cart drawer** (fewer steps to checkout).
5. **Subscriptions** shown calmly and clearly optional.
6. **Email capture** on home, footer and an exit-intent modal on desktop only (setting, off by default). Mobile: a small slide-in after 30 seconds (setting, off by default). Never block content.
7. **Batch lookup as a marketing hook.** Every ad can say "check your batch", and the page proves it.
8. **Shareable proof:** each batch card has a "Copy link" button that copies `/pages/batch-results?batch=XXXX`.
9. **UTM-safe links:** never strip query strings; keep `?view=landing` working with UTMs.
10. **Tracking:** do NOT hardcode Meta Pixel or GA in the theme. Add a README note: install the Meta and Google & YouTube Shopify apps (they use Customer Events). Make sure add-to-cart in the drawer fires Shopify's standard events by using the Cart AJAX API.
11. **SEO:** unique titles and meta descriptions from settings; `json-ld-product` with name, brand, image, offers (price, availability) and NO aggregateRating until real reviews exist; `json-ld-organization`; descriptive alt text on all images; one H1 per page.
12. **Speed:** no jQuery or heavy libraries. Vanilla JS in `assets/theme.js` with `defer`. Lazy-load images below the fold with `image_url` and `image_tag` widths. Target Lighthouse mobile performance 85+.

## 10. BUILD ORDER

1. Move `assets/index.html` to `refrence/`. Create `layout/theme.liquid`, `config/settings_schema.json`, `config/settings_data.json`, `locales/en.default.json`, `locales/en.default.schema.json`. Run `shopify theme check`.
2. Header group, footer group, announcement bar, `fda-footnote` snippet.
3. Home page sections in the order in 8.3.
4. Product page, native bundle selector, selling plans, sticky ATC, cart drawer, `assets/theme.js`.
5. `product.landing` template.
6. Science, Batch Results (metaobject), FAQ, About, Contact, Advertorial pages.
7. Collection, search, cart page, 404, blog/article, password, customer templates (simple, on-brand).
8. JSON-LD snippets, SEO settings.
9. Accessibility and contrast pass, mobile pass at 375 px, `prefers-reduced-motion` pass.
10. Run `shopify theme check` (zero errors), then `shopify theme dev` and fix anything visibly broken.
11. Update `README.md` with: how to create the `batch_result` metaobject, how to set up product variants (1/3/6) and the selling plan, how to assign `product.landing` and `page.*` templates, and the list of placeholders still to fill.

Commit after each step with a clear message.

## 11. PLACEHOLDERS (fill these or leave them as theme settings)

| Placeholder | Meaning | Status |
|---|---|---|
| `{{FLAVANOL_MG}}` | Lab-verified cocoa flavanols per serving (target 500+) | From supplier COA |
| `{{CAFFEINE_MG}}` | Caffeine per serving | From supplier |
| `{{SERVINGS}}` | Servings per tub | From supplier |
| `{{PRICE_1}}`, `{{PRICE_3}}`, `{{PRICE_6}}` | Per-tub price at 1 / 3 / 6 tubs | Pending landed cost |
| `{{SAVE_3}}`, `{{SAVE_6}}` | Savings % vs single-tub price; must match the prices exactly | Calculate from prices |
| `{{SUB_DISCOUNT}}` | Subscription discount % | Pending |
| `{{FREE_SHIP_THRESHOLD}}` | Free shipping threshold in USD | Pending |
| `{{GUARANTEE_DAYS}}` | 60 | Decided |
| `{{GUARANTEE_TEXT}}` | Default: unopened tubs within 60 days for a full refund | Confirm wording |
| "Ships in 48 hours" | Used in several places; make it a single theme setting | Only keep if your 3PL can guarantee it |

Pricing rules for the bundle (enforce in the README and default settings): one price ending across all tiers (.95 or .00, not .99); unit price gets the clean ending; every "SAVE X%" must equal 1 − (tier price ÷ single price) exactly; the discount grows but by less each step (e.g. 20% then 30%, not 20% then 40%).

## 12. DONE MEANS

- `shopify theme check` passes with zero errors.
- Every page in section 8 exists, is editable in the theme editor, and looks right at 375 px and 1440 px.
- No copy breaks section 5. Search the theme for "lower", "prevent", "cure", "treat", "proven", "no heavy metals", "zero" and "#1" and fix any hit.
- No fake reviews, ratings, logos, timers or stock counts anywhere.
- White text never sits on gold.
- Add to cart opens the drawer, the free-shipping bar updates, checkout works.
- The Batch Results page shows the "coming soon" message with no metaobjects, and real cards once one is added.
- README lists every remaining manual step for the owner.
