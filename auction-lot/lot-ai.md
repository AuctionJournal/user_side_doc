[Auction Lot](./index.md) · [Auction Journal](../index.md)

# Auction Lot AI — fast catalog and Analyse lots

These steps cover **team assistants** working in **Lot-AI** and **auctioneers** running **Analyse lots** in the Auctioneer Dashboard. For other ways to add lots, see [What are the ways lots can be created in an auction?](lot-creation-ways.md).

---

## How does an auctioneer user create an auction lot?

An **auctioneer user** is a team **assistant** working for your auction company. They prepare lots in the **Lot-AI** catalog app at [catalog.auctionjournal.com](https://catalog.auctionjournal.com/) — not in the main Auctioneer Dashboard.

1. Sign in to Lot-AI and open the auction.
2. Start **Add lot** from the catalog workflow.
3. Enter the **lot number** and confirm it is available. You cannot reuse a number that already has a full catalog line; **QR-only** placeholders are allowed.
4. Enter **quantity** and choose the **seller**. Lot-AI may remember defaults for seller and quantity for this auction until you log out.
5. Add **photos** with the camera or upload — at least one image is required to save.
6. Select **Save**.

The lot is stored for your auction. It is **not** ready to publish on its own: it stays off the public catalog until **title**, **description**, and **category** are filled in (using **Analyse lots** below or **Edit Lot** in the dashboard).

If Lot-AI reports that the auction is incomplete, the auctioneer must finish required auction settings (auction ID, fees, increments, default seller, and related fields) in the **Auctioneer Dashboard** before assistants can add lots.

See also [Who is a user? How can a user help an auctioneer?](../auctioneer-assistants/index.md).

---

## How can an auctioneer user edit a lot?

### In Lot-AI (assistant)

1. Open the auction catalog and find the lot card.
2. Tap the **edit** control on the lot.
3. What you can change depends on the lot:
   - **Still being built** (no title yet): adjust **seller**, **quantity**, and **images** (add, remove, or reorder).
   - **After a title exists** (you entered it or the auctioneer ran AI): you can also edit **title**, **description**, and **category**.
4. Save with **Update Lot**.

The lot number is fixed after the lot is created; focus on photos and text.

### In the Auctioneer Dashboard (auctioneer)

Use **Edit Lot** on the auction **Lots** tab for the full catalog form (fees, visibility, and publish rules). See [How can an auctioneer edit a lot?](edit-lot.md).

---

## How do I generate content for a lot using AI?

**Who:** The **auctioneer** (primary account) in the **Auctioneer Dashboard**.

**When:** After assistants or other flows have added lots with photos but **without** full titles and descriptions. On the **Lots** tab, **Analyse lots** appears when incomplete lots are waiting.

1. Open the auction and go to the **Lots** tab.
2. Click **Analyse lots**.
3. Read the confirmation: AI uses the **first four images** in the lot’s image order (featured images). If the wrong photos are first, reorder them in **Edit Lot** before you generate.
4. Click **Generate**.
5. Follow **Lot Analysis Progress**. You can close the dialog and use **View Status** while processing runs. Large batches take time; the screen shows how many lots are done and an estimated time remaining.
6. When processing finishes, review the lot list. Open **Edit Lot** on any line that still needs fixes before you publish.

AI fills **title**, **description**, and **category** and marks those lots complete for catalog rules that depend on a finished line. Lots that fail (for example, no usable images) stay incomplete until you fix images or edit manually.

Assistants **do not** run **Analyse lots**; they add photos in Lot-AI, then the auctioneer runs AI from the dashboard.

**Related:** [Ways to create lots](lot-creation-ways.md) (fast catalog) · [Create a lot manually](create-lot.md) · [Edit a lot](edit-lot.md)
