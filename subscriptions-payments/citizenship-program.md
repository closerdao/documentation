# Citizen Program (Configurable Membership)

The **Citizen Program** lets communities transform their spaces into membership clubs. Members can unlock deeper engagement through token gating, payment plans, and community vouching. The following details are based on an example configuration visible in the screenshots—you can adjust these settings to fit your own needs.

---

## 1. Overview

### Example Citizen Package
- **Membership Token Requirement:** Hold **TDF30** or finance it monthly (e.g., from €193.67/month).
- **Benefits:**
  - Everything included in a lower-tier package (e.g., Pioneer).
  - **Proof of Presence**: Reward members who physically spend time in the community.
  - **Proof of Sweat**: Encourage hands-on contributions or volunteer work.
  - **Instant Bookings**: Simplified reservation flow for accommodations or events.
  - **Flexible Cancellation**: More lenient refund policies for Citizen members.
  - **Makerspace & Incubator Access**: Additional facilities or resources.

### Why Make It Configurable?
- **Token Gating**: Require a certain token balance to join or maintain membership.
- **Flexible Payment Plan**: Let members pay their membership fees over time, earning full status once they reach a target token count.
- **Community Vouching**: Ensure only positively recognized members get Citizen status.

---

## 2. Eligibility Checks

When a user attempts to apply for Citizenship, the system runs through various checks, such as:

1. **Account Status**  
   - Has the user created a valid account?
   - Are they banned or flagged?

2. **Token Balance**  
   - Does the user have the minimum required tokens (e.g., TDF30)?
   - If not, can they finance it via a monthly plan?

3. **Proof of Presence**  
   - Have they spent enough days onsite in the last X months/years?

4. **Community Vouching**  
   - Are they endorsed by enough existing members (e.g., 3 vouches)?

5. **No Reports**  
   - Check that the user hasn’t been reported or blocked by other members.

### Example Ineligibility Screen
If the user doesn’t meet one or more of these criteria, they’ll see a message explaining why they aren’t eligible yet. For instance:

> **You are not eligible to become a member just yet**  
> - You created an account (OK)  
> - You have not been reported by other members (OK)  
> - You spent at least 14 days at TDF in the past two years (Not Met)  
> - You have been vouched for by 3 other members (OK)

The user might also see their **Wallet Balance** (e.g., cEUR 245.81, TDF 1.00 total, 0.99 available) or other relevant token info.

---

## 3. Flexible Payment and Financing

Communities can configure payment options that allow members to acquire required tokens gradually:
- **One-Time Purchase**: Pay upfront to hold 30 tokens (or whatever the requirement is).
- **Monthly Financing**: Spread out the cost over a set period (e.g., 12 or 36 months).
- **Hybrid Model**: A partial token purchase plus monthly installments.

### Example: Financing Panel
> **Hold TDF30** or finance it from **€193.67 per month**  
> - Once fully paid, the user’s token balance is updated automatically.
> - Users can track their progress in the membership portal.

---

## 4. Membership Application Flow

1. **Check Requirements**: The system ensures the user meets presence, vouching, and token criteria.
2. **Connect Wallet**: If tokens are required, users link their wallets to validate token balances.
3. **Confirm Payment Plan**: The user decides whether to pay upfront or finance monthly.
4. **Submit Application**: If all checks pass, the user can finalize enrollment.
5. **Automatic Updates**: As users accumulate tokens or receive vouches, the system updates their membership status.

---

## 5. Customization and Best Practices

- **Adjust Token Threshold**: You can require fewer or more tokens based on your community’s size and economy.
- **Tailor Vouching Rules**: Set how many endorsements are needed and who can vouch.
- **Enable Multi-Currency**: Allow fiat, stablecoins, or local tokens for more payment flexibility.
- **Define Perks Clearly**: Make sure potential citizens know exactly what they gain by joining your membership club.
- **Maintain Transparency**: Display all eligibility criteria so users understand their progress or shortfall.

---

## 6. FAQ

**Q1: Can I change the name of the program from “Citizen” to something else?**  
A: Absolutely. The Citizen Program is fully configurable. Rename it to match your community’s branding or ethos.

**Q2: Do I have to use tokens?**  
A: Token gating is optional. You can also run a purely fiat-based subscription system.

**Q3: What if I want more advanced checks (e.g., tasks completed, volunteer hours)?**  
A: Integrate additional proofs like *Proof of Sweat* to track hands-on contributions. The system is flexible enough to handle many criteria.

**Q4: Can I allow partial membership for those who don’t meet all requirements yet?**  
A: Yes. Set up intermediate tiers or status levels that members can hold until they complete all steps for full Citizenship.

---

By leveraging token gating, presence tracking, community vouching, and flexible payment plans, this **Citizen Program** fosters deeper participation and long-term commitment from your members. Customize each step to match your community’s unique values and economic model.