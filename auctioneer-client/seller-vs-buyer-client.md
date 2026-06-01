[Auctioneer Client](./index.md) · [Auction Journal](../../index.md)

# What is the difference between a seller client and a buyer client for an auctioneer?

*Last modified: 2026-06-01*

In the Auctioneer Dashboard, every **customer** is a **client** record under your company. A client is not only a contact card—it carries a **role** for how they work with **your** auctions.

The two main roles are **consigner (seller)** and **buyer**. They answer different questions: who **owns** the goods you sell, and who **purchases** lots at your sales.

---

## Seller client (consigner)

A **seller** (shown as **Consigner** in the dashboard) is the party who **owns the property** you sell. You host their items in auctions **you** conduct.

| Topic | What it means |
|-------|----------------|
| **Relationship to the auction** | The seller’s tie is through **lots**: each lot in your catalog can be assigned to a seller client. |
| **What you configure** | On the client profile, open the **Consigner** section—commission (default or specific), seller tax, and consignment tax-exempt rules. See [Configure customer as buyer and seller](customer-preferences.md#consigner-seller-settings). |
| **When you use it** | Building lots, running the sale, and **seller settlement** (commissions and seller-side charges on their consignments). |

A seller does **not** have to be a bidder on Auction Journal. Many consigners never register or bid online—they only consign through you.

---

## Buyer client

A **buyer** is someone who **purchases** lots at **your** auctions. Auction Journal uses the buyer profile for registration, clerking, bid cards, tax, buyer’s premium, and **buyer settlement**.

A buyer can come from several paths:

| Source | How they become your buyer client |
|--------|-----------------------------------|
| **You add them manually** | **Customers** → **Add Clients** → on step 3, expand **Buyer** and save. |
| **Registered bidder on Auction Journal** | Bidders across the platform do **not** automatically appear in your customer list. They become **your** buyer when you add them as a client **or** when they **register for one of your auctions** (the system then creates or updates a linked buyer client). See [Bidder vs customer](bidder-relationship.md). |
| **Floor bidder (onsite)** | Someone bidding in the room without using the public bidder site. You onboard them with **Onboard Floor Bidder**; they are stored as a **buyer** client for your company. See [Floor bidder](floor-bidder/index.md). |

On step 3 of add/edit client, the **Buyer** section covers reserved bid card, tax, bid permission, and buyer’s premium. See [Configure customer as buyer and seller](customer-preferences.md#buyer-settings).

---

## Side-by-side summary

| | **Seller (consigner)** | **Buyer** |
|---|------------------------|-----------|
| **Primary role** | Owns goods you sell | Purchases lots at your sales |
| **Tied to** | **Lots** (seller on each lot) | **Registrations**, bidding, clerking, **settlement** as purchaser |
| **Typical dashboard section** | **Consigner** on client step 3 | **Buyer** on client step 3 |
| **Platform bidder required?** | No | Only if they bid **online** under a linked bidder account |
| **Floor onsite bidder?** | No (unless they also buy) | Yes—onboard as floor bidder (buyer client) |

---

## Same person: buyer and seller together

One client profile can be **both** consigner and buyer at the same time—for example, a consigner who also buys at your sale.

When you add or edit the client:

1. Complete contact and address steps as usual.  
2. On **step 3**, expand **both** **Buyer** and **Consigner** and set each side’s preferences.  
3. Select **Submit**.

Auction Journal keeps one CRM record; buyer rules apply when they purchase, and consigner rules apply on lots where they are the seller.

---

## Related

- [Who is a customer? What types exist? How do I add a customer?](add-customer.md)  
- [Configure each customer as a buyer and as a seller](customer-preferences.md)  
- [In what ways are customers created?](creation.md)  
- [Bidder vs customer of an auctioneer](bidder-relationship.md)  
- [Floor bidder](floor-bidder/index.md)
