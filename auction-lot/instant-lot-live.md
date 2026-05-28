[Auction Lot](./index.md) · [Auction Journal](../index.md)

# How do I create an instant lot during live bidding?

An **instant lot** is a catalog line you create **at the block** while a **non-catalogued** **Onsite With Live Webcast** sale is already **live**. You enter the lot number in the live ring, add photos, fill in (or AI-generate) details, save, and the lot **opens in that ring** for bidding.

This is not the same as **New Lot** on the auction **Lots** tab before the sale. See [ways to create lots in an auction](lot-creation-ways.md).

---

## When to use this

| Situation | Use instant lot? |
|-----------|------------------|
| Onsite live webcast, **Non Catalogued**, ring is **live** | Yes — lot number at the block is not in the system yet |
| You built the full catalog before going live | No — **open** the existing lot instead |
| Online timed auction or catalogued onsite sale | No — use **New Lot**, **Import LOTS**, or pre-build the catalog |
| Before live bidding starts | No — use **New Lot** on the **Lots** tab |

---

## Before you start

| Requirement | Why |
|-------------|-----|
| Auction type **Onsite With Live Webcast** | Instant create is only wired to the live webcast ring |
| **Non Catalogued** lot type (chosen when the auction was created) | Catalogued sales expect lots to exist before you open them |
| **Live bidding** started and you are inside the **live ring** | The wizard appears when you try to **open** a missing lot number during the sale |
| Auction setup complete (sellers, fees, rings, bid increments) | The lot form inherits auction defaults like **New Lot** |

For auction and ring setup, see [auction types](../auction/auction-types.md) and [How does Ring work in an auction?](../auction/rings.md). Starting the live session is covered under [Onsite live webcast](../auction/onsite-livewebcast/index.md) (full live-bidding guides are still being added to the doc set).

---

## Start the create flow

1. Open the auction and go to **live bidding** for the correct **ring**.
2. In the live ring controls, enter the **lot number** you want to sell next.
3. Trigger **open lot** (same action you use to bring a catalogued lot onto the block).

**If that lot number does not exist yet** (and the auction is non-catalogued), Auction Journal opens **Create Instand Lot - (#_lot number_)** instead of only showing an error.

**If the lot number is above your last ring’s range**, you may see a warning that the lot is outside the current ring range and that creating it will **extend the last ring range**. Confirm if you intend to proceed.

**If a different lot is already open**, you may be asked to confirm before switching—especially if the current lot was created on the fly and is not clerked yet.

---

## Step 1 — Add images

The wizard starts on **images** (first step in the stepper).

| Rule | Detail |
|------|--------|
| Minimum | At least **one** image |
| Maximum | **Four** images |
| Sources | **SELECT FROM YOUR FILES** (multiple files) or **camera capture** on supported devices |

Remove a thumbnail with the **X** on the preview if you picked the wrong file.

Click **Next** when you have the photos you want. **Cancel** closes the wizard without creating a lot.

---

## Step 2 — Analyze or create manually

Review the image thumbnails, then choose one path:

### Analyze (AI)

1. Click **Analyze**.
2. Wait while images are processed and uploaded.
3. The service suggests **title**, **description**, and **category** from the photos (same family of image analysis used elsewhere in lot tooling).
4. The wizard moves to the lot details step with those fields pre-filled where possible.

### Create Lot Manually

1. Click **Create Lot Manually**.
2. Images are uploaded without running analysis.
3. You enter title, description, and category yourself on the next step.

Both paths assign **sale order** automatically on the server (you do not pick it in this step).

Use **Previous** to return to image selection if you need different photos.

---

## Step 3 — Lot details and save

The final step uses the same core sections as **[New Lot](create-lot.md)**:

- **Lot Info** — lot number is fixed to the number you typed in the ring; **sale order** is filled in for you and cannot be changed here
- **Seller**, **title**, **description**, **category**
- **Lot value** — for non-catalogued sales, **start bid** is required; reserve and value range follow your auction rules
- **Lot media** — images from steps 1–2; you can adjust media on this screen if needed

Click **Save** to create the lot. Use **Previous** to go back to step 2. **Cancel** exits without saving.

Field-by-field help: [How do I create a lot in an auction?](create-lot.md).

---

## After save

When save succeeds:

1. The **Create Instand Lot** dialog closes.
2. The system **opens that lot in the current ring** so you can set the next bid amount and run floor or internet bidding.
3. Continue the sale as usual (clerking, pass/sold, open the next lot).

The new lot is a **real catalog row** (auction ready when required fields are complete), not a QR placeholder.

---

## What this is not

| Tool | Difference |
|------|------------|
| **New Lot** (Lots tab) | Used **before** or outside live bidding; not triggered by opening a missing number in the ring |
| **Import LOTS** | Bulk spreadsheet rows; no live-ring wizard |
| **Fast catalog** (Lot-AI app) | Assistant minimal capture; completed later in the dashboard |
| **Instant lot** | Only during **live** non-catalogued onsite webcast when the lot number is missing at open time |

---

## Related

- [Ways to create lots in an auction](lot-creation-ways.md)
- [How do I create a lot in an auction?](create-lot.md)
- [Auction types](../auction/auction-types.md)
- [Rings](../auction/rings.md)
- [Onsite live webcast](../auction/onsite-livewebcast/index.md)
