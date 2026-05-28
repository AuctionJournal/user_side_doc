[Auction](./index.md) · [Auction Journal](../index.md)

# How to make preceding bidding as winning bidder? How does it works?

Last modified: 2026-05-28

Use this action when you want the lot winner to be changed to the latest accepted previous bidder for that lot.

---

## Where to use it

1. Open **Auction Day** clerking.
2. Open **Edit** for the lot.
3. Select **Make precedence bid the winning bidder**.

---

## What it does

When allowed, the system:

- finds the latest accepted bid from another bidder (not current winner)
- sets lot to **Sold**
- sets hammer to that bid amount
- sets that bidder as winner
- records a clerk log reason automatically

If settlement is already generated, related settlement lines are updated in background.

---

## When this option is not available

- Auction is not closed yet
- No suitable accepted previous bidder is found
- Onsite With Live Webcast lot already has live webcast clerking data
- Payment has already started on affected settlement(s)

---

## Tip

Review settlement totals after this change if invoices were already generated.

---

## Related

- [How can an auctioneer edit clerking?](edit-clerking.md)
- [How does clerking work in an auction?](clerking.md)
- [What are the types of clerk status?](clerking-status-types.md)
- Dev: [Precedence bidder winner](../../auction/clerking/precedence-bidder-winner.md)

