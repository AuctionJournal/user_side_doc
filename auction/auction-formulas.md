[Auction](./index.md) · [Auction Journal](../index.md)

# Explain each formula used in an auction

Last modified: 2026-06-03

A **formula** is a saved rule (usually a **percentage**) that tells Auction Journal how to calculate charges on **sold lots** when you run **settlement**. You create formulas once under **Miscellaneous → Formulas**, then choose them on the **auction**, on **lots**, and sometimes on **customers**.

---

## The five main formula types

| Formula type | Who it affects | What it calculates |
|--------------|----------------|-------------------|
| **BUYER PREMIUM** | Buyer (purchaser) | Extra charge on top of the winning bid (hammer) |
| **BUYER TAX** | Buyer | Sales tax on the hammer (when the auction collects taxes) |
| **COMMISSION** | Seller (consignor) | Your commission on the hammer |
| **SELLER TAX** | Seller | Tax withheld on the hammer (when the auction collects taxes) |
| **SALESPERSON COMMISSION** | Salesperson | A share of **your commission** (not a % of hammer) |

Each formula also ties to a **Miscellaneous account** so amounts book to the right place. See [Formulas in Miscellaneous](../../auctioneer-misc/formulas.md) for how to create flat or **sliding scale** commission rules.

---

## Step 1 — Create formulas in Miscellaneous

Before building auctions, create the formulas you will reuse (for example `BP 10%`, `Comm 15%`, local tax codes).

1. Open **Miscellaneous → Formulas**.
2. Select **ADD NEW FORMULA** and pick the **Formula Type**.
3. Save each rule with a clear **Formula Code** and **Account**.

You need core types in place before **New Auction** will pass requirements checks (commission, buyer premium, and tax formulas).

---

## Step 2 — Set auction defaults (New Lot Default)

On the auction **Details** tab, **New Lot Default** picks the formulas that **new lots** inherit:

- **Commission**
- **Buyer Premium**
- **Buyer Tax** and **Seller Tax** (when **Collect Taxes** is enabled)
- Reserve, default seller, and related defaults

See [How to set default settings for all lots](default-lot-settings.md).

When you create or import a lot, these values pre-fill the lot. You can still change formulas on an individual lot later.

---

## Step 3 — Override on a specific lot (optional)

In lot build or edit, you can set **custom** commission, buyer premium, buyer tax, or seller tax for that lot only. Lots that still use auction defaults update if you change **New Lot Default** later; customized lots keep their own values.

---

## Step 4 — Customer-specific formulas (optional)

On a **customer** record, step 3 **Accounting** can override defaults for that person:

### Buyer (purchaser)

- **Buyers Premium** tab — **Set specific buyers premium** uses your chosen formula for lots **that customer wins** at settlement instead of the lot/auction default.
- **Buyer tax** on settlement still follows the **tax formula on the lot**, combined with whether the customer is **Taxable** and the auction **Collect Taxes** setting.

See [Configure customer as buyer and seller](../auctioneer-client/customer-preferences.md).

### Consigner (seller)

- **Consigner** settings — specific **commission** and **seller tax** formulas apply to **lots they consign** when “specific buyback” style settings are enabled.
- Otherwise those lots use the auction’s default commission and seller tax.

---

## When formulas actually run — settlement

Formulas apply when you **generate settlement** (or when clerking updates settlement after the sale). For each **sold** lot:

### Buyer invoice (lots the customer won)

| Charge | Which formula is used |
|--------|------------------------|
| Buyer premium | Customer-specific premium **if set**; otherwise the lot’s **Buyer Premium** formula |
| Buyer tax | Lot’s **Buyer Tax** formula (only if auction collects tax and buyer is taxable) |

Amounts are a **percentage of the hammer** (winning bid). The buyer’s line total is hammer + premium + tax (plus any separate lot charges).

More detail: [Buyer invoice — per won lot](buyer-lot-calculation.md).

### Seller invoice (lots they consigned)

| Charge | Which formula is used |
|--------|------------------------|
| Commission | **Commission** formula on the lot (from auction default or customer consigner override); sliding scale tiers apply by hammer band |
| Seller tax | **Seller Tax** on the lot when seller is taxable and auction collects tax |

Seller net is hammer **minus** commission and seller tax (and minus any seller lot expenses).

More detail: [Seller invoice — per sold lot](seller-lot-calculation.md).

---

## Quick reference — buyer vs seller

| | Buyer formulas | Seller formulas |
|--|----------------|-----------------|
| **Types** | BUYER PREMIUM, BUYER TAX | COMMISSION, SELLER TAX |
| **Set on auction defaults** | Buyer Premium, Buyer Tax | Commission, Seller Tax |
| **Customer override** | Specific buyer’s premium | Specific commission / seller tax (consigner) |
| **Settlement** | Added to what the buyer pays | Deducted from what the seller receives |

**SALESPERSON COMMISSION** is separate: it is a percent of **your commission**, assigned on the lot for salesperson tracking.

---

## Rules to remember

- Formulas must be **greater than zero** where a percentage is required — settlement expects valid rules on sold lots.
- **Buyer tax** always comes from the **lot**; only **buyer premium** can switch to a **customer-specific** formula.
- **Commission** can use **sliding scale** tiers (different % by hammer price band) — define that when creating a **COMMISSION** formula in Miscellaneous.
- Changing a formula code in Miscellaneous does not automatically re-open old settlements — plan edits carefully if invoices were already sent.

---

## Related topics

- [Formulas in Miscellaneous](../../auctioneer-misc/formulas.md)
- [Explain each auction field](fields.md) — default formula fields on the auction
- [Explain each auction lot field](../auction-lot/fields.md) — formula fields on lots
- [Generate settlement](generate-settlement.md)
- [Customer preferences](../auctioneer-client/customer-preferences.md)
