[Auction Lot](./index.md) · [Auction Journal](../index.md)

# Explain each auction lot field

Last modified: 2026-05-29

A **lot** is one sellable item (or line) in your auction catalog. This page explains **lot-level** fields in the **Auctioneer Dashboard** and what bidders see on Auction Journal. For **auction-level** fields, see [Explain each auction field](../auction/fields.md).

Step-by-step: [Create a lot](create-lot.md) · [Edit a lot](edit-lot.md).

---

## Where lot fields appear

| Area | What you set or see |
|------|---------------------|
| **New Lot** / **Edit Lot** | Catalog, value, media, bidding time (online), accounting |
| **Lots** tab list | Lot number, title, status, auction ready, actions (hide, featured, etc.) |
| **Import / Lot AI / QR tools** | Same fields, filled in bulk or from files |
| **Live ring** (onsite) | Hammer, clerk status, floor bidder — during live bidding |
| **Public catalog** | Title, images, current bid, close time — what bidders see |

---

## Lot Info (create and edit)

| Field | What it is | Notes |
|-------|------------|--------|
| **Lot number** | Your lot ID in this auction | Must be **unique** per auction; set at create; **read-only** on edit |
| **Sale order** | Order lots run in the sale (catalog / soft-close order) | Must be unique; locks in later auction stages on some types |
| **Quantity** | How many of this line (often `1`) | |
| **Seller** | Consignor / customer for this lot | From your **Customers** list; may drive commission and seller tax |
| **Title** | Short name on the catalog and invoices | Required for a complete lot |
| **Category** | Lot category (equipment type, etc.) | Required for a complete lot — [lot categories](lot-categories.md) |
| **Category detail** | Optional extra category notes | |
| **Description** | Full lot description for bidders | Required for a complete lot |

---

## Lot Value

| Field | What it is | Notes |
|-------|------------|--------|
| **Selected value range (min / max)** | Optional estimate range for bidders | If you enter one, enter both; max must be greater than min |
| **Reserve** | Minimum price to sell (where your auction type uses reserve) | Hidden for **Online Absolute**; can inherit from auction **New Lot Default** |
| **Start bid** | Opening bid level | From **bid increment** schedule on create; **required** for **non-catalogued** onsite; may lock after publish |

---

## Lot Media

| Field | What it is | Notes |
|-------|------------|--------|
| **Lot images** | Photos in the lot gallery | Upload on create or in **Edit Lot**; [import images in bulk](import-lot-images.md) |
| **Featured** (list / options) | Highlight lot in catalog when enabled | Optional promotion on the lot row or options |

---

## Lot Bidding Time (online timed / online absolute only)

Per-lot overrides of auction soft-close behavior. **Not shown** for **Onsite With Live Webcast**.

| Field | What it is | Notes |
|-------|------------|--------|
| **Soft close seconds** | Time added in the stagger before **this** lot closes | Usually copied from auction at create; can override — [soft close](../auction/soft-close.md) |
| **Bid soft closed seconds** | Extra time when someone bids on this lot during soft close | |

**Close bidding** (per lot) is set by the system from the auction schedule at publish—not a field you type on each lot.

---

## Lot Accounting (most auction types)

Fees and taxes for settlement. Hidden for **Absentee Bidding** in the edit form.

| Field | What it is | Notes |
|-------|------------|--------|
| **Commission** | Seller commission formula | Often from auction default or seller’s consigner settings |
| **Seller tax** | Tax formula on seller side | |
| **Is seller taxable** | Whether seller tax applies on this lot | Follows seller / auction tax rules |
| **Buyer’s premium** | Buyer premium formula | Usually from auction default |
| **Buyer tax** | Buyer tax formula | When auction collects taxes |
| **Buyer lot charge 1 / 2** | Extra buyer charge formulas | When configured on your account |
| **Seller lot expenses** | Extra seller charges on this line | **+ ADD** rows: account, description, amount |
| **Sales person** | Name for reporting | Optional |
| **Sales person commission** | Related commission text | Optional |

Changing **seller** can refresh commission and seller tax from that customer’s profile.

Defaults: [New Lot Default](../auction/build-details.md#new-lot-default) · [Default settings for all lots](../auction/default-lot-settings.md).

---

## Shipping (lot level)

| Field | What it is | Notes |
|-------|------------|--------|
| **Shipping** (per lot) | Whether this lot can ship when auction allows **specific** shipping | Auction **Details → Shipping** sets auction-wide rules — [shipping](../auction/shipping.md) |

---

## Lots list and lifecycle flags

What you see on the **Lots** tab or in tools—not always separate form fields.

| What you see | Meaning |
|--------------|---------|
| **Auction ready** | Required catalog fields are complete; lot counts toward **publish** on catalogued auctions |
| **Incomplete** | Missing required data; finish in **Edit Lot** or import |
| **Hidden** | Lot hidden from public catalog until you show it |
| **QR only** | Placeholder from **Generate QR**; replace with a full lot or removed at publish — [QR lots](qr-lots.md) |
| **Instant / created on the fly** | Lot created during **non-catalogued** live bidding — [instant lot](instant-lot-live.md) |
| **Lot closed** | This lot’s bidding window has ended |
| **Auction closed** (on lot) | Parent auction has ended; lot is in post-close workflow |

---

## Bidding state (runtime — mostly system-set)

Updated by bids and live sessions. You usually **view** these; auctioneer bid tools may adjust some values.

| What bidders / you see | Meaning |
|------------------------|---------|
| **Current bid** | Highest accepted bid amount on the lot |
| **Next bid** | Minimum amount for the next bid step |
| **Bid count** | Number of bids |
| **Lot winner** | Winning bidder after bidding / clerking |
| **Winning floor bidder** | Floor customer recorded as winner (onsite) |
| **Winner bid card number** | Bidder card # for the winner |
| **Highest maximum bid** | Top max bid amount (max-bidding auctions) |
| **View count / watchlist count** | Engagement stats on the public catalog |

To change a bid as auctioneer, see [edit a bidder’s bid](bidding.md#how-can-an-auctioneer-edit-a-bidders-bid).

---

## Clerking fields (onsite and after bidding)

Set during **live rings** or in **clerking** after the sale.

| Value / field | Meaning |
|---------------|---------|
| **Clerk status** | **Sold**, **Pass**, **Hold**, **High Bid** (absentee), or not set yet — [clerk status types](../auction/clerking-status-types.md) |
| **Clerk updated** | A clerk decision was saved on this lot |

---

## Live webcast (onsite)

| What it means | When |
|---------------|------|
| **Live in ring** | Lot is the active lot in a live webcast session; catalog bidding on that lot is blocked |
| **Ring / session** | Tied to the auction’s live webcast for that ring — [live bidding](../auction/live-bidding.md) |

---

## Fields by how the lot was created

| Source | Typical fields you fill |
|--------|-------------------------|
| **New Lot** | All sections in the dialog |
| **Import lots** | Columns map to lot number, title, category, etc. — [import lots](import-lots.md) |
| **Lot AI / fast catalog** | Title, description, category from AI; you review — [Lot AI](lot-ai.md) |
| **Generate QR** | Placeholder only until you replace — [QR lots](qr-lots.md) |
| **Instant lot (live)** | Minimal fields at hammer; complete later in **Edit Lot** |

Overview: [ways to create lots](lot-creation-ways.md).

---

## Related

- [Create a lot](create-lot.md)
- [Edit a lot](edit-lot.md)
- [Lot categories](lot-categories.md)
- [Online lot bidding](bidding.md)
- [Explain each auction field](../auction/fields.md)
- Developer reference: [Auction lot fields](../../auction-lot/fields.md)
