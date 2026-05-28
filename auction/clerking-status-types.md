[Auction](./index.md) · [Auction Journal](../index.md)

# What are the types of clerk status?

Last modified: 2026-05-28

For normal auction clerking, lot status is mainly:
- **Sold**
- **Pass**

For **Online Absolute Auction**, lot status can also be:
- **Hold**

---

## Meaning of each status

| Status | Meaning |
|---|---|
| **Sold** | Lot is sold and moves toward settlement/invoice flow |
| **Pass** | Lot is not sold |
| **Hold** (Online Absolute use-case) | Lot result is kept pending for review/action |

---

## How status is set by auction type

### 1) Non-Onsite-With-Live-Webcast auctions

After auction closes, lots without clerk status are auto-clerked by system (backend `lotsClerkingAfterAuctionEnd`):
- **Sold** when bid/reserve conditions are met
- **Pass** otherwise

You can still edit clerking later if needed.

### 2) Onsite With Live Webcast

Lots are clerked live during auction flow (typically **Sold** or **Pass**) by auctioneer/team as bidding happens.

So this type relies on live clerking decisions during sale, not only post-close auto result assignment.

---

## Practical note

Before generating settlement, review clerking statuses and correct any lot where final outcome should differ.

---

## Related

- [How does clerking work in an auction?](clerking.md)
- [How can an auctioneer edit clerking?](edit-clerking.md)
- [What happens automatically when an auction closes?](after-auction-closes.md)

