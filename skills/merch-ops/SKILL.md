---
name: merch-ops
description: Manage artist merchandise on Shopify — create products, track inventory, run drops, generate discount codes, and coordinate with email campaigns. Use when the artist asks about merch, t-shirts, physical products, or Shopify store management.
metadata: { "openclaw": { "emoji": "👕" } }
---

# Merch Ops

Manage artist merchandise and Shopify store operations.

## When to Activate

- "Set up merch," "create a product," "merch drop"
- "How are merch sales?" "Generate a discount code"
- Release plan includes merchandise component

## Merch Strategy

### Merch That Sells for Independent Artists

| Product | Margin | Effort | Best For |
|---|---|---|---|
| T-shirts | 50-70% | Low (POD) | Core revenue, fan uniform |
| Hoodies | 40-60% | Low (POD) | Fall/winter, premium feel |
| Vinyl records | 30-50% | High (manufacturing) | Collectors, premium fans |
| Cassettes | 60-80% | Medium | Aesthetic, niche appeal |
| Posters | 70-85% | Low | Tour dates, artwork prints |
| Stickers | 80-90% | Very low | Low-cost fan engagement |
| Hats | 50-65% | Low (POD) | Streetwear audience |
| Digital downloads | 95-100% | None | Bonus tracks, stems, sessions |

### Print-on-Demand vs Inventory

**Print-on-Demand (Printful, Printify, Gooten):**
- No upfront cost
- Ships per order
- Higher per-unit cost
- No inventory risk
- Best for: testing designs, artists under 10K followers

**Holding inventory:**
- Upfront cost ($500-2000+)
- Bulk pricing = better margins
- Storage needed
- Risk of unsold stock
- Best for: proven designs, artists with engaged fanbase

## Shopify Setup

Use the Shopify API or existing shopify skill for:

```bash
# Create a product
POST /admin/api/2024-10/products.json
{
  "product": {
    "title": "[Artist] - [Design Name] Tee",
    "body_html": "<p>Official merch. 100% cotton.</p>",
    "vendor": "[Artist Name]",
    "product_type": "T-Shirt",
    "tags": "merch, tee, [release-name]",
    "variants": [
      { "option1": "S", "price": "30.00" },
      { "option1": "M", "price": "30.00" },
      { "option1": "L", "price": "30.00" },
      { "option1": "XL", "price": "30.00" }
    ]
  }
}
```

## Merch Drop Playbook

For a coordinated merch drop tied to a release:

**2 weeks before:**
- [ ] Finalize designs (mockups approved by artist)
- [ ] Create Shopify products (hidden/draft)
- [ ] Set up Klaviyo email with preview
- [ ] Create social teaser content

**1 week before:**
- [ ] Announce drop date on social
- [ ] Email "first look" to fan list
- [ ] Generate discount code for superfans (10-15% off)

**Drop day:**
- [ ] Publish products on Shopify
- [ ] Send "IT'S LIVE" email
- [ ] Post across all social platforms
- [ ] IG Story with direct link
- [ ] Pin link in TikTok bio

**Post-drop:**
- [ ] Share UGC (fans wearing merch)
- [ ] Send "last chance" email after 5-7 days
- [ ] Report on sales (units, revenue, best sellers)

## Pricing Guidelines

| Cost to Make | Suggested Retail | Margin |
|---|---|---|
| $8-12 (POD tee) | $28-35 | ~65% |
| $15-20 (bulk tee) | $28-35 | ~45% |
| $15-25 (POD hoodie) | $55-65 | ~60% |
| $3-5 (sticker pack) | $8-12 | ~65% |
| $15-25 (vinyl pressing) | $25-40 | ~40% |

Rule of thumb: 3-4x cost for retail price. Fans understand artist merch is premium.
