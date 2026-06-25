<!-- This file renders on the public org page:
     https://github.com/TicketWaveHQ
     Source: github.com/TicketWaveHQ/.github/profile/README.md -->

<div align="center">

# TicketWave HQ

**Access-decision infrastructure for ticketing, hospitality, and services.**

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

- [Three verticals, one engine](#-three-verticals-one-engine)
- [How partners use it](#-how-partners-use-it)
- [Pricing](#-pricing)
- [The repos in this org](#-the-repos-in-this-org)
- [Stack + security](#-stack--security)
- [About the company](#-about-the-company)
- [Contact](#-contact)

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

All repos in this org are currently private; public source links will be added if and when individual repos are open-sourced. The TWHQ engine sits behind multiple consumer-facing brands. The recs network at the [`2026{city}.com` domains](https://2026london.com) (Bourdain-style city guides) lives inside the monorepo under `apps/city-template`; the directory verticals (officesinleeds + the 6 leeds-* repos) stand alone in this org.

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
