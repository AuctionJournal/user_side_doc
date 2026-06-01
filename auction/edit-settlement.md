[Auction](./index.md) · [Auction Journal](../index.md)

# How can an auctioneer edit a settlement?

After you **generate invoices** for an auction, you can correct billing on individual **buyer** or **seller** settlements without running **Generate Invoice** again. Use **clerking** when hammer price, sold/pass status, or the winning buyer should change; use **settlement edit** for fees, formulas on a line, and extra charges you add on the invoice.

**Prerequisite:** [How is a settlement generated for an auction?](generate-settlement.md)

---

## Where to edit

1. Open **Auctions** → **Dashboard** for the auction.
2. Go to the **Settlement** tab ([Settlement tab](auction-dashboard.md#settlement-tab)).
3. Choose **Bidder** or **Seller** to list invoices for that auction.
4. Open the buyer or seller you need (invoice / settlement detail).

You cannot edit a settlement that is already marked **Paid**—the system blocks changes after payment is completed on that document.

---

## What you can change

### Auction-level charges

Fees that apply to the **whole invoice** (not one lot), such as delivery or an admin fee.

| On a **buyer** invoice | On a **seller** invoice |
|------------------------|-------------------------|
| **Increases** what the buyer owes | **Reduces** what you pay the seller (more withheld) |

For each charge you pick a **misc account**, enter a **description**, and choose **Fixed** (dollar amount) or **Percentage** (stored as the charge value you enter). You can **add**, **edit**, or **remove** auction charges until the invoice is paid.

**Buyer auction charges (step-by-step):** [What are buyer auction charges? How do I add them?](buyer-auction-charges.md)

**Seller auction expenses (step-by-step):** [What are seller auction expenses? How do I add them?](seller-auction-expenses.md)

### Per-lot lines (formulas)

On each sold lot line you can change which **formula** applies (not the hammer—that comes from clerking):

| Invoice type | What you can change on the line |
|--------------|--------------------------------|
| **Buyer** | Buyer’s premium, buyer tax |
| **Seller** | Commission, seller tax |

The system recalculates that lot’s premium, tax, or commission from the **hammer on the line** and updates the invoice subtotal.

**Step-by-step:** [How to update lot entries in settlement](update-lot-entries.md)

### Extra lot charges

Additional fees on **one lot** (buyer) or deductions on **one lot** (seller):

- Pick an account and description.
- **Fixed** amount, or **Percentage** of that lot’s hammer.
- **Add**, **edit**, or **remove** extras on a lot until paid.

**Step-by-step:** [Buyer lot expenses](buyer-lot-expenses.md) · [Seller lot expenses](seller-lot-expenses.md).

Seller expenses on the lot at build time are included at generation; you can add more on settlement edit for that lot.

---

## What you should not use settlement edit for

| Situation | Use instead |
|-----------|-------------|
| Wrong hammer, lot not sold, wrong buyer | **Clerking** — settlement lot lines rebuild from clerking ([After you generate](generate-settlement.md#after-you-generate)) |
| One discount or surcharge for the **entire** invoice | **Adjustment** — see [What if an auctioneer wants to do some adjustments in settlement?](settlement-adjustments.md) |
| First-time invoices | **Generate Invoice** on the Settlement tab |

---

## Buyer vs seller (direction of money)

| Edit | Buyer invoice | Seller invoice |
|------|---------------|----------------|
| Add auction charge | Buyer owes more | Seller receives less |
| Add extra lot charge | Buyer owes more | Seller receives less |
| Change premium / tax / commission | Recalculates that lot | Recalculates that lot |

**Grand total** on the screen includes any **adjustment** you added separately ([settlement adjustments](settlement-adjustments.md)).

---

## After you save

- Totals on the Settlement tab and on **PDF / email invoice** reflect your changes.
- If you also change **clerking**, lot lines may update again asynchronously—refresh the settlement view if amounts look stale.
- Recording **payment** can lock the invoice; finish edits before marking **Paid**.

---

## Related

- [Buyer settlement calculation](buyer-settlement-calculation.md)
- [Seller settlement calculation](seller-settlement-calculation.md)
- [Adjustments in settlement — how they work](settlement-adjustments.md)
- [Settlement payment](settlement-payment.md)
- [Miscellaneous accounts — Adjustments parent](../auctioneer-misc/account.md)
- Dev: [Edit settlement](../../auction/settlement/edit.md) · [Settlement hub](../../auction/settlement/index.md)
