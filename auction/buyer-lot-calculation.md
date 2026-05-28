[Auction](./index.md) · [Auction Journal](../index.md)

# How is each won lot calculated on a buyer invoice?

Last modified: 2026-05-27

When you **generate buyer settlement** for an auction, every **sold lot a winning bidder won** becomes **one line** on that buyer’s invoice. Each line is built from the **hammer** (winning bid) plus **buyer’s premium** and sometimes **buyer tax**. This page explains **one lot at a time**; for auction-wide fees, adjustments, and payment, see [Full buyer settlement calculation](buyer-settlement-calculation.md).

**Prerequisite:** [How is a settlement generated for an auction?](generate-settlement.md).

---

## Which lots get a line on the buyer invoice

The system only adds a line when the lot is clerked **Sold** and the registration is the recorded winner for that auction type:

| Buyer type | Lots on that buyer’s invoice |
|------------|------------------------------|
| **Floor bidder** (onsite live) | Sold lots where they are the **floor** winner |
| **Internet bidder** (onsite live) | Sold lots they won in the **live** session |
| **Online timed / absolute** | Sold lots where they are the **lot winner** |

Lots are listed in **lot number** order on the invoice.

---

## Each lot line — three parts

| Part | What it is |
|------|------------|
| **Hammer** | Your winning bid amount for that lot (from clerking / the sold lot record) |
| **Buyer’s premium** | A **percentage of the hammer** (not a flat fee unless your setup uses a 0% formula) |
| **Buyer tax** | Only when the auction **collects taxes** and you (as the auctioneer’s customer) are marked **taxable** — also a **percentage of the hammer** |

**Per-lot total (at generation):**

```text
Hammer + Buyer’s premium + Buyer tax (if applicable)
```

Example on a **$500** hammer with **10%** premium and **7%** tax:

| Item | Amount |
|------|--------|
| Hammer | $500.00 |
| Buyer’s premium (10%) | $50.00 |
| Buyer tax (7%) | $35.00 |
| **Lot total** | **$585.00** |

If the same buyer won **two** lots with the same rates, the invoice **lot subtotal** is **$1,170.00** before any auction-level charges or adjustments.

---

## Where the rates come from

| Setting | Effect on your lot line |
|---------|-------------------------|
| Customer uses the **default** buyer premium | Rate comes from the **lot** setup |
| Customer has a **custom** buyer premium | Rate comes from the **customer** record |
| Auction does not collect taxes | No buyer tax on the line |
| Customer is not marked **taxable** | No buyer tax even if the auction collects taxes |
| Tax applies | Tax rate comes from the **lot** buyer tax formula |

Premium and tax percentages both apply to the **hammer only**, not to hammer plus premium.

---

## What is not on the lot line at first

These are added later on the **whole invoice** or on a **specific lot** when the auctioneer edits settlement:

| Item | Where it lives |
|------|----------------|
| **Auction-level charges** (delivery, admin fee, etc.) | Invoice section — not per lot at generation |
| **Extra lot charges** | Added to that lot when editing settlement |
| **Invoice adjustment** (discount or surcharge) | One line for the entire invoice |

See [Edit settlement](edit-settlement.md) and [Full buyer settlement calculation](buyer-settlement-calculation.md).

---

## If clerking changes after the invoice exists

Changing **sold/pass**, **winner**, or **hammer** in clerking updates or moves lot lines on the buyer settlement (when payment rules allow). The same hammer + premium + tax rules are used to rebuild a line when needed.

---

## Related

- [Full buyer settlement calculation](buyer-settlement-calculation.md)
- [Generate settlement](generate-settlement.md)
- [How does clerking work?](clerking.md)
- Dev detail: [Buyer per-lot calculation](../../auction/settlement/buyer-lot-calculation.md)
