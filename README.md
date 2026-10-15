# SEVA CONNECT — A Unified Social Help & Donation Platform
> **Tagline:** *"One Platform. Many Helping Hands."*

SEVA CONNECT is a social welfare platform where ordinary people, compassionate donors, registered NGOs, and volunteers connect in real-time to share essential resources, fulfill verified needs, and organize community aid with complete transparency and dignity.

---

## 🌟 Key Real-World Features & Architecture

### 0. Two-Interface Progressive Experience
- **1st Interface (Welcome Gateway):** Focuses solely on platform identity with the official **SEVA CONNECT Logo**, **Web Name**, and the official slogan: *"One Platform. Many Helping Hands."*, accompanied by an Email & Password sign-in form (with password hint `Ex: Password123`) and an integrated account registration toggle.
- **2nd Interface (Unified Community Hub):** Unlocked immediately upon entering email and password, revealing the full suite: interactive navigation, Live Geo-Map Explorer, urgent needs marketplace, usable item donation hub, registered NGO directory, volunteer campaigns, and dashboard. Returning to the 1st interface is always accessible via the **Sign Out** button.

### 1. Real-World User & NGO Registration
- **Register Any Person or NGO:** Click **"Register / Join"** in the top navigation bar to create an active account as:
  - **Beneficiary / Resident** (e.g. parents, teachers, students)
  - **Donor** (individual citizens, businesses)
  - **Registered NGO** (adds the organization to the verified NGO directory and map with 12A/80G details)
  - **Volunteer**
- **Profile Management:** View and edit your profile, update phone numbers, WhatsApp, physical address, and map coordinates at any time.

### 2. Live Interactive Geo-Map (Leaflet + Google Maps Directions)
- **Live Geo-Map Explorer:** View all community assets on an interactive map:
  - 🏢 **Emerald Green Pins:** Verified NGO centers
  - 🎁 **Orange Pins:** Donor pickup and drop points
  - 🆘 **Red Pins:** Urgent community help requests
  - 👤 **Blue Pin:** Your current location
- **One-Click Turn-by-Turn Directions:** Click any pin or card to launch **Google Maps Navigation** (`https://www.google.com/maps/dir/?api=1&destination=LAT,LNG`) directly to their physical center or pickup point!
- **Auto-Detect GPS:** Click **"Locate Me (GPS)"** to automatically center the map around your current device location using the HTML5 Geolocation API.

### 3. Direct Contact Everywhere (Call & WhatsApp)
- Every NGO, Donor listing, and Help Request now includes:
  - 📞 **"Call Directly" (`tel:+91...`):** Instant phone call action on mobile or desktop.
  - 💬 **"WhatsApp" (`https://wa.me/...`):** 1-click pre-filled WhatsApp chat for fast real-world communication without third-party barriers.
  - 📍 **Physical Street Address:** Full address with locality and pincode (e.g. *Akurdi, Nigdi, Kothrud, Pune*).

### 4. Intelligent Rule-Based Request Matching System
- Matches needs and donations based on an explainable, weighted algorithm:
  - **Category Alignment (45% weight):** Pairs Education, Food, Clothing, Healthcare, Household essentials.
  - **Locality & City Proximity (30% weight):** Prioritizes neighborhood matches (e.g. *Akurdi, Nigdi, Kothrud, Pune*).
  - **Keyword Similarity (15% weight):** Text analysis of requested item vs. listed item.
  - **Quantity Coverage (10% weight):** Full vs. partial quantity fulfillment.
- Transparent match explanation badge (e.g., *"95% Match: Same Category (Education), Matching Neighborhood (Akurdi)"*).

### 3. Multi-Step Donation Fulfillment Workflow
1. Beneficiary or NGO posts a request with locality and needed-by date.
2. Donors discover the request and submit an **Offer** with promised quantity.
3. Requester **Accepts** the offer, unlocking protected coordination chat.
4. Parties coordinate public handover locations safely.
5. Donor marks as **Handed Over**.
6. Recipient clicks **Confirm Receipt**, which updates the live request status, triggers celebratory confetti, and adjusts community impact metrics.

### 4. Privacy & Beneficiary Dignity Safeguards
- Exact home addresses, personal phone numbers, and identity documents are **never displayed publicly**.
- Only approximate localities (*Akurdi*, *Nigdi*, *Kothrud*) are exposed on public cards.
- Coordination happens through protected in-app channels.

---

## 🚀 How to Run Locally

### Option 1: Direct Browser Launch (Zero Dependencies)
You can open `index.html` directly in any modern browser (Chrome, Edge, Firefox, Brave):
- Double click `c:\Users\admin\Desktop\Antigravity\UHVFA2\index.html` or drag and drop it into your browser.

### Option 2: PowerShell HTTP Server (Recommended)
A lightweight local HTTP server script is included in this directory:
```powershell
cd c:\Users\admin\Desktop\Antigravity\UHVFA2
powershell -ExecutionPolicy Bypass -File .\server.ps1
```
Then navigate to: **`http://localhost:5174/`**

---

## 🗄️ Database Design (Supabase / PostgreSQL)

The complete relational database schema is provided in [`schema.sql`](file:///c:/Users/admin/Desktop/Antigravity/UHVFA2/schema.sql), featuring:

| Table | Description |
|---|---|
| `profiles` | Extended user records with role, locality, and contact fields |
| `ngos` | Registered organizations, registration numbers, and verification status |
| `ngo_verification_documents` | 12A, 80G, and Trust Deed files submitted for review |
| `help_requests` | Verified requirements with quantities, urgency, and statuses |
| `donation_listings` | Items pledged by donors with condition and pickup preference |
| `donation_offers` | Offers made by donors towards specific help requests |
| `donation_transactions` | Handover logs and confirmation timestamps |
| `campaigns` | NGO-driven large scale community aid campaigns |
| `volunteer_opportunities` | Drives posted by NGOs with skill requirements |
| `volunteer_applications` | Volunteer registrations and approval status |
| `notifications` | In-app notification queue |
| `conversations` & `messages` | Protected coordination chat |
| `reports` & `audit_logs` | Platform moderation and security trails |
| `categories` | Central taxonomy for items and causes |

### Deploying to Supabase
1. Create a project at [supabase.com](https://supabase.com).
2. Open the **SQL Editor** in your Supabase Dashboard.
3. Paste the contents of [`schema.sql`](file:///c:/Users/admin/Desktop/Antigravity/UHVFA2/schema.sql) and run it.
4. Enable **Storage** buckets: `item-photos` and `ngo-documents` with public read policies.
5. In [`supabase_client.js`](file:///c:/Users/admin/Desktop/Antigravity/UHVFA2/supabase_client.js), provide your `SUPABASE_URL` and `SUPABASE_ANON_KEY`.

---

## 📁 Project Directory Structure
```
c:\Users\admin\Desktop\Antigravity\UHVFA2\
├── index.html           # Full Single-Page Application (React 18, Tailwind, Lucide, Confetti)
├── schema.sql           # PostgreSQL / Supabase Schema, Indices, RLS & Triggers
├── supabase_client.js   # Cloud database client integration & localStorage sync
├── server.ps1           # Zero-dependency PowerShell local HTTP server
└── README.md            # Comprehensive documentation & architecture guide
```
