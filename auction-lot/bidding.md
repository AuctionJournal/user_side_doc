[Auction Lot](./index.md) · [Auction Journal](../index.md)

# Online bidding on auction lots

These answers cover **timed / catalog bidding** on the public site and **Auctioneer Dashboard** moderation. **Live ring bidding** during an onsite webcast is a separate flow — see [sample questions](../sample_questions.md) under **Auction Live Bidding** when documented.

---

## How bid increments work?

A **bid increment ladder** is a schedule your auction uses to decide how much each bid must go up. You set it when you **build the auction** (threshold prices and step sizes). Bidders do not type arbitrary amounts on the standard catalog screen.

### What bidders see

- On each open lot, the button shows **bid $X**, where **X** is the **next required bid** for that lot right now.
- That amount comes from the ladder and the **current high bid** (or the lot **start bid** if nobody has bid yet).
- On the **auction** or **lot detail** page, the **Bid Increments** section lists your ladder (for example: below $100, bids go up $5; below $500, bids go up $10). It is **informational** — bidders still place bids using the **bid $X** button.

### Flat vs maximum auctions

- **Flat bidding:** Each click raises the price by exactly one step on the ladder (the amount shown on the button).
- **Maximum bidding:** Bidders can still take the one-step **bid now** amount, or enter a **maximum** (ceiling). The system may advance the visible price in ladder steps automatically when two max bidders compete.

### For auctioneers

Configure increments in the auction **build** before the sale goes live. If bidders report “amount changed” or cannot bid the number they expected, the **next bid** on the lot likely moved because someone else bid first — they should refresh the page.

---

## How does bidding work?

### Before you bid

1. **Register** for the auction on Auction Journal and wait until your registration is **approved** (or permanently approved) for bidding.
2. Open the **catalog** while the lot is **open** (after the auction’s bidding start and before that lot’s close time).
3. The lot must be **visible** in the catalog (not hidden by the auctioneer).

See [How do I register for an auction?](../bidder/register-for-auction.md).

### Placing a bid

1. Find the lot in the **catalog** or open its **detail** page.
2. Click **bid $X** (X is the next required amount).
3. If you are not signed in, log in as a **bidder**.
4. In the confirmation window:
   - **Flat-only auction:** Confirm the bid at the shown amount.
   - **Maximum-bidding auction:** You can **bid now** at the shown amount **or** enter a **maximum bid** (your ceiling). Use whole dollars only.
5. Complete any **identity verification** prompt if the site asks for it.

### After you bid

- If you are **winning**, the lot shows you as high bidder at the current amount; the **next bid** button shows what the next challenger must pay.
- If you are **outbid**, you may get an alert or email depending on auction settings.
- If the site says the **amount changed**, refresh the page — another bidder moved the next step before your submit went through.
- If your registration or a prior bid on that lot is **pending** or **declined**, you may not be able to bid until the auctioneer resolves it.

### Onsite live webcast note

For some **onsite with live webcast** auctions, catalog bidding may only apply during **pre-bidding** or may be replaced by **live** bidding in the ring. Follow the **Bid Live** or webcast link on the lot when shown.

---

## How can an auctioneer edit a bidder's bid?

Only the **auctioneer** (primary account) can change how an existing online bid is treated. Team assistants cannot use this action in the current product.

### When you might edit a bid

- **Accept** — Apply a bid that was held for review (for example over permission limits).
- **Decline** — Remove the **current winning** bid; the visible high bid usually returns to the **previous accepted bidder** at their last accepted amount, or to the start-bid level if there is no other accepted bid. The declined bidder may receive email.
- **Raise maximum** — On **maximum-bidding** auctions only, increase a bidder’s **max bid** ceiling on an accepted bid (must stay within their registration permission and above the current next bid on the lot).

You generally cannot decline or pend a bid from a bidder who is **not** the current lot winner through this screen.

### Where to do it in the Auctioneer Dashboard

**From registration (per bidder):**

1. Open the auction → **Registration** (or bidder registration list).
2. View that bidder’s **bids** for the auction.
3. Use **edit** on a bid row (when the lot is still open and the row is editable).
4. Choose **Accept** or **Decline** for status, or **Edit max bid** on maximum-bidding auctions.

**From lot status (per lot):**

1. Open the auction → **Lot status** (or equivalent lot list with bid activity).
2. Open **bids on lot** for the lot you need.
3. Use **Update bid status** on the **current winner’s** row.
4. Set **Accept** or **Decline** and save.

After a decline, review the lot’s **current winning bid** and **next bid** on the catalog or lot list before publish or close.

### Related

- [How can an auctioneer edit a lot?](edit-lot.md)
- [Registration acceptance](../auction/registration-acceptance.md)
