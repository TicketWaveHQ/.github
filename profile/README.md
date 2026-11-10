<!-- This file renders on the public org page:
     2026-11-10: five practices became two (ADR-0037, 2026-11-08); the table follows
     ticketwavehq.com's lib/practices.ts word for word. Later the same day: the seven
     new repositories, and both contact rows to hello@, as the privacy notice and
     /security give it (security@ does not exist yet; privacy@ is in no record).
     https://github.com/TicketWaveHQ
     Source: github.com/TicketWaveHQ/.github/profile/README.md

     Rewritten 2026-09-19. The previous version described this company as a
     white-label commerce and ticketing platform with two product lines, a
     pricing page and a partner programme. None of that is what TicketWave HQ
     Ltd is or does.

     It mattered more than an ordinary out-of-date page. GitHub organisation
     profiles rank, and this one carried a "Platform: live" badge linking
     straight at ticketwavehq.com, so a high-authority domain was telling
     search engines precisely the thing the company site had just stopped
     saying. It also linked to /partners/apply, which 404s, and to /pricing,
     which redirects to a different product's pricing page.

     Per the group operating model: HQ Ltd sells professional services. The
     model assigns the commerce and sensing products to IP Ltd, but IP Ltd is
     planned, not registered, so this page must not say they belong to it
     (governance ADR-0001: never assert an entity that does not exist). It did
     say that until 2026-10-07. Keep this page describing the company that
     owns this org. -->

<div align="center">

# TicketWave HQ

**Governed digital operations for UK businesses.**

Two practices under one accountable CTO, on UK and EEA infrastructure,
against controls published before you sign rather than described after you ask.

[![Companies House](https://img.shields.io/badge/Companies%20House-17143167-d6d3e0?style=flat-square&labelColor=0b0620)](https://find-and-update.company-information.service.gov.uk/company/17143167)
[![Hosting](https://img.shields.io/badge/Hosting-UK%20%2B%20EEA-3dff8e?style=flat-square&labelColor=0b0620)](https://ticketwavehq.com/sovereignty)
[![Sub-processors](https://img.shields.io/badge/Sub%E2%80%91processors-published-3dff8e?style=flat-square&labelColor=0b0620)](https://ticketwavehq.com/data-processors)

[**ticketwavehq.com**](https://ticketwavehq.com) · [**Practices**](https://ticketwavehq.com/practices) · [**Governance**](https://ticketwavehq.com/governance) · [**Contact**](https://ticketwavehq.com/contact)

</div>

---

## What this company is

**TicketWave HQ Ltd** is a UK professional services company, registered in
England and Wales, number **17143167**.

It sells consulting, implementation, agency delivery and managed services
through two client-facing practices (since 8 November 2026). It sits in a wider
group of which it is, for now, the only incorporated company. The rest of the
group is planned rather than registered.

A practice is a capability and a brand is a shop front.

| Practice | Promise | Sold through |
|---|---|---|
| **Digital** | Acquire, convert and retain customers, and create the visual and media assets they judge a business by | [VerySEOly](https://veryseoly.com): websites, search and the marketing systems behind them, built and run for UK businesses, and photography, video, brand identity and social content as its creative production |
| **Technology support and maintenance** | Support, maintain, integrate and secure the technology a business or a home depends on | [JorTech](https://www.jortech.co.uk): repairs and tech help for homes and small offices, at your door or online, and event tech and live streaming · [Dacros](https://dacros.com): managed IT, business email, networks, telecoms and data cabling, and security reviews, Cyber Essentials readiness, email-fraud protection, and UK GDPR and DPIA support, for businesses |

Integrations between business systems, database and platform migrations, Odoo
implementation, white-label delivery, security audits of deployed systems,
vendor review, disaster-recovery planning, technical due diligence and the
[fractional CTO](https://ticketwavehq.com/fractional-cto) retainer are contracted
with TicketWave HQ directly.

**[Custodiance](https://custodiance.com)**, the fourth trading name, is a pilot for regulated practices:
law firms, accountancy practices, clinics and schools. Its own site describes what it sells.

---

## Work you can read

Procurement asks for a capability statement and gets prose. These are the
working documents and tools instead: public, licensed, tested, and usable by
people who will never hire us. Several began as code that runs our own sites
and backups.

| Repository | What it is |
|---|---|
| [`eu-sovereignty-checklist`](https://github.com/TicketWaveHQ/eu-sovereignty-checklist) | The checklist we apply to our own estate before a vendor is approved, plus a verification script that runs. CC BY 4.0 |
| [`eu-sovereign-stack`](https://github.com/TicketWaveHQ/eu-sovereign-stack) | EEA and UK alternatives to common US SaaS, with the trade-offs each choice carries written down |
| [`uk-gdpr-dpa-templates`](https://github.com/TicketWaveHQ/uk-gdpr-dpa-templates) | Article 28 data processing agreements, sub-processor disclosure, and an AI processing addendum |
| [`website-care-checklist`](https://github.com/TicketWaveHQ/website-care-checklist) | What ongoing website maintenance should actually include, so a client can check whether they are getting it |
| [`astro-performance-budget`](https://github.com/TicketWaveHQ/astro-performance-budget) | A performance budget that fails the build rather than filing a warning nobody reads |
| [`static-csp`](https://github.com/TicketWaveHQ/static-csp) | A hashed Content-Security-Policy for any static build, failing the build on inline handlers and `javascript:` URLs. MIT |
| [`next-export-strip-js`](https://github.com/TicketWaveHQ/next-export-strip-js) | Removes the Next.js runtime from a static export when no page needs JavaScript, and refuses when one does. MIT |
| [`pages-to-caddy`](https://github.com/TicketWaveHQ/pages-to-caddy) | Cloudflare Pages and Netlify `_headers` and `_redirects` as Caddyfile rules, refusing any rule it cannot translate exactly. MIT |
| [`person-entity-check`](https://github.com/TicketWaveHQ/person-entity-check) | Checks that one person's profile pages agree: JSON-LD names, `sameAs` links and canonicals. MIT |
| [`serverless-backup-sentinel`](https://github.com/TicketWaveHQ/serverless-backup-sentinel) | Checks from outside that a recent backup exists in S3-compatible storage, and alarms when it does not. MIT |
| [`age-offsite-backups`](https://github.com/TicketWaveHQ/age-offsite-backups) | Encrypts backups with age before they leave the machine, and proves on another that every copy decrypts. MIT |
| [`odoo-json2`](https://github.com/TicketWaveHQ/odoo-json2) | TypeScript and Python clients for Odoo's JSON-2 API, with a migration guide from XML-RPC. MIT |

---

## How we run

**UK and EEA infrastructure by default.** Anything outside it requires a written
exception with a named owner and an expiry date. Undocumented is not one of the
available options, because it means nobody ever decided.

**The exceptions are published**, not buried. Every processor is named at
[/data-processors](https://ticketwavehq.com/data-processors) with its region and
its data protection agreement, including the ones outside the EEA and the reason
each is there. A sovereignty claim with no exception list is not one anyone
experienced will believe.

**Nineteen registers**, named individually at
[/governance](https://ticketwavehq.com/governance): entities, intercompany
agreements, transfer pricing, vendors and sub-processors, data processing,
DPIAs, AI systems, model risk, open-source IP, IP assignment, incidents, product
portfolio, retention, domains, international transfers, social presence,
credentials, recovery objectives, and services.

**AI governance treated as operational**, not forthcoming. EU AI Act Article 50
transparency obligations apply now; where a decision is automated we record
whether it is wholly or partly so, and human review has to be capable of reaching
a different answer.

---

## Contact

| For | Where |
|---|---|
| Press and partnerships | [hello@ticketwavehq.com](mailto:hello@ticketwavehq.com) |
| Data protection requests | [hello@ticketwavehq.com](mailto:hello@ticketwavehq.com) · [privacy notice](https://ticketwavehq.com/privacy) |
| Security disclosure | [hello@ticketwavehq.com](mailto:hello@ticketwavehq.com) · [scope and policy](https://ticketwavehq.com/security) |

<div align="center">
<sub>TicketWave HQ Ltd · Company no. 17143167 · Ground Floor, Radley House, Richardshaw Road, Leeds, LS28 6LE · Registered in England and Wales</sub>
</div>
