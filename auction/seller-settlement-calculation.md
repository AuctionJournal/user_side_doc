[Auction](./index.md) · [Auction Journal](../index.md)

# Explain the full settlement calculation for a seller

A **seller settlement** is the **payout statement** for a **consignor** (seller customer) for **sold lots** in one auction. The total is what you owe the seller **after** commissions, taxes, and lot-level expenses—not what the buyer paid.

Per-lot detail only: [How is each sold lot calculated on a seller invoice?](seller-lot-calculation.md).

**Prerequisite:** [How is a settlement generated for an auction?](generate-settlement.md). Compare with [Buyer settlement calculation](buyer-settlement-calculation.md).

---

## Who gets a seller invoice

When you **Generate Invoice**, the system finds every **seller** (customer) assigned on lots in that auction. For each seller:

- Include only lots clerked **Sold** that belong to them.
- If they have **no** sold lots, **no** seller invoice is created.
- One invoice per seller per auction (all their sold lots on the same document).

---

## Per-lot calculation (at generation)

For each **Sold** lot:

| Line item | What it is |
|-----------|------------|
| **Hammer** | Winning bid amount on the lot |
| **Commission** | Percentage **withheld** from the hammer — from the **commission** formula on the lot (may be a **sliding scale** by hammer tier) |
| **Seller tax** | Only if the lot is **seller taxable** and the auction **collects taxes** — percentage **withheld** from the hammer |
| **Seller lot expenses** | Fixed amounts set on the lot (for example marketing or handling)—**subtracted** from the seller’s net |

**Per-lot net (what counts toward the seller):**

```text
Hammer − Commission − Seller tax (if applicable) − Seller lot expenses on that lot
```

Unlike a **buyer** invoice, fees are **deductions** from the hammer, not additions on top.

---

## Invoice totals (fields you see)

| Label / idea | Meaning |
|--------------|---------|
| **Lot charges total** | Sum of each lot’s **net** (after commission, tax, and lot expenses) |
| **Auction charges** | Fees you add at the **auction** level on this seller invoice—they **reduce** the payout (withhold more from the seller) — [how to add](seller-auction-expenses.md) |
| **Extra lot charges** | Additional deductions on a **specific lot** you add when editing — [how to add](seller-lot-expenses.md) |
| **Subtotal / total** | Net lot total after auction charges and extras |
| **Adjustment** | One discount or surcharge for the whole seller invoice |
| **Grand total** | Amount due **to the seller** after adjustment (before you mark payouts / receipts) |

At generation, **grand total** equals the **lot net total** until you add auction fees or an adjustment.

---

## Sliding scale commission

If the lot uses **Sliding Scale Commission**, the rate depends on the **hammer tier** (higher hammers can use a different percentage). The system picks the tier from the commission formula configured on the lot.

---

## Example (one lot)

| Item | Rate / amount | On $1,000 hammer |
|------|---------------|------------------|
| Hammer | — | $1,000.00 |
| Commission | 15% | −$150.00 |
| Seller tax | 5% (if applicable) | −$50.00 |
| Seller lot expense | $25 fixed | −$25.00 |
| **Net to seller** | | **$775.00** |

If the same seller had two sold lots with the same structure, the invoice **lot subtotal** is the sum of both nets before auction-level items.

---

## Changes after the invoice exists

| Action | Effect on seller payout |
|--------|-------------------------|
| **Edit clerking** | Lot lines rebuild from updated hammer / sold status |
| **Edit settlement** — commission or seller tax | Recalculates that lot |
| **Add auction charge** | **Lowers** payout (more withheld) |
| **Add extra lot charge** | **Lowers** that lot and the invoice |
| **Adjustment — surcharge** | **Lowers** grand total (less paid to seller) |
| **Adjustment — discount** | **Raises** grand total (more paid to seller) |
| **Payment / receipt** | Tracks what you paid the seller; edits may block when marked paid |

---

## Seller vs buyer on the same lot

| | Buyer pays | Seller receives (net) |
|---|------------|------------------------|
| Direction | Hammer **plus** buyer premium/tax | Hammer **minus** commission/tax/expenses |
| Same hammer | Buyer total is usually **higher** than hammer | Seller total is **lower** than hammer |

Both invoices are created together when you [generate settlement](generate-settlement.md). Review **Bidder** vs **Seller** toggles on the **Settlement** tab ([auction dashboard](auction-dashboard.md#settlement-tab)).

---

## Related

- [Edit settlement](edit-settlement.md) · [Settlement adjustments](settlement-adjustments.md) · [Settlement payment](settlement-payment.md)

- [Buyer settlement calculation](buyer-settlement-calculation.md)
- [Generate settlement](generate-settlement.md)
- Dev detail: [Seller settlement calculation](../../auction/settlement/seller-calculation.md) · [Settlement fields](../../auction/settlement/fields.md)
