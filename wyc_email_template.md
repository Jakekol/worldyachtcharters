# WYC Monthly Email Template — Reference Guide

## File to copy each month
`wyc_email_MMMYYYY.html`  → duplicate and update the fields below.

---

## Monthly update checklist

### 1. Header
- Change issue date: `May 2026` → next month
- Update broker intro quote (lines ~85–95)

### 2. Each yacht card — fields to update
| Field | Where in code |
|---|---|
| Yacht name | `Georgia` serif heading + `openEnq('NAME',...)` |
| Destination | line below yacht name |
| Year built | same line as destination |
| Guests / Cabins / Crew | spec line |
| Price | `Georgia` price figure |
| View Yacht link | `href="https://worldyachtcharters.com/fleet/SLUG"` |
| Photo gradient | `background:linear-gradient(...)` in the 200px div |
| Assigned broker key | `openEnq('NAME','JH'/'SL'/'MC',...)` |

### 3. Section headers
Change vessel category labels:
- `Featured Motor Yachts · May 2026`
- `Sailing & Catamarans · May 2026`
- `Traditional Gulets · May 2026`

---

## Broker directory (keep updated)

| Key | Name | Speciality | Email | Mobile |
|---|---|---|---|---|
| JH | James Harlow | Mediterranean | james@wyc.com | +44 7700 900123 |
| SL | Sophie Laurent | Caribbean | sophie@wyc.com | +44 7700 900789 |
| MC | Marco Conti | Sailing & Gulets | marco@wyc.com | +44 7700 900456 |

To add a new broker, add to the `BROKERS` object in the `<script>` block:
```js
XX: { name:'Full Name', role:'Speciality', email:'x@wyc.com', phone:'+44...', initials:'XX' },
```
Then reference with `openEnq('Yacht Name','XX',...)` on the Enquire button.

---

## Enquiry flow — how it works

When a reader clicks **Enquire** on any yacht:
1. A modal opens pre-filled with the yacht name and assigned broker
2. Reader fills in: name, email, phone, dates, guests, message
3. On submit, THREE things fire simultaneously:
   - **Email** opens to broker (`broker@wyc.com`) with full enquiry details
   - **SMS** opens to broker's mobile with a short summary
   - **CC email** opens to `enquiries@wyc.com` (head office copy)
4. Confirmation message shown to reader

---

## Photo gradients — colour guide by vessel type

| Type | Gradient |
|---|---|
| Motor yacht (night) | `linear-gradient(160deg,#060f1e 0%,#1a3870 100%)` |
| Superyacht | `linear-gradient(160deg,#020608 0%,#122040 100%)` |
| Motor (daylight) | `linear-gradient(160deg,#1a3060 0%,#3060a8 100%)` |
| Sailing | `linear-gradient(160deg,#1e4a8a 0%,#4a90d0 100%)` |
| Catamaran | `linear-gradient(160deg,#1060a0 0%,#40a8e0 100%)` |
| Gulet | `linear-gradient(160deg,#1a3870 0%,#3878b8 60%,#ffa030 100%)` |

---

## Sending the email

This is a standalone HTML file. To send:
- **Mailchimp**: Import HTML → paste into "Code your own" template
- **HubSpot**: New email → Drag & drop off → Custom HTML module
- **Gmail/Outlook manual send**: Open in browser → File → Print → Save as PDF, or use "Insert HTML" plugins

---
