[Auction Lot](./index.md) · [Auction Journal](../index.md)

# What are the ways lots can be created in an auction?

Auction Journal offers several ways to add lots to an auction. You can use more than one on the same sale (for example, assistants add photos in the field, then you import remaining lines from a spreadsheet, or you create instant lots during a live ring).

---

## At a glance

| Method | Who | Where | Lot when saved | Auction ready? |
|--------|-----|--------|----------------|----------------|
| **New Lot** (manual) | Auctioneer | Auctioneer Dashboard → auction **Lots** tab → **New Lot** | Full catalog row | Yes (if required fields are complete) |
| **Import LOTS** (CSV) | Auctioneer | Same **Lots** tab → **Import LOTS** | Full rows from your file (after validation) | Yes for created/updated complete rows — see [How do I import lots?](import-lots.md) |
| **Fast catalog** | Auctioneer user (assistant) | [Lot-AI](https://catalog.auctionjournal.com/) catalog app | Minimal row (number, images, seller, quantity) | **No** — must be completed later |
| **Instant lot** | Auctioneer | **Live** onsite webcast ring while bidding | Full lot created on the fly for a lot number that does not exist yet | Yes when the create flow finishes |
| **Generate QR** (related) | Auctioneer | **Lots** tab → **Generate QR** | Placeholder only | N/A — not a real catalog lot until replaced |
| **Mass import images** (related) | Auctioneer | **Lots** tab → **Mass import images** | Adds images to **existing** lot numbers only | Does not create new lots — see [bulk image import](import-lot-images.md) |

For **catalogued** auctions, every real lot (not QR-only placeholders) must be **auction ready** before you can **publish**. For **non-catalogued** auctions, publish focuses more on auction-level setup; lots can still be added and completed as the sale runs.

---

## 1. New Lot — manual, one at a time

**Best for:** Adding or fixing a single lot with full title, description, category, media, seller, and pricing defaults.

1. Open the auction in the **Auctioneer Dashboard**.
2. Go to the **Lots** tab.
3. Click **New Lot**.
4. Complete the form and **Save**.

The lot is created with the auction’s **New Lot Default** (commission, buyer premium, taxes, soft close, reserve, start bid, default seller, and so on). See the full walkthrough: [How do I create a lot in an auction?](create-lot.md).

**Auction ready:** A successful **New Lot** save counts as auction ready when all required fields are present, so it satisfies publish rules on catalogued auctions.

---

## 2. Import LOTS — spreadsheet / CSV

**Best for:** Many lots at once from a CSV or export from another system.

1. On the auction **Lots** tab, click **Import LOTS**.
2. Upload your file and map columns to lot fields.
3. Run validation, then confirm import.

The system checks sellers, categories, duplicate lot numbers and sale orders, and ring ranges where they apply. On **published** timed auctions, import may be blocked or limited close to the auction end or after bidding has started.

**Auction ready:** Imported lots are created as complete catalog rows when your file and mapping supply the required data.

Detailed import steps: [How do I import lots?](import-lots.md).

---

## 3. Fast catalog — assistant in Lot-AI

**Best for:** Field work—photographing items and assigning lot numbers before the auctioneer fills in titles and descriptions in the office.

An **auctioneer user (assistant)** works in the **Lot-AI** catalog app ([catalog.auctionjournal.com](https://catalog.auctionjournal.com/)) for auctions belonging to their auctioneer.

Typical fast catalog capture:

- **Lot number** (must not already exist, unless the number is only a **QR placeholder**)
- **Images** (upload or camera)
- **Seller** and **quantity** (session defaults can pre-fill seller and quantity)

The system assigns **sale order** on the server. The new lot is **not auction ready** and is not treated as a finished catalog line for publish until completed.

**To finish the lot**, the auctioneer (or team) in the **Auctioneer Dashboard**:

- **Edit Lot** — enter title, description, category, and any missing fields manually, or  
- **Analyse Lots** / AI tools on the **Lots** tab — generate content from images where your workflow uses Lot-AI analysis.

See [Who is a user? How can a user help an auctioneer?](../auctioneer-assistants/index.md). For AI-specific steps, see [Auction Lot AI — fast catalog & Analyse lots](lot-ai.md).

---

## 4. Instant lot — during live onsite webcast bidding

**Best for:** **Non-catalogued** **Onsite With Live Webcast** sales when you open a lot number in the live ring that does not exist yet.

This path only appears **during live bidding** in the webcast ring, not from the normal **Lots** tab before the sale.

1. Start live bidding for an **Onsite With Live Webcast** auction whose catalog type is **non-catalogued**.
2. In the live ring, try to **open** a lot number that is not in the catalog.
3. The system offers **Create Instand Lot** for that number (dialog title shows the lot number).
4. Follow the steps: add images (optional image recognition), then complete the lot form (same core fields as **New Lot**, with sale order handled for instant create).
5. After save, the ring can open that lot for bidding.

If the lot number is **outside** the current ring range, you may see a warning that the lot will be created and the **last ring range extended** to include it.

**Auction ready:** The instant flow creates a real lot suitable for opening in the live ring once the form succeeds.

Step-by-step live UI detail: [How do I create an instant lot during live bidding?](instant-lot-live.md).

---

## Related ways (not full catalog create)

These tools **seed** the catalog or media; they are not the same as a full **New Lot** or **Import LOTS** row.

| Tool | Purpose |
|------|---------|
| **Generate QR** | Creates **placeholder** lot numbers for labels; replace with a real lot via **New Lot** or import before publish. See [What are QR lots?](qr-lots.md). |
| **Mass import images** | Upload many images keyed by lot number onto lots that already exist. See [How do I import lot images in bulk?](import-lot-images.md). |

---

## Choosing a method

| Your situation | Start with |
|----------------|------------|
| One lot, all details known now | **New Lot** |
| Dozens or hundreds of lines in a spreadsheet | **Import LOTS** |
| Photos in the field, details later | Assistant **fast catalog** in Lot-AI, then dashboard **Edit** or **Analyse Lots** |
| Non-catalogued live sale, new lot number at the block | **Instant lot** in the live ring |
| Pre-print QR labels before data entry | **Generate QR**, then **New Lot** or import on those numbers |

---

## Related

- [How do I create a lot in an auction?](create-lot.md) — **New Lot** form detail  
- [How do I create an instant lot during live bidding?](instant-lot-live.md) — **Create Instand Lot** in the live ring  
- [Auctioneer assistants](../auctioneer-assistants/index.md) — Lot-AI and team workflow  
- [Auction types](../auction/auction-types.md) — catalogued vs non-catalogued  
- [Rings](../auction/rings.md) — lot numbers and live webcast rings  
- [Create an auction](../auction/create-auction.md) — publish and catalog readiness  
