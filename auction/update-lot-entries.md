[Auction](./index.md) · [Auction Journal](../index.md)

# How to update lot entries in settlement

Last modified: 2026-05-27

Use **Update Entries** when you need to change formula selections on a single settlement lot line:
- **Buyer invoice:** Buyer Premium / Buyer Tax
- **Seller invoice:** Commission / Seller Tax

This updates calculation entries for that lot line. It does **not** change hammer, sold/pass, or winner (those are clerking changes).

---

## Where to open Update Entries

1. Open **Auctions** → **Dashboard** → **Settlement**.
2. Choose **Bidder** (buyer) or **Seller**.
3. Open the settlement record.
4. On the lot row, select **Update Entries**.

The popup fields depend on settlement type.

---

## Buyer lot entries (Update Entries)

Buyer modal fields:
- **Buyer Premium**
- **Buyer Tax** (if applicable for that lot)

![Update Entries — buyer premium and buyer tax](../image/auction/update-entries-buyer-modal.png "Update Entries (Buyer)")

After save, the lot line recalculates from that lot's hammer:
- buyer premium amount
- buyer tax amount
- lot total
- invoice totals

If the selected rates are higher, buyer amount due increases; if lower, it decreases.

---

## Seller lot entries (Update Entries)

Seller modal fields:
- **Commission**
- **Seller Tax** (if applicable for that lot)

![Update Entries — seller commission and seller tax](../image/auction/update-entries-seller-modal.png "Update Entries (Seller)")

After save, the lot line recalculates from that lot's hammer:
- commission amount
- seller tax amount
- lot net
- seller payout totals

Higher commission/tax lowers seller payout; lower commission/tax raises payout.

---

## What changes and what does not

| Changes | Does not change |
|---------|------------------|
| Premium/tax/commission formula entries on that lot line | Hammer amount |
| Lot line total and settlement totals | Sold/pass status |
| Grand total (after existing adjustment is applied) | Lot winner/bidder assignment |

For hammer/winner/status corrections, use clerking.

---

## Related

- [Edit settlement](edit-settlement.md)
- [Buyer settlement calculation](buyer-settlement-calculation.md)
- [Seller settlement calculation](seller-settlement-calculation.md)
- [Buyer lot expenses](buyer-lot-expenses.md) · [Seller lot expenses](seller-lot-expenses.md)
- Dev: [Update lot entries](../../auction/settlement/update-lot-entries.md)

