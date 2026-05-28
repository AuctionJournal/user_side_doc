[Auction](./index.md) · [Auction Journal](../index.md)

# How does clerking work in an auction?

**Clerking** is how you record the **final result** of each lot after bidding: **Sold** (with hammer price and buyer), **Pass**, **Hold**, or **High Bid** (absentee auctions). Those results decide who appears on **buyer invoices** and **seller statements** when you [generate settlement](generate-settlement.md).

Quick status-only reference: [What are the types of clerk status?](clerking-status-types.md).

---

## Why clerking matters

| Without clerking | With clerking |
|------------------|---------------|
| The system only knows bid activity | You have an official **sold / not sold** outcome per lot |
| Settlement cannot bill correctly | **Sold** lots flow into invoices with the right hammer and buyer |

---

## When clerking happens

| Phase | What happens |
|-------|----------------|
| **During onsite live webcast** | You often clerk each lot **in the ring** as it sells (live clerking screen). |
| **When the auction closes** | For lots with **no** status yet, Auction Journal may set defaults (**Sold**, **Pass**, or **High Bid** for absentee) from bids vs **reserve**. Lots you already clerked are **not** overwritten. |
| **Auction Day (your review)** | You open the **clerking** list to fix hammer, buyer, or status before settlement. |

Details on automatic close steps: [What happens automatically when an auction closes?](after-auction-closes.md).

---

## Open the clerking list (Auction Day)

1. Go to **Auctions** in the Auctioneer Dashboard.
2. Open **Dashboard** for the auction (after publish).
3. Go to **Auction Day** / clerking for that sale — URL pattern: `/dashboard/auctions/{auctionId}/clerking`.

You can also use **Auction Day** from the top bar when you are already in clerking-related flows.

### What you see

| Column / control | Meaning |
|------------------|---------|
| **Lot No., Title, Seller** | Identity of the lot |
| **Reserves** | Reserve amount |
| **Price Realised** | Hammer / winning bid amount on the lot |
| **Bidder#** | Winning bidder or floor buyer (bid card when applicable) |
| **Status** | **Sold**, **Pass**, **Hold**, or **High Bid** |
| **Search / Sort / Filter** | Find lots; filter by status |
| **Edit** (pencil) | Change hammer, buyer, or status — [Edit clerking](edit-clerking.md) |
| **View** (eye) | **Clerk logs** — history of changes |

If a bid was changed in clerking, a tooltip notes that the auctioneer updated it.

---

## Clerk statuses explained

| Status | Meaning | Settlement |
|--------|---------|------------|
| **Sold** | Lot sold to the listed buyer at the hammer shown | Counts toward buyer/seller invoices |
| **Pass** | Lot did not sell | Not invoiced |
| **Hold** | Outcome not final | **Blocks** **Generate Invoice** until you pass, sell, or confirm ignoring holds |
| **High Bid** | Absentee-style high bid (not the same as **Sold**) | Use absentee **Result** / CSV flows; not standard sold invoicing |

Only lots in **Sold** status with a valid buyer are included when you [generate settlement](generate-settlement.md).

---

## Typical workflow

1. Confirm the auction is **Closed** on the dashboard.
2. Open **Auction Day** clerking and review every lot (especially any auto **Sold** or **Pass** you disagree with).
3. Resolve **Hold** lots before generating invoices.
4. [Generate settlement](generate-settlement.md) once clerking is correct.
5. [Collect payments](settlement-payment.md) after invoices exist.

You can still [edit clerking](edit-clerking.md) after invoices exist **until** payment has started on the affected buyer’s settlement.

---

## Onsite live webcast

During the sale, clerking in the **live ring** is the main path. After close, the **Auction Day** list fills in any lots that never received a status. See [How does Ring work?](rings.md).

---

## Related

- [Edit clerking](edit-clerking.md)
- [After the auction closes](after-auction-closes.md)
- [Generate settlement](generate-settlement.md)
- [Auction Dashboard](auction-dashboard.md)
- Dev: [Clerking](../../auction/clerking/index.md) · [How it works (implementation)](../../auction/clerking/how-it-works.md)
