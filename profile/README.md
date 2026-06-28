<!-- This file renders on the public org page:
     https://github.com/TicketWaveHQ
     Source: github.com/TicketWaveHQ/.github/profile/README.md -->

<div align="center">

# TicketWave HQ

**White-label commerce for events, bookings, and online ordering. Sold under your brand, not ours.**

Multi-vertical platform for UK businesses that sell time, seats, or access.
Events, restaurants, and service bookings — one engine, one payout, one identity.

[![Live](https://img.shields.io/badge/Platform-live-22c55e?style=flat-square&labelColor=0b0620)](https://ticketwavehq.com)
[![Companies House](https://img.shields.io/badge/Companies%20House-17143167-d6d3e0?style=flat-square&labelColor=0b0620)](https://find-and-update.company-information.service.gov.uk/company/17143167)
[![EU-sovereign](https://img.shields.io/badge/Hosting-EU%E2%80%91sovereign-5b4fe5?style=flat-square&labelColor=0b0620)](#-stack--security)
[![Stripe Connect](https://img.shields.io/badge/Payments-Stripe%20Connect-635bff?style=flat-square&labelColor=0b0620)](https://ticketwavehq.com)
[![Next.js 16](https://img.shields.io/badge/Engine-Next.js%2016-000?style=flat-square&labelColor=0b0620)](#-stack--security)

[**Visit ticketwavehq.com**](https://ticketwavehq.com) · [**Apply as a partner**](https://ticketwavehq.com/partners/apply) · [**Contact**](https://ticketwavehq.com/contact)

</div>

---

## 📑 Contents

- [Two product lines under TicketWave HQ Ltd](#-two-product-lines-under-ticketwave-hq-ltd)
- [Three verticals, one engine](#-three-verticals-one-engine)
- [How partners use it](#-how-partners-use-it)
- [Pricing](#-pricing)
- [The repos in this org](#-the-repos-in-this-org)
- [Consumer brands](#-consumer-brands)
- [Stack + security](#-stack--security)
- [About the company](#-about-the-company)
- [Contact](#-contact)

---

## 🏛 Two product lines under TicketWave HQ Ltd

| Product line | What it is | Lives at | Sectors |
|---|---|---|---|
| 🎟 **TicketWave** | White-label commerce platform for events, bookings, and online ordering | [access.ticketwavehq.com](https://access.ticketwavehq.com) | Events, festivals, hospitality, food + drink, services |
| 🛰 **TicketWave Witness** | Physical-security sensing for the built environment | [witness.ticketwavehq.com](https://witness.ticketwavehq.com) | BTR, hotels, venues, universities, PBSA, councils, transport hubs, events |

Both product lines are owned by **TicketWave HQ Ltd** (Companies House [17143167](https://find-and-update.company-information.service.gov.uk/company/17143167)). They share legal entity, security posture, and EU-sovereign hosting, but ship under their own product surfaces.

---

## 🎟 Three verticals, one engine

| Vertical | Who it's for | What it ships |
|---|---|---|
| 🎫 **Events + ticketing** | Festivals, club nights, sports clubs, community events | Per-event ticket types, ticket transfers, post-event payouts to organiser's Stripe Connect account, partner referral tracking |
| 🍽 **Food** | Restaurants, takeaways, delivery | Online ordering at `/order/<slug>`, kitchen + driver routing, capabilities-flagged menus, customer accounts |
| 🛎 **Bookings + services** | Activities, classes, appointments | Slot-based booking, tiered platform fee (1.5–4%), automatic Stripe Connect payout split |

All three share the same engine: a single `platformFee` column, one customer identity, one partner identity, one Stripe Connect rail. Partners don't pick a "product" — they sign one agreement and run whichever verticals apply to their business.

---

## 🤝 How partners use it

The platform is built around **partner sovereignty**: every event, every menu, every booking belongs to the operator who created it. We're the rails; they're the brand.

1. Partner applies at [ticketwavehq.com/partners/apply](https://ticketwavehq.com/partners/apply)
2. Onboards a Stripe Connect account (Express by default; Standard available for higher-trust partners)
3. Lists their first event / menu / booking slots from the partner dashboard
4. Customers buy via the partner's TicketWave-hosted page or a custom domain
5. Partner takes their cut on each transaction; TWHQ takes the published platform fee
6. Monthly payout report is generated per Connect account, never aggregated across currencies

---

## 💰 Pricing

Single source of truth, no hidden uplift:

- **Food**: 3% flat
- **Events**: 1.5%–4% tiered by volume + risk profile
- **Bookings + services**: 1.5%–4% tiered

No SaaS subscription. No setup fee. No charge if you don't transact.

---

## 📦 The repos in this org

| Repo | What it does |
|---|---|
| **ticketwave** | The platform monorepo — dashboard, public-facing apps, partner portal, webhook handlers, Stripe Connect orchestration. Next.js 16 + Turborepo. *Private.* |
| **officesinleeds** | Reference implementation of the directory template — a Leeds workspace listings site published at [officesinleeds.com](https://officesinleeds.com). Astro 6.4 + SSR. *Private.* |
| **leeds[spa\|pizza\|cafe\|burgers\|caribbeanfood\|rent]** | Forks of the officesinleeds template, one per Leeds vertical. Same engine, different domain + dataset. *Private.* |
| **marketing-asset-gen** | Side-tool generating ad-creative bundles for partners (£19/campaign, no subscription). Astro + image pipeline. *Private.* |

All repos in this org are currently private; public source links will be added if and when individual repos are open-sourced. The TWHQ engine sits behind multiple consumer-facing brands. The Bourdain-style city-guides network lives inside the monorepo under `apps/city-template` and is the engine behind the **Citorah** consumer brand (see below); the directory verticals (officesinleeds + the 6 leeds-* repos) stand alone in this org.

---

## 🌍 Consumer brands

The TWHQ engine sits behind consumer-facing properties that are operated as separate properties with their own positioning and editorial voice.

### Citorah — city-guide network

**[citorah.com](https://citorah.com)** is the apex consumer brand for the city-guides network. Each city ships as a path under the apex:

| City | Path |
|---|---|
| London | [citorah.com/london](https://citorah.com/london) |
| Lisbon | [citorah.com/lisbon](https://citorah.com/lisbon) |
| Ibiza | [citorah.com/ibiza](https://citorah.com/ibiza) |
| Madrid | [citorah.com/madrid](https://citorah.com/madrid) |
| Barcelona | [citorah.com/barcelona](https://citorah.com/barcelona) |
| Greece | [citorah.com/greece](https://citorah.com/greece) |
| Dubai | [citorah.com/dubai](https://citorah.com/dubai) |

Seven city surfaces, one apex, one editorial voice. Runs on the same Next.js monorepo (`apps/city-template`) with runtime multi-tenancy keyed off the URL path.

---

## 🔒 Stack + security

| Layer | Choice |
|---|---|
| **Application** | Next.js 16 on Vercel (London region, `lhr1`) |
| **Database** | Neon Postgres (London region) |
| **Payments** | Stripe + Stripe Connect (Express + Standard, multi-currency) |
| **Email** | Resend (DKIM-signed, DMARC-aligned) |
| **DNS + edge** | Cloudflare for DNS, DNSSEC, CAA. Vercel as the primary edge for active traffic |
| **Bot + scraper defense** | Vercel Firewall with explicit AI-training-scraper blocks on 12 transactional zones |
| **Mail authentication** | SPF, DKIM, DMARC `quarantine`/`reject`, MTA-STS, TLS-RPT |
| **DNSSEC** | Enabled across all live production zones |
| **Org security** | 2FA enforced on every contributor account |

Single-region, single-vendor by design — observability and incident response stay tractable.

---

## 🏢 About the company

**TicketWave HQ Ltd** — UK private company limited by shares, registered in England & Wales.

- **Company number**: [17143167](https://find-and-update.company-information.service.gov.uk/company/17143167)
- **Registered office**: England & Wales
- **Founder**: Jordan Gilbert ([LinkedIn](https://www.linkedin.com/in/eu-jordangilbert/))

The TWHQ brand stays B2B-only — operator-facing, partner-facing, integration-focused. Consumer brands (the recs network, the directory verticals) are run as separate properties with their own positioning.

---

## 📬 Contact

| Audience | Where to go |
|---|---|
| **Partner applications** | [ticketwavehq.com/partners/apply](https://ticketwavehq.com/partners/apply) |
| **General enquiries** | [ticketwavehq.com/contact](https://ticketwavehq.com/contact) |
| **Security disclosure** | See [SECURITY.md](https://github.com/TicketWaveHQ/.github/blob/main/SECURITY.md) (RFC 9116 / `/.well-known/security.txt`) |
| **Press / investors** | Email via the contact page above |

---

<div align="center">

*TicketWave HQ Ltd · Companies House [17143167](https://find-and-update.company-information.service.gov.uk/company/17143167) · England & Wales*

</div>
