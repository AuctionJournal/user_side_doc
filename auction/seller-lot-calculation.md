[Auction](./index.md) · [Auction Journal](../index.md)

# How is each sold lot calculated on a seller invoice?

Last modified: 2026-05-27

Each **Sold** lot for a seller is calculated separately, then all lot nets are added to form the seller invoice total. This page explains one lot line only.

Prerequisite: [How is a settlement generated for an auction?](generate-settlement.md).

---

## Per-lot formula

For each sold lot:

```text
Seller lot net = Hammer - Commission - Seller tax (if applicable) - Seller lot expenses
```

Where:

- **Hammer** = winning bid on that lot
- **Commission** = lot commission formula (regular or sliding scale)
- **Seller tax** applies only when:
  - auction is set to collect taxes, and
  - lot/seller is marked taxable
- **Seller lot expenses** = fixed expense lines configured on that lot

This is opposite of buyer lots: seller math is net payout after deductions.

---

## Line items on one lot

| Line item | Meaning |
|-----------|---------|
| Hammer | Winning bid amount |
| Commission | Percentage withheld from hammer |
| Seller tax | Percentage withheld from hammer (if tax applies) |
| Seller lot expenses | Fixed deductions for that lot |
| Lot total | Net amount due to seller for that lot |

---

## Sliding scale commission

If the lot uses **Sliding Scale Commission**, the system picks the commission tier based on the lot hammer amount and uses that tier's percentage.

---

## Example (one lot)

| Item | Rate/amount | On $1,000 hammer |
|------|-------------|------------------|
| Hammer | — | $1,000.00 |
| Commission | 15% | -$150.00 |
| Seller tax | 5% | -$50.00 |
| Seller lot expense | $25 fixed | -$25.00 |
| **Net to seller (lot total)** | | **$775.00** |

If the seller has multiple sold lots, invoice lot total is the sum of each lot's net.

---

## What changes after generation

- **Edit clerking** can change sold status, winner, or hammer, which updates settlement lot lines.
- **Edit settlement** can further change charges/adjustments at lot or invoice level.
- Once marked paid in settlement workflow, some edits are blocked.

---

## Related

- [Seller settlement calculation (full invoice)](seller-settlement-calculation.md)
- [Edit settlement](edit-settlement.md)
- [Settlement adjustments](settlement-adjustments.md)
- Dev detail: [Seller per-lot calculation](../../auction/settlement/seller-lot-calculation.md)
