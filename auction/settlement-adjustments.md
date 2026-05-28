[Auction](./index.md) · [Auction Journal](../index.md)

# How do adjustments work in settlement?

An **adjustment** is a **single** discount or surcharge on a **whole** buyer or seller invoice. It changes the **grand total** (what the buyer should pay or what you owe the seller) without changing individual lot hammer lines. Use it for goodwill credits, late fees, or other one-off invoice-level amounts—not for per-lot fees (those are **extra lot charges** or **auction charges** on the settlement).

**Prerequisite:** [Generate settlement](generate-settlement.md) · **Other edits:** [Edit settlement](edit-settlement.md)

---

## Setup (once per account)

Adjustments use accounts under **`6000 : Adjustments`** in **Miscellaneous → Account**:

1. Expand **6000 : Adjustments**.
2. **Add** a sub-account with a clear description.
3. Set **Used For** to **Discounts** or **Surcharges** (required for this parent).

See [Miscellaneous accounts](../auctioneer-misc/account.md) for the full Account workflow.

| **Used For** | Typical use |
|--------------|-------------|
| **Discounts** | Credit that **reduces** what a buyer owes or **increases** what you pay a seller |
| **Surcharges** | Fee that **increases** what a buyer owes or **reduces** what you pay a seller |

---

## How to add an adjustment on an invoice

1. Open the auction **Settlement** tab and open the **buyer** or **seller** invoice.
2. Find the **adjustment** section (one line allowed per invoice).
3. Choose the **Adjustments** account you created, enter a **description**, and pick **Fixed** or **Percentage**:
   - **Fixed** — dollar amount you enter.
   - **Percentage** — percent of the invoice **subtotal** (`total` before adjustment), not of each lot separately.
4. Save.

The **grand total** updates. **Subtotal** (lot + auction charges) stays the same; only **grand total** includes the adjustment.

You can **change** the adjustment by saving again (replaces the previous one) or **remove** it to restore grand total to the subtotal.

---

## How the amount affects buyer vs seller

| Invoice | Account type | Effect |
|---------|--------------|--------|
| **Buyer** | **Surcharge** | Buyer pays **more** |
| **Buyer** | **Discount** | Buyer pays **less** |
| **Seller** | **Surcharge** | Seller is paid **less** (more withheld) |
| **Seller** | **Discount** | Seller is paid **more** (credit to seller) |

### Examples (buyer subtotal $1,000 before adjustment)

| Adjustment | Type | Grand total |
|------------|------|-------------|
| $50 fixed | Surcharge | $1,050 |
| $50 fixed | Discount | $950 |
| 10% | Surcharge (10% of $1,000) | $1,100 |
| 10% | Discount | $900 |

---

## Limits and rules

| Rule | Detail |
|------|--------|
| **One per invoice** | Only one adjustment block; a new save replaces the old one. |
| **Not after paid** | Cannot add or remove adjustments when the settlement is **Paid**. |
| **Cannot exceed balance** | A discount cannot make **grand total** less than what you have already recorded as **paid** on that invoice (you will see an error if the adjustment is too large). |
| **Shows on PDF** | Adjustment account, description, and amount appear on settlement PDF and emailed invoice. |

---

## Adjustments vs other settlement edits

| Tool | Scope | Examples |
|------|--------|----------|
| **Auction charge** | Whole invoice, misc account | Delivery fee, admin fee |
| **Extra lot charge** | One lot | Per-lot handling |
| **Lot formula edit** | One lot | Different buyer premium % on a line |
| **Adjustment** | Whole invoice, **Discounts / Surcharges** account only | $100 goodwill credit, 5% late surcharge |

---

## Related

- [Edit settlement](edit-settlement.md)
- [Buyer settlement calculation](buyer-settlement-calculation.md) — **Grand total** row
- [Seller settlement calculation](seller-settlement-calculation.md)
- Dev: [Settlement adjustments](../../auction/settlement/adjustments.md)
