[Auction](./index.md) · [Auction Journal](../index.md)

# Explain the full settlement calculation for a buyer

A **buyer settlement** (buyer invoice) is what a winning bidder owes the auctioneer for **sold lots** in one auction. The total is built **lot by lot**, then you can add **auction-level fees**, **per-lot extras**, and one **adjustment** before collecting payment.

**Per-lot detail only:** [How is each lot I won calculated?](buyer-lot-calculation.md).

**Prerequisite:** [How is a settlement generated for an auction?](generate-settlement.md).

---

## What you start with at generation

When you click **Generate Invoice**, the system creates one invoice per **approved** bidder (or floor buyer registration) who won at least one **Sold** lot.

For each **Sold** lot on that invoice:

| Line item | What it is |
|-----------|------------|
| **Hammer** | The lot’s winning bid amount (from clerking / current bid on the lot) |
| **Buyer’s premium** | Percentage fee on the hammer — from the **customer’s** buyer premium setting when you use a custom premium, otherwise from the **lot** setup |
| **Buyer tax** | Only if the auction **collects taxes** and the buyer (customer) is marked **taxable** — percentage on the **hammer** using the lot’s buyer tax formula |

**Per-lot total (at generation):**

```text
Hammer + Buyer’s premium + Buyer tax (if applicable)
```

The invoice **subtotal** is the **sum of all lot lines** for that buyer. **Auction-level charges** are **not** added automatically—they start empty until you add them when editing the settlement.

---

## Where premium and tax rates come from

| Setting | Effect |
|---------|--------|
| Customer uses **default** buyer premium | Rate comes from the **lot** (buyer premium on the lot) |
| Customer has a **custom** buyer premium | Rate comes from the **customer** profile |
| Auction does not collect taxes | No buyer tax line |
| Customer not **taxable** | No buyer tax line even if the auction collects taxes |
| Taxable + auction collects taxes | Tax rate from the **lot** buyer tax formula |

Rates are **percentages of the hammer** (not of hammer + premium) in the current system.

---

## Invoice totals (fields you see)

| Label / idea | Meaning |
|--------------|---------|
| **Lot charges total** | Sum of every lot line (hammer + premium + tax on each lot) |
| **Auction charges** | Fees you add at the **auction** level on this invoice (for example delivery, admin fee)—**added** to what the buyer owes — [how to add](buyer-auction-charges.md) |
| **Extra lot charges** | Additional fees on a **specific lot** you add when editing (fixed or percent of that lot’s hammer) — [how to add](buyer-lot-expenses.md) |
| **Subtotal / total** | Lot total + auction charges (+ lot extras after you add them) |
| **Adjustment** | One discount or surcharge for the whole invoice (from your misc accounts marked **Discounts** or **Surcharges**) |
| **Grand total** | Subtotal after adjustment — amount the buyer should pay before receipts |
| **Paid / balance due** | Updated when you record payments — [Settlement payment](settlement-payment.md) |

At generation, **grand total** equals the **lot charges total** until you add auction fees or an adjustment.

---

## Example (one lot)

| Item | Rate | On $500 hammer |
|------|------|----------------|
| Hammer | — | $500.00 |
| Buyer’s premium | 10% | $50.00 |
| Buyer tax | 7% (if applicable) | $35.00 |
| **Lot total** | | **$585.00** |

If the same buyer won two lots with the same rates, the invoice **lot subtotal** is **$1,170.00** before any auction-level charges or adjustments.

---

## Changes after the invoice exists

| Action | Effect on buyer total |
|--------|------------------------|
| **Edit clerking** (hammer, sold/pass, buyer) | Lot lines rebuild; totals update (may take a moment to refresh) |
| **Edit settlement** — change premium/tax on a line | Recalculates that lot using the new formula |
| **Add auction charge** | Increases amount owed |
| **Add extra lot charge** | Increases that lot and the invoice |
| **Adjustment — surcharge** | Increases **grand total** |
| **Adjustment — discount** | Decreases **grand total** |
| **Payment recorded** | Reduces balance due; further edits may be blocked when marked paid |

You cannot run **Generate Invoice** again for the same auction; fix amounts through clerking or **edit settlement**.

---

## Onsite vs online (which lots count)

| Buyer type | Lots on the invoice |
|------------|---------------------|
| **Floor bidder** (onsite) | Sold lots where they are recorded as the **floor** winner |
| **Internet bidder** (onsite live) | Sold lots they won in the **live** session |
| **Online timed / absolute** | Sold lots where they are the **lot winner** and clerking is **Sold** |

---

## Related

- [Generate settlement](generate-settlement.md)
- [Edit settlement](edit-settlement.md) · [Settlement adjustments](settlement-adjustments.md)
- [Auction Dashboard — Settlement tab](auction-dashboard.md#settlement-tab)
- Dev detail: [Buyer settlement calculation](../../auction/settlement/buyer-calculation.md) · [Settlement fields](../../auction/settlement/fields.md)
