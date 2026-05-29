[Auction](./index.md) · [Auction Journal](../index.md)

# Explain each auction field

Last modified: 2026-05-29

This guide lists **auction-level** fields you set or see in the **Auctioneer Dashboard** when you build and run a sale. It does **not** cover **lot** fields — see [Explain each auction lot field](../auction-lot/fields.md) — or every button on the auction list.

For **where** to fill fields step by step, use [Details](build-details.md) and [Upload Settings](build-upload-settings.md). For **dates and stages**, see [Bidding dates](bidding-dates.md) and [Auction lifecycle](lifecycle.md).

---

## Where auction fields live

| Area | What you configure |
|------|-------------------|
| **New Auction** (create) | Type, name, listing date; onsite also **catalogued / non-catalogued** |
| **Details** tab | Identity, images, default lot fees, shipping, rings (onsite) |
| **Upload Settings** tab | Marketing dates text, notices, payment/pickup copy, bidding schedule, registration, increments |
| **Lots** tab | Catalog (not auction header fields, but required for many types) |
| **Expenses** tab | In-house auction charges |
| **Auction list / dashboard** | Status badge, lot count, settlement state |

---

## Create auction (first screen)

| Field | What it is | Notes |
|-------|------------|--------|
| **Auction Type** | Kind of sale (online timed, online absolute, absentee, onsite with live webcast) | **Cannot change** after the draft exists |
| **Name** | Title of the auction | Shown to bidders |
| **Listing Date** | When the sale becomes visible on Auction Journal and registration can open | Set at create; locks after registration starts — [bidding dates](bidding-dates.md) |
| **Lot type** (onsite only) | **Catalogued** (lots in system) or **Non catalogued** | **Cannot change** after create; non-catalogued uses flat bidding rules |

---

## Details → Auctions Information

| Field | What it is | Notes |
|-------|------------|--------|
| **Auction Type** | Same as at create | Read-only on build screen |
| **Name** | Auction title | Required at publish |
| **Listing Date** | Same as **start date** in scheduling | See [bidding dates](bidding-dates.md) |
| **Terms & Conditions** | Legal/terms bidders accept | Required at publish |
| **Short BP Explanation** | Short explanation of **buyer’s premium** for bidders | Required at publish |
| **Auction ID** | Your reference code for the sale (letters and numbers) | Unique; use **+ AUTO GENERATE ID** if you like |
| **Description** | Full auction description (rich text) | Required at publish |
| **Currency** | Sale currency | **USD** in current product |
| **Collect Taxes** | Whether buyer/seller tax formulas apply | If on, tax formulas may be required at publish |
| **Address** (street, city, state, country, ZIP) | Physical location of the sale | Required at publish; used for map/location on the public site |

**Templates:** Bell icons may apply saved text from **Miscellaneous → Templates**.

---

## Details → Auction Images

| Field | What it is | Notes |
|-------|------------|--------|
| **Auction images** | Photos for the auction header / gallery | At least one required at publish — [manage auction images](manage-auction-images.md) |
| **Preview gallery order** | Which images appear first | **Preview** tab — reorder featured images |

---

## Details → New Lot Default

Defaults for **new lots** and often for formulas on existing lots when you change them at auction level.

| Field | What it is | Notes |
|-------|------------|--------|
| **Commission** | Seller commission formula | From **Miscellaneous → Formulas** — [formulas](../auctioneer-misc/formulas.md) |
| **Buyer Premium** | Buyer premium formula | Required for most online publishes |
| **Reserve amount** | Default reserve on new lots | Optional on draft |
| **Sellers / Consigner** | Who may consign in this auction | Search and add customers |
| **Default seller** | Which seller is pre-selected on new lots | One of your added sellers |
| **Buyer Tax / Seller Tax** | Tax formulas when **Collect Taxes** is on | |
| **Use consolidated seller** (if shown) | Whether settlement groups sellers | When enabled in your build |

Full guide: [Default settings for all lots](default-lot-settings.md).

---

## Details → Shipping

| Field | What it is | Notes |
|-------|------------|--------|
| **Shipping availability** | Whether you offer shipping on this auction | e.g. all lots, specific lots, or none — [shipping](shipping.md) |
| **Shipping account** | Account used when shipping is offered | Required when availability needs it |

---

## Details → Ring Option (onsite with live webcast)

Only when **Auction will have multiple rings** is enabled in Auctions Information.

| Field | What it is | Notes |
|-------|------------|--------|
| **Assign ring by** | Split rings by **lot number** or **sale order** range | |
| **Ring ranges** | **Range begins** / **Range ends** per ring | Each ring gets a live session — [rings](rings.md) |
| **Multiple rings** checkbox | Whether the sale runs more than one ring | Enables Ring Option section |

---

## Upload Settings → Dates (informational text)

These are **text lines for bidders** on the public auction page. They do **not** start or stop bidding by themselves.

| Field | What it is |
|-------|------------|
| **Preview Date/Time** | When buyers can preview items (your wording) |
| **Auction Date/Time** | Main auction timing (marketing copy) |
| **Checkout Date/Time** | Payment or pickup window (your wording) |

Real bidding clocks are under **Bidding** (online) or pre-bid / live days (onsite) — [bidding dates](bidding-dates.md).

---

## Upload Settings → Notices

| Field | What it is |
|-------|------------|
| **Bidding Notice** | Rules and alerts about bidding |
| **Auction Notice** | General announcements for the sale |

---

## Upload Settings → Payment / Shipping / Pickup

| Field | What it is |
|-------|------------|
| **Payment Information** | How winners pay (cards, wire, etc.) |
| **Shipping / Pick Up** | Pickup hours, location, shipping policy narrative |

Complements **Details → Shipping** (availability) with instructions bidders read.

---

## Upload Settings → Bidding

### All online timed / online absolute / absentee

| Field | What it is | Notes |
|-------|------------|--------|
| **Bidding type** | Mirrors auction type (e.g. online timed) | Set from type |
| **Reserve type** | Whether reserve status is shown to bidders | Published vs unpublished reserve |
| **Bid amount type** | **Maximum bidding** vs **flat / fixed bidding** | |
| **Timezone** | Zone for open/close times | US zones in product |
| **Open bidding** | When internet bidding **starts** | On or after listing date |
| **Closed bidding** | When main online bidding **ends**; soft close begins | After open bidding |
| **Soft close seconds** | Gap between each lot **starting** to close (`hh:mm:ss`) | Online only — [soft close](soft-close.md) |
| **Bid soft closed seconds** | Extra time on a lot when bid during soft close | Online only |
| **Show immediate bid status on closed lots** | Show won/lost on closed lots when enabled | Optional |
| **Time is money on quantity &gt; 1** (if shown) | Special rule for multi-quantity lots | Optional advanced rule |
| **Auto-sync grouped lot soft close** (if shown) | Keep grouped lots on same close schedule | Optional |

**End date** is calculated when you publish (from closed bidding, soft close, and lots). You do not type it on online timed sales.

### Onsite with live webcast only

| Field | What it is | Notes |
|-------|------------|--------|
| **Pre-bidding allowed** | Whether bidders can bid on the website catalog before / between live days | If off, catalog bids only during live workflow rules |
| **Pre-bidding start** | When catalog pre-bids open | |
| **Multi-date bidding** | More than one **live webcast day** | If off, only the first bidding day is kept at publish |
| **Bidding day(s) / timings** | Start of each **live webcast day** | Last day’s midnight (in timezone) ends the auction — [bidding dates](bidding-dates.md) |
| **Timezone** | Used for end-of-last-day and display | |

Onsite auctions **do not** use open/closed bidding or soft close fields on the auction.

---

## Upload Settings → Registration

| Field | What it is | Notes |
|-------|------------|--------|
| **Registration types** | **Registered bidder** vs **verified bidder** (ID, card, phone, etc.) | |
| **Starting bidcard number** | First bidder card number assigned in this auction | |
| **Bidder permission** | Default bid limit for auto-approved registrations | |
| **Email subject / Email body** | Message sent when registration is approved | System appends your profile signature — do not duplicate |

See [registration acceptance](registration-acceptance.md).

---

## Upload Settings → Bid increment

| Field | What it is | Notes |
|-------|------------|--------|
| **Increment table** | Rows: **up to amount** → **increment** | Required at publish; can load from template |
| **Increment type** | How increments apply to bids | e.g. force minimum to schedule vs apply by each step |

---

## System fields you see (not always on the build form)

| What you see | Meaning |
|--------------|---------|
| **Draft** | Not published; only your company sees the auction |
| **Published** | Published; listing date not reached yet |
| **Registration Open**, **Bidding Open**, **Soft Close**, **Prebidding Open**, **Live**, **Closed** | Time-based status on the auction card — [stages](auction-stages.md) |
| **Total lots** | Count of auction-ready lots (updates at publish) |
| **Settlement generated** | You already ran **generate settlement** for this auction |
| **Incomplete lots** (if shown in tools) | Lot numbers not yet auction-ready — finish before publish |
| **Analysing lots** (if shown) | Lot AI batch still running |

---

## Fields by auction type (quick reference)

| Field group | Online timed / absolute | Absentee | Onsite live webcast |
|-------------|-------------------------|----------|---------------------|
| Open / closed bidding, soft close | Yes | Yes (clerking differs) | No |
| Pre-bid, bidding days | No | No | Yes |
| Rings | No | No | Optional multi-ring |
| Catalogued lots required at publish | Yes (catalogued) | Per rules | Catalogued yes; non-catalogued may publish without lots |
| Commission / buyer premium at publish | Typically required | May differ | Required for non-catalogued |

Type overview: [Auction types](auction-types.md).

---

## Related

- [Details section](build-details.md)
- [Upload Settings](build-upload-settings.md)
- [Bidding dates](bidding-dates.md)
- [Auction lifecycle](lifecycle.md)
- [Create an auction](create-auction.md)
- Developer field reference: [Auction fields](../../auction/fields.md)
