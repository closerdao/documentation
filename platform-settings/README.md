# Platform Configuration Overview

This page describes the settings that power your Closer platform. Each module below controls a specific part of the system. You can adjust these settings to match your community’s needs.

![](https://github.com/user-attachments/assets/93e93ea2-9d79-4a31-bdb7-bc5ffbb8bb8e)

---

## 1. Payment Settings

**Slug:** `payment`

**Key Fields:**
- **Enabled:** Whether the payment system is active.  
  _Example:_ `true`
- **Card Payment:** Allow payments by credit/debit card.  
  _Example:_ `true`
- **Crypto Payment:** Enable crypto payment options.  
  _Example:_ `true`
- **Polygon Wallet Address:** Wallet address on Polygon (currently not set).  
  _Example:_ `""`
- **Ethereum Wallet Address:** Wallet address on Ethereum (currently not set).  
  _Example:_ `""`
- **VAT Rate:** The tax rate applied.  
  _Example:_ `"0.23"`

---

## 2. Fundraiser Settings

**Slug:** `fundraiser`

**Key Fields:**
- **Enabled:** Turn fundraising on or off.  
  _Example:_ `true`
- **Credit Prices:**  
  - 30 Credits: `70`
  - 90 Credits: `60`
  - 180 Credits: `50`
- **Media & URLs:**  
  - Video ID (for promo or info): `"btBqOboLdOg"`
  - Wanderer URL: `/subscriptions/checkout?priceId=price_1N1YLVE9CDXOM807XtNAwiBW`
  - Pioneer URL: `/subscriptions/checkout?priceId=price_1O7ddSE9CDXOM807UGJZ5TEP`
  - One Month Shared and Private URLs (for Stripe checkout links)
  - Buy token URLs: for purchasing 5 or 10 tokens.
  - Host Event URL: an email link (e.g., `mailto: space@traditionaldreamfactory.com`)

---

## 3. Booking Settings

**Slug:** `booking`

**Key Fields:**
- **Enabled:** Activate the booking module.  
  _Example:_ `true`
- **Food Option Enabled:** Allow food options with bookings.  
  _Example:_ `true`
- **Utility Options:**  
  - Utility Option Enabled: `true`
  - Utility Fiat Value: `5` (in EUR)
  - Utility Token Value: `0.01` (in ETH)
- **Times & Duration:**  
  - Check-in Time: `14` (2PM)
  - Check-out Time: `11` (11AM)
  - Maximum Duration: `180` (days)
  - Minimum Duration: `"1"` day
- **Volunteer Commitment:**  
  - Example: `"4h/day"`
- **Member & Guest Settings:**  
  - Member maximum duration: `180` days, booking horizon: `365` days.
  - Guest maximum duration: `31` days, booking horizon: `90` days.
- **Discounts:**  
  - Daily: `0`
  - Weekly: `0.33` (33% off weekly)
  - Monthly: `0.66` (66% off monthly)
- **Seasonal Settings:**  
  - High season starts in: `"April"`
  - High season ends in: `"November"`
  - High season modifier: `1.3`
- **Cancellation Policies:**  
  - Last day: `0.5`
  - Last week: `0.5`
  - Last month: `0.75`
  - Default: `1`
- **Pick-Up Option:**  
  - Enabled: `true`

---

## 4. Subscriptions Settings

**Slug:** `subscriptions`

**Key Fields:**
- **Enabled:** Subscription system is on.  
  _Example:_ `true`
- **Elements:** An array of subscription tiers.  
  For example:
  - **Explorer:**  
    - Title: "Explorer"
    - Description: "DIP YOUR TOE BEFORE BUCKLING UP FOR THE ADVENTURE"
    - Price: `0` (free)
  - **Wanderer:**  
    - Title: "Wanderer"
    - Price: `10` (monthly)
    - Perks: "Co-living access, Community calls, Discord Access, Learning Hub, E-book..."
  - **Pioneer:**  
    - Title: "Pioneer" (emoji: 👨🏽‍🚀)
    - Price: `30` (monthly), includes discounts on stays.
  - **Citizen:**  
    - Title: "Citizen"
    - Price: `"193.67"` (monthly)
    - Perks: "Proof of Presence, Proof of Sweat, Instant Bookings, Flexible cancellation policy, Makerspace & Incubator"
  - **Test & Sacred Vessel:**  
    - Additional tiers with yearly billing options and extra perks.

*Note:* Each tier also includes fields like `slug`, `monthlyCredits`, `billingPeriod`, and availability flags.

---

## 5. General Platform Settings

**Slug:** `general`

**Key Fields:**
- **Enabled:** General settings are active.
- **Time Zone:**  
  _Example:_ `"Europe/Lisbon"`
- **Platform Short Name:**  
  _Example:_ `"tdf"`
- **Platform Full Name:**  
  _Example:_ `"Traditional Dream Factory"`
- **Domain:**  
  _Example:_ `"traditionaldreamfactory.com"`
- **Legal Address:**  
  _Example:_ `"Fábrica de Sonhos Tradicional, 7540-011, Abela, Santiago do Cacém, Portugal"`
- **Client Support Email:**  
  _Example:_ `"traditionaldreamfactory@gmail.com"`
- **Social Media Links:**  
  - Instagram: `https://instagram.com/traditionaldreamfactory`
  - Facebook: `https://www.facebook.com/oasaliving`
  - Twitter: `https://twitter.com/traditionaldreamfactory`
- **Location Coordinates:**  
  - Latitude: `"38.003164469592555"`
  - Longitude: `"-8.55915483117878"`
- **Visitors Guide:**  
  _Example:_ a link to a Google Docs guide.
- **Facebook Pixel ID:**  
  _Example:_ `"761004479106346"`
- **FAQs Google Sheet ID:**  
  _Example:_ `"1ZPnTQQW9sI5X_Ig1A8lKZ7DWI8UmoYNUn66pB8WUYUY"`
- **Minimum Stay Duration for Vouching:**  
  _Example:_ `"14"` (days)

---

## 6. Booking Rules

**Slug:** `booking-rules`

**Key Fields:**
- **Enabled:** Booking rules are active.
- **Elements:**  
  - Example Rule 1: Title: `"rule 1"`, Description: `"text"`
  - Example Rule 2: Title: `"rule 2"`, Description: `"rule"`

---

## 7. Volunteering Settings

**Slug:** `volunteering`

**Key Fields:**
- **Enabled:** Volunteering features are on.
- **Minimum Stay for Volunteering:**  
  _Example:_ `"14"` days
- **Residency Settings:**  
  - Minimum Stay: `30` days
  - Time Frame: `"October 2024 - December 2025"`
- **Skills:**  
  _Example:_ `"Gardening & Permaculture, Carpentry & Construction, Hospitality & Space Care, Cooking, Photography"`
- **Diet Options:**  
  _Example:_ `"Vegetarian, Vegan, Gluten-free, Dairy-free, Non-vegetarian"`
- **Residents Pay Utilities:**  
  _Example:_ `false`

---

## 8. Emails Configuration

**Slug:** `emails`

**Key Fields:**
- **Enabled:** Email notifications are active.
- **Elements:**  
  A list of email templates that trigger on events such as:
  - Booking paid (for guest and space host)
  - Booking cancelled
  - Booking request (for guest and space host)
  - User account actions (creation, email update, password reset, invitation)
  - Subscription events (created, updated, cancelled, paused, resumed, payment failed)
  
*Note:* The email templates include details like subject lines, body content, call-to-action links, and trigger conditions.

---

## 9. Learning Hub Settings

**Slug:** `learningHub`

**Key Field:**
- **Enabled:** Learning Hub is active.  
  _Example:_ `true`

---

## 10. Citizenship Settings

**Slug:** `citizenship`

**Key Fields:**
- **Enabled:** Citizenship program is active.
- **Space Host Vouching Required:**  
  _Example:_ `true`
- **Down Payment Percent:**  
  _Example:_ `10`%
- **Token Price Modifier Percent:**  
  _Example:_ `5`%
- **Minimum Vouches Required:**  
  _Example:_ `"3"`
- **Minimum Vouching Stay Duration:**  
  _Example:_ `14` days

This module controls how membership is granted using token gating and community endorsements.

---

## 11. Affiliate Settings

**Slug:** `affiliate`

**Key Fields:**
- **Enabled:** Affiliate program is active.
- **Commission Rates:**  
  - Token Sale Commission Percent: `3`%
  - Financed Token Sale Commission Percent: `3`%
  - Subscription Commission Percent: `30`%
  - Stays Commission Percent: `10`%
  - Events Commission Percent: `10`%
  - Products Commission Percent: `10`%

This module sets the commission rates for various revenue streams generated through affiliate referrals.

---

## Final Notes

Each configuration module is set to be **public**, meaning that these settings are visible and managed by the platform administrator. They are created and updated by your admin team, and can be modified as your community evolves.

Use this page as a reference when adjusting your Closer platform settings. By keeping these values updated, you ensure that your platform continues to operate smoothly and meets the needs of your community.
