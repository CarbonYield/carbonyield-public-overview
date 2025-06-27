# Technical Overview

## Platform Architecture

CarbonYield is a **sale-powered, credit-regenerative platform**. It allows users to make a one-time contribution, receive internal-use-only Impact Credits, and continue guiding future impact through a structured regeneration cycle.

**Core technology stack:**

- **Frontend:** React + TypeScript + Vite
- **Styling:** Tailwind CSS
- **Animations:** Framer Motion
- **Hosting:** Netlify
- **Database & Auth:** Firebase + Firestore
- **Forms (MVP):** Formspree

---

## How the Impact Cycle Works

1. **User Contributes** — Adds funds to a pooled climate fund.
2. **Credits Issued** — User receives Impact Credits (10 per $1).
3. **Credits Assigned** — Credits are assigned to project categories (e.g., reforestation).
4. **Platform Funds Projects** — CarbonYield selects and funds verified projects within those categories.
5. **Credits Resold** — Carbon credits are resold by the platform (post-MVP).
6. **Credits Regenerated** — A portion of sale proceeds regenerate credits for past contributors.
7. **Credits Reused** — Users reuse regenerated credits to guide future categories.

> For full logic, see: [`docs/mission-summary.md`](./mission-summary.md)

---

## Regeneration & Reuse Logic

| Action       | Controlled By     | Notes                                                                 |
|--------------|-------------------|-----------------------------------------------------------------------|
| Credit Issuance | Platform         | 10 credits per $1. Internal-use-only.                                |
| Regeneration    | Platform         | Triggered by sale proceeds (post-MVP) or platform reserve (MVP).     |
| Reuse           | User             | Users reassign regenerated credits to new categories.                |
| Auto-Reuse      | Platform/User    | Triggered after 90 days of inactivity. Users can opt out.            |

---

## MVP vs Post-MVP Logic

| Phase     | Regeneration Source           | Sale Activity         | Logs Visible |
|-----------|-------------------------------|------------------------|--------------|
| MVP       | 5–10% reserve from contributions | Simulated only         | Simulated    |
| Post-MVP  | Real carbon credit sale proceeds | Active broker sale     | Real logs    |

---

## Sale & Revenue Model

- CarbonYield funds verified climate projects **below market rate**.
- Projects deliver **verified carbon credits** (e.g., Verra, Gold Standard).
- CarbonYield holds **exclusive sale rights**, but never custody.
- Sale proceeds are **retained by the platform**.
- Proceeds are split between:
  - Impact Credit regeneration (60–80%)
  - Operational support (20–40%)

Users **never receive sale revenue** or financial return.

---

## Technical Safeguards

- 🛡 Impact Credits are never redeemable or tradable
- 🛡 Sale is executed via contract — not public listing or token
- 🛡 All user interaction data (credit assignment, reuse, badges) is stored securely in Firestore
- 🛡 No financial information is collected or displayed in the app

> See [`docs/legal-ux-summary.md`](./legal-ux-summary.md) for compliance design

---

## Future Additions

Post-MVP technical upgrades may include:

- Live sale log integration
- Project developer dashboard
- Impact portfolio view (per user)
- AI-generated “impact story” summaries
