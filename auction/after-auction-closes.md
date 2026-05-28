[Auction](./index.md) · [Auction Journal](../index.md)

# What happens automatically when an auction closes?

When an auction reaches **Closed**, bidding stops for bidders and your work shifts to **clerking**, **settlement**, and **payments**. Some steps run **automatically** on the platform; others need you to start them from the **Auction Dashboard**.

For the full stage journey (Draft → Live → Closed), see [What are the different stages of an auction?](auction-stages.md).

---

## When does an auction become Closed?

| Auction type | Typical close trigger |
|--------------|----------------------|
| **Online** (Timed, Absolute, Absentee) | **End date** passes after the bidding window (including **soft close** if you use it). |
| **Onsite With Live Webcast** | **End date** passes, or all **bidding days** and **rings** are finished for the sale. |

On the **Auctioneer Dashboard**, the auction status shows **Closed**. Bidders no longer see the sale as an active bidding event on the public site.

---

## What the platform does automatically

These steps run without you clicking a “close auction” button for each item (the system ends the sale on schedule or when onsite days are complete).

### 1. Auction marked closed

- The auction **status** is set to **Closed**.
- Active-sale **caches** are cleared so catalog and live views stop treating the auction as open.

### 2. Default clerking on lots (where you have not decided yet)

For lots that still have **no clerk outcome**, the platform applies **default** results based on bids and **reserve**:

| Situation | Typical automatic outcome |
|-----------|---------------------------|
| Visible lot, **bid at or above reserve**, no clerk status yet | **Sold** (online timed / absolute style) |
| Hidden lot, **no bid**, or bid **below reserve**, no clerk status yet | **Pass** |
| **Absentee Bidding** auction, eligible high bid, no clerk status yet | **High Bid** (not “Sold”) instead of the normal sold default |

**Important:** Lots you already clerked during **live** rings or in the clerk UI **keep** your decision—the automatic step does **not** overwrite existing **Sold**, **Pass**, **Hold**, or similar statuses.

**Onsite live webcast** sales often have clerk results **during** the ring; after close, defaults mainly fill gaps on lots that never got a status.

### 3. Lots flagged as auction closed

Affected lots are marked so post-close tools (clerking review, settlement) treat the sale as finished.

---

## What you still do manually

Automatic clerking is a **starting point**. Settlement and money movement wait on you.

| Step | Who acts | What happens |
|------|----------|--------------|
| **Review / edit clerking** | Auctioneer | Open **Auction Day** clerking — [How clerking works](clerking.md) · [Edit clerking](edit-clerking.md). Fix hammer, buyer, **Sold** / **Pass** / **Hold** if defaults are wrong. |
| **Generate settlement** | Auctioneer | Run **generate settlement** **once** per auction when clerking is ready. Not auto-created the instant the clock hits end date. |
| **Buyer invoices & seller statements** | System after you generate | Built from sold lots, premiums, taxes, and auction charges. See [How is a settlement generated?](generate-settlement.md), [Buyer calculation](buyer-settlement-calculation.md), [Seller calculation](seller-settlement-calculation.md). |
| **Collect buyer payments / pay sellers** | Auctioneer + bidders | After settlements exist—cards, receipts, and payout rules depend on your [Stripe Connect](../auctioneeer/stripe-connect.md) and payment setup. |

### Settlement gates (before Generate works)

- Auction is **published** and **closed** for the sale.
- **End date** has passed (onsite may also require **all rings** closed).
- Settlement was **not** already generated for this auction.
- If any lot is still **Hold**, generation is **blocked** until you resolve holds or choose to **ignore** hold lots (product may move ignored holds to **Pass**).

---

## What bidders see after close

- They **cannot place new bids** on that auction.
- **Registration** for that sale is no longer offered after the registration window ends.
- Invoices and payment requests come **after** you generate settlement and the payment flow runs—not at the exact second the auction closes.

---

## Quick checklist for auctioneers

1. Confirm status is **Closed** on the dashboard.
2. Review **clerking** on every lot — [Clerking](clerking.md) (especially any auto **Sold** / **Pass** / **High Bid** you disagree with).
3. Resolve **Hold** lots if settlement is blocked.
4. **Generate settlement** once.
5. Send or collect **payments** and track paid status.

---

## Related

- [Auction stages](auction-stages.md) — labels from Draft through Closed
- [Generate settlement](generate-settlement.md)
- [Registration acceptance](registration-acceptance.md) — while the sale was open
- [Auction Dashboard](auction-dashboard.md)
- Dev mirror: [After the auction closes](../../auction/post-close.md)
