# Security Policy

## Reporting Security Vulnerabilities

We take the security of TicketWave and its ecosystem seriously. If you believe you have found a security vulnerability in any TicketWave HQ property — the platform, partner dashboard, public-facing apps, or any service we operate — we appreciate your help in disclosing it to us responsibly.

This policy is published per [RFC 9116](https://www.rfc-editor.org/rfc/rfc9116) and matches the `/.well-known/security.txt` file served at [access.ticketwavehq.com](https://access.ticketwavehq.com/.well-known/security.txt).

---

## Where to Report

Email: **security@ticketwavehq.com**

- PGP key available on request (reply to your initial email and we will share a current public key + fingerprint).
- Please do **not** report security issues via GitHub Issues, public PRs, social media, or the general contact form.
- If you do not receive an acknowledgement within 24 hours, please resend — mail delivery occasionally fails silently.

When reporting, please include:

- A description of the issue and its potential impact.
- Steps to reproduce, including any proof-of-concept code, screenshots, or HTTP requests/responses.
- The affected endpoint, subdomain, or component.
- Your name or handle (if you would like to be credited) and a contact address we can reply to.

---

## Scope

The following properties are **in scope** for responsible disclosure:

- `ticketwavehq.com` and all subdomains (including `access.ticketwavehq.com`)
- Any production service operated by TicketWave HQ Ltd and reachable from the public internet
- Mobile-web flows, partner dashboard, customer purchase flows, webhook handlers, Stripe Connect orchestration
- Authentication, authorisation, and session-management surfaces across the above

The following are **out of scope**:

- Social engineering of TicketWave HQ staff, partners, or customers (including phishing, vishing, smishing)
- Physical attacks against TicketWave HQ or its suppliers
- Denial-of-service (DoS / DDoS) testing of any kind, including volumetric, application-layer, or resource-exhaustion attacks
- Third-party services we depend on (Stripe, Vercel, Neon, Cloudflare, Resend, etc.) — please report those directly to the relevant vendor
- Findings derived from automated scanners with no demonstrated impact (e.g. missing headers without an exploitable consequence)
- Reports about software versions without a working proof of concept
- Self-XSS, clickjacking on pages with no sensitive actions, and similar low-severity issues

---

## Response Timeline

We commit to the following timelines for in-scope reports submitted in good faith:

| Stage | Target |
|---|---|
| Acknowledgement of receipt | Within **24 hours** |
| Initial triage + severity assessment | Within **5 working days** |
| Fix deployed for **high** or **critical** severity issues | Within **30 days** |
| Fix deployed for **medium** or **low** severity issues | Best effort, communicated in our reply |
| Public disclosure / credit | Coordinated with the reporter after the fix is live |

If we cannot meet a timeline, we will tell you why and agree a revised one with you.

---

## Safe Harbour

We will not pursue legal action against security researchers who:

- Make a good-faith effort to comply with this policy.
- Report findings promptly and give us a reasonable opportunity to remediate before any public disclosure.
- Avoid privacy violations, destruction of data, or disruption of service.
- Only interact with accounts you own, or with the explicit permission of the account holder.

We do **not** authorise:

- Testing that disrupts, degrades, or interrupts service for our partners or customers.
- Accessing, exfiltrating, modifying, or destroying data that is not yours.
- Any activity that violates UK law, including the Computer Misuse Act 1990.
- Using findings for extortion, demanding payment under threat of disclosure, or any other coercive use.

If you are unsure whether a particular test is in scope, email us **before** you run it.

---

## Bug Bounty

We do **not** currently operate a paid bug bounty programme.

We do credit reporters who follow this policy at [ticketwavehq.com/trust/security-acknowledgments](https://ticketwavehq.com/trust/security-acknowledgments), unless you ask us to keep your report anonymous. A short hall-of-fame entry includes your name or handle, the date of disclosure, and (optionally) a one-line description of the class of issue.

---

## Contact Summary

- **Security disclosure**: security@ticketwavehq.com
- **Acknowledgement window**: 24 hours
- **`security.txt`**: [access.ticketwavehq.com/.well-known/security.txt](https://access.ticketwavehq.com/.well-known/security.txt)
- **Policy version**: 2026-06-25

---

*TicketWave HQ Ltd · Companies House [17143167](https://find-and-update.company-information.service.gov.uk/company/17143167) · England & Wales*
