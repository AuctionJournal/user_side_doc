[Auction](./index.md) · [Auction Journal](../index.md)

# How is a settlement generated for an auction?

**Settlement** turns your **closed** auction and **clerking outcomes** into **buyer** and **seller** invoices (one generation per auction). Run it only after **bidding is finished** and you have reviewed **clerking** so sold lots, hammer prices, and buyers are correct.

---

## When to generate

| Step | What you do |
|------|-------------|
| 1. Bidding ends | The auction shows **Closed** (or, for **Onsite With Live Webcast**, all **rings** are closed). |
| 2. Clerking | Confirm each lot’s outcome (**Sold**, **Pass**, **Hold**, etc.), hammer, and buyer. The system may set defaults on lots that had no clerk result at close—see [auction stages — after close](auction-stages.md#after-the-auction-is-closed). |
| 3. Generate once | Open **Settlement** and run **Generate Invoice** when you are ready to bill. You cannot run first-time generation again on the same auction. |

You can still **edit clerking** after invoices exist in many cases (see [After you generate](#after-you-generate) below)—finish clerking corrections **before** generate when possible so invoices match what you intend to bill.

---

## Where to open Settlement

1. Go to **Auctions** → **Dashboard** for the auction ([auction dashboard](auction-dashboard.md)).
2. Open the **Settlement** tab when it appears:

| Auction type | Settlement tab shows when |
|--------------|---------------------------|
| **Onsite With Live Webcast** | **All rings** are completely closed |
| **Online** (Timed, Absolute, etc.) | Current time is **after** the auction **end date** |
| **Absentee Bidding** | Settlement tab is **not** shown on the dashboard in the current product (use your absentee workflow if applicable) |

![Settlement tab on Auction Dashboard](../image/auction/auction-dashboard-settlement.png "Settlement tab")

---

## Generate invoices (steps)

### 1. Start generation

On the **Settlement** tab, while **`Generate Invoice`** is visible (settlement not yet generated for this auction), click **Generate Invoice**.

### 2. Confirm

A confirmation dialog asks whether you want to generate invoices.

- Select **Confirm** to proceed, or **Cancel** to go back.
- The dialog may say you cannot change clerking after generation. In practice, **clerking edits are still allowed** after invoices exist until **payment** has started on a buyer’s settlement—see [After you generate](#after-you-generate). Refresh settlement totals after clerking changes if amounts look stale.

### 3. Lots on Hold (if applicable)

If any lots are still **`Hold`**, generation is blocked until you resolve them or choose to continue:

- You see an alert that some lots are on hold.
- If you **Confirm**, held lots are treated as **Pass** for settlement and invoices are generated.
- If you **Cancel**, fix clerking (change **Hold** to **Sold** or **Pass**) and try again.

### 4. Success

You see a success message (for example **Invoice generated successfully**). The tab then shows **Bidder** and **Seller** lists instead of **Generate Invoice**.

---

## What gets created

| Document | Who gets one | Based on |
|----------|--------------|----------|
| **Buyer settlement** | Each **approved** auction registration (internet or floor) that has at least one **Sold** lot to bill | Sold lots for that buyer, buyer premium, buyer tax (if the auction collects tax) |
| **Seller settlement** | Each **seller** (customer) who has at least one **Sold** lot | Sold lots for that seller, commission, seller tax, seller extras |

Notes:

- **One invoice per buyer registration** for the auction—all their sold lots appear as line items on the same document.
- Registrations with **no** sold lots do **not** get a buyer invoice.
- **Auction-level charges** on buyer invoices start empty; you can add them later when editing settlement.
- If **no** buyer or seller qualifies, you may still get **no** invoice rows, but the auction is marked as settlement generated—you cannot click **Generate Invoice** again. Fix clerking **before** generating when you expect invoices.

Toggle **Bidder** vs **Seller** on the Settlement tab to review each list. Line-item math: **[Buyer settlement calculation](buyer-settlement-calculation.md)** · **[Seller settlement calculation](seller-settlement-calculation.md)**.

---

## Onsite With Live Webcast shortcut

During live bidding, when **all lots are clerked**, the product may offer a path to generate invoices from the live flow (for example **All Lots Clerked – Ready for Invoice Generation**). That still calls the same backend generation as **Generate Invoice** on the dashboard. You can also use the **Settlement** tab after rings are closed.

---

## After you generate

| Topic | Behavior |
|-------|----------|
| **Clerking edits** | You can change hammer, status, or winner on lots after invoices exist **unless** payment has already started on the affected buyer settlement. Settlement amounts update from clerking changes **asynchronously**—refresh the Settlement tab if totals lag. |
| **No second generate** | **Generate Invoice** does not return; use clerking or settlement edit tools instead. |
| **Payments** | Collect buyer payments and seller payouts from the Settlement tab — [Settlement payment](settlement-payment.md). Starting payment can block further clerking for that buyer. |

Developer detail: [Generate settlement](../../auction/settlement/create.md) · [Clerking](../../auction/clerking.md).

---

## Typical errors

| Message / situation | What to do |
|---------------------|------------|
| Settlement tab not visible | Wait until **end date** (online) or close **all rings** (onsite). |
| **We found a few Lots on Hold** | Clear holds in clerking or confirm the hold warning to pass held lots. |
| **Invalid generation** | Auction may be unpublished, not ended, or settlement already generated. |
| **Auction is not closed yet** / **rings are not closed** | Close the auction or rings (onsite), then retry. |

---

## Related

- [Clerking](clerking.md) · [Edit clerking](edit-clerking.md)
- [Auction Dashboard — Settlement tab](auction-dashboard.md#settlement-tab)
- [Auction stages — after close](auction-stages.md#after-the-auction-is-closed)
- Dev: [Auction settlement](../../auction/settlement/index.md) · [Generate settlement (implementation)](../../auction/settlement/create.md)
