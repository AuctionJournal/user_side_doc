[Auction](./index.md) · [Auction Journal](../index.md)

# How can an auctioneer edit clerking?

Use **Edit** on a lot in **Auction Day** clerking to change **hammer price**, **status**, or **winning buyer** after the auction has **closed**. Changes update the lot, create an audit **log**, and—if you already generated settlement—update invoice lines when allowed.

**Prerequisite:** [How does clerking work?](clerking.md)

---

## Open Edit Clerk

1. Go to **Auctions** → **Dashboard** → **Auction Day** (`/dashboard/auctions/{auctionId}/clerking`).
2. Find the lot in the table (use **Search**, **Sort**, or **Filter**).
3. Click the **Edit** (pencil) icon on that row.

---

## Fields in Edit Clerk

| Field | What you can do |
|-------|-----------------|
| **Hammer Price** | Dollar amount; editable when status is **Sold** |
| **Bidder#** | Pick a registered **internet bidder** or **floor** customer from the auction registration list |
| **Status** | **Sold**, **Hold**, or **Pass** (and **High Bid** on absentee auctions) |
| **Reasons** | Optional note stored in clerk logs |

Read-only on the form: lot number, title, seller code, quantity.

---

## Save and confirmation

1. Select **Save**.
2. Read the confirmation: you are overwriting automated clerking; **only Sold lots** appear on invoices.
3. Confirm **Save** again.

On success, the list refreshes. If settlement already exists, totals may take a moment to update—refresh the **Settlement** tab if amounts look stale.

---

## Make precedence bid the winning bidder

For **online** auctions (not **Onsite With Live Webcast** with live webcast data on the lot), you can use **Make precedence bid the winning bidder** instead of picking a buyer manually.

Step-by-step page: [How to make preceding bidding as winning bidder?](precedence-bidder-winner.md)

The system sets the lot to **Sold** using the latest **accepted** bid from a **different** bidder than the current winner (per backend rules). A log reason is recorded automatically.

This button is **not** available for onsite live webcast lots that already have live webcast bidding records.

---

## View clerk logs

Click **View** (eye) on a row to open **View Logs**:

- Each entry shows date/time (auction timezone), hammer, bidder or floor client code, status, and **reason** if you entered one.
- If no edits were saved yet, you may see one line based on the lot’s current values.

---

## Rules and limits

| Rule | Detail |
|------|--------|
| **Auction must be closed** | Edit is rejected before the auction **end date** |
| **Hammer** | Must be greater than zero and **not below** the lot’s current bid at edit time |
| **Buyer** | Must be **approved** (or permanently approved) for this auction |
| **Online lots** | If the bidder has a bid row on the lot, it must be **Accepted** (not pending/declined) |
| **No duplicate save** | Same hammer, status, and buyer as already on the lot is rejected |
| **Payment started** | If the current or new buyer’s settlement already has payment recorded or is **Paid**, clerking edit is **blocked** |
| **After settlement** | Edits can update invoice lines asynchronously; refresh settlement if needed |

Finish clerking corrections **before** [collecting full payment](settlement-payment.md) when possible.

---

## What each status change does

| Change | Effect |
|--------|--------|
| Set **Sold** with buyer | Lot bills on buyer/seller settlement (after generate) |
| **Pass** or **Hold** from **Sold** | Lot drops off buyer/seller invoice lines |
| Change hammer on **Sold** | Recalculates premium/tax/commission on that line |
| Change buyer on **Sold** | Moves the lot line to the new buyer’s invoice |

---

## Related

- [Clerking overview](clerking.md)
- [Generate settlement](generate-settlement.md)
- [Settlement payment](settlement-payment.md)
- [Edit settlement](edit-settlement.md) — fees and adjustments, not hammer/buyer
- Dev: [Edit clerking (implementation)](../../auction/clerking/edit.md)
