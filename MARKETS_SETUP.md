# VitalCocoa Markets Setup Guide

## Setting Up US & CA Markets in Shopify Admin

Your VitalCocoa store will serve both **US (USD)** and **Canada (CAD)** markets with:
- Same products
- Different pricing per market
- Same shipping to both countries
- Automatic currency detection based on visitor location

---

## Step 1: Create Markets in Shopify Admin

**Location:** Settings → Markets

### Create US Market:
1. Click **"Add market"**
2. **Market name:** United States
3. **Primary locale:** English (United States)
4. **Regions:** Select "United States"
5. **Currency:** USD
6. Click **"Create market"**

### Create CA Market:
1. Click **"Add market"**
2. **Market name:** Canada
3. **Primary locale:** English (Canada)
4. **Regions:** Select "Canada"
5. **Currency:** CAD
6. Click **"Create market"**

---

## Step 2: Set Up Pricing for Each Market

**Location:** Products → (Select VitalCocoa product) → Markets

### For Each Variant (1, 3, 6 tubs):

#### US Market:
- **Variant:** Quantity 1
  - **Price (USD):** $X.XX (from supplier)
  
- **Variant:** Quantity 3
  - **Price (USD):** $X.XX (3 × unit price)
  
- **Variant:** Quantity 6
  - **Price (USD):** $X.XX (6 × unit price)

#### CA Market:
- **Variant:** Quantity 1
  - **Price (CAD):** $X.XX × 1.3 (approximate conversion, adjust as needed)
  
- **Variant:** Quantity 3
  - **Price (CAD):** $X.XX × 1.3
  
- **Variant:** Quantity 6
  - **Price (CAD):** $X.XX × 1.3

**Note:** Adjust CAD prices based on:
- Current USD/CAD exchange rate
- Your margin preferences
- Competitive pricing in Canada

---

## Step 3: Set Up Shipping for Each Market

**Location:** Settings → Shipping and delivery

### Shipping Profile: Standard Shipping

#### US Shipping:
- **Region:** United States
- **Shipping rate:** $X (or free over $Y threshold)
- **Example:** 
  - $5.99 for orders under $150
  - FREE for orders $150+

#### CA Shipping:
- **Region:** Canada
- **Shipping rate:** $X CAD (or free over $Y CAD threshold)
- **Example:**
  - $9.99 CAD for orders under $150 CAD
  - FREE for orders $150+ CAD

**Keep rates the same relative to currency** (e.g., if US is $5.99, CA should be ~$7.80 CAD)

---

## Step 4: Set Default Market & Redirect Rules

**Location:** Settings → Markets → "Market settings"

### Primary Market: 
- Set to **United States** (the larger market)

### Redirect Settings:
Enable automatic redirect so:
- Visitors from US → See USD prices automatically
- Visitors from CA → See CAD prices automatically

---

## Step 5: Assign Markets to Domains (Optional)

If you use separate domains:
- `vitalcocoa.com` → US market (USD)
- `vitalcocoa.ca` → CA market (CAD)

**Location:** Settings → Markets → (Market name) → Assign sales channel

---

## Step 6: Configure Payments for Each Market

**Location:** Settings → Payment providers

Ensure your payment gateway supports:
- ✅ USD (Stripe, PayPal, etc.)
- ✅ CAD (most processors support both)

No additional setup needed if your processor supports multi-currency.

---

## Step 7: Set Up Taxes for Each Market

**Location:** Settings → Taxes and duties

### US Taxes:
- **Sales tax:** Configure by state if needed
  - Or use simplified rate by market
  
### CA Taxes:
- **GST/HST:** Add Canadian tax rates
  - Ontario (HST): 13%
  - Other provinces vary
  - Or let Shopify handle automatically

**Recommendation:** Use Shopify's automatic tax calculation (if available in your plan)

---

## Step 8: Test Market Switching

1. Go to your store: https://sjwjsx-uv.myshopify.com
2. Look for **currency switcher in header** (shows current currency)
3. Click currency button to switch between USD ↔ CAD
4. Prices should update immediately
5. Verify:
   - ✅ USD prices show for US market
   - ✅ CAD prices show for CA market
   - ✅ Correct shipping rates apply

---

## Step 9: Configure Theme Settings for Markets

**In Shopify theme editor (Customize theme):**

### Free Shipping Threshold:
- Create **separate settings** for each market, OR
- Use one threshold and handle conversion in display

**Option A (Recommended):**
- Free shipping threshold (USD): $150
- Free shipping threshold (CAD): $195 (1.3× conversion)

**Option B (Simpler):**
- Free shipping threshold: Use same number, adjust in messaging
  - "Free shipping on orders over $150" (USD)
  - "Free shipping on orders over $195" (CAD)

---

## Step 10: Localization for Each Market

**In theme `locales/en.default.json`:**

Add market-specific translations if needed:
- "Free Shipping Threshold": varies by market
- "Shipping Info": varies by market
- "Return Address": varies by market

**Currently not needed** since you're using same English messaging, but ready to expand.

---

## Market-Specific Customization (Optional)

If you want **different messaging per market**, add to theme settings:

```json
"market_us_message": "Ships from US within 48 hours",
"market_ca_message": "Ships from Canada within 2-3 business days"
```

Then use in `header.liquid`:
```liquid
{% if localization.country.iso_code == 'US' %}
  {{ settings.market_us_message }}
{% elsif localization.country.iso_code == 'CA' %}
  {{ settings.market_ca_message }}
{% endif %}
```

---

## Checklist: Markets are Live ✅

- [ ] US Market created (United States, USD)
- [ ] CA Market created (Canada, CAD)
- [ ] Product variants priced for each market
- [ ] Shipping rates configured for each market
- [ ] Default market set to US
- [ ] Market redirect enabled
- [ ] Taxes configured
- [ ] Currency switcher tested in store
- [ ] Prices update when switching currency
- [ ] Shipping rates apply correctly
- [ ] Payment gateway supports USD + CAD

---

## Commands to Test Markets

```bash
# Check current market configuration
shopify theme check

# Start dev server
shopify theme dev

# Push updated settings
shopify theme push
```

---

## Example Pricing Structure

| Product | US Price | CA Price | 
|---------|----------|----------|
| 1 Tub | $39.99 | $51.99 |
| 3 Tubs | $99.99 | $129.99 |
| 6 Tubs | $179.99 | $233.99 |

**Note:** Adjust based on supplier costs and market positioning!

---

## Troubleshooting

**Q: Currency not switching?**
A: Check that markets are created and assigned to the sales channel

**Q: Prices showing wrong?**
A: Verify product variants have prices set for each market

**Q: Shipping not updating?**
A: Ensure shipping rates are configured for each country

**Q: Tax not calculating?**
A: Enable automatic tax calculation in Shopify settings

---

## Ready to Go Live! 🚀

Once markets are set up, your store will automatically:
- Detect visitor location
- Show correct currency
- Apply correct prices
- Use correct shipping rates
- Calculate correct taxes

**No code changes needed** - all configured in Shopify Admin!

---

**Last updated:** November 23, 2026
