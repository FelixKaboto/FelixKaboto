<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
    <img src="assets/banner-light.svg" alt="Felix Kaboto, MarTech engineer, web developer, and RevOps consultant" width="880">
  </picture>
</p>

<p align="center">
  <a href="https://felixkaboto.dev">Portfolio</a> &middot;
  <a href="https://www.linkedin.com/in/felix-kaboto">LinkedIn</a> &middot;
  <a href="https://x.com/FelixKaboto">X</a> &middot;
  <a href="mailto:felixkaboto@gmail.com">Email</a>
</p>

<p align="center">
  <img alt="Server-side GTM" src="https://img.shields.io/badge/Tracking-sGTM-2563eb?style=flat-square&labelColor=18181b">
  <img alt="BigQuery" src="https://img.shields.io/badge/Data-BigQuery-2563eb?style=flat-square&labelColor=18181b">
  <img alt="Next.js" src="https://img.shields.io/badge/Web-Next.js-2563eb?style=flat-square&labelColor=18181b">
  <img alt="n8n" src="https://img.shields.io/badge/Automation-n8n-2563eb?style=flat-square&labelColor=18181b">
  <img alt="RevOps" src="https://img.shields.io/badge/Ops-RevOps-2563eb?style=flat-square&labelColor=18181b">
</p>

---

> I work on the systems a business runs on, from the site that turns a visitor into a lead to the reporting that tells leadership whether any of it worked. Some engagements are a rebuild, some are a migration, some are a strategy session that ends with a roadmap and nobody touching a server.

---

## How the pieces connect

Events leave the browser once, pass through a controlled server-side container, then fan out to ad platforms, analytics, and a warehouse. Consent state travels with them, so every destination only receives what it is allowed to.

```mermaid
flowchart LR
  browser["Browser and data layer"] --> sgtm["Server-side GTM on GCP"]
  consent["Consent Mode v2"] --> sgtm
  sgtm --> capi["Conversions APIs"]
  sgtm --> ga4["GA4"]
  sgtm --> bq["BigQuery"]
  bq --> crm["CRM and offline sync"]
  bq --> dash["Looker Studio"]
```

---

## Four lanes

Each engagement starts in one lane and often pulls in a second. The list is deliberately distinct: no lane is a reworded version of another.

| Lane | What the work looks like | What it changes |
| --- | --- | --- |
| **Measurement engineering** | Server-side tracking on GCP, first-party routing, Conversions APIs, consent configuration, warehouse pipelines | Ad platforms see the conversions that actually happened, and the numbers survive scrutiny |
| **Web development** | Next.js and React builds, WordPress and PHP sites, performance work, technical SEO, booking and form flows | Pages load fast, structure stays crawlable, and forms hand clean data to the systems behind them |
| **RevOps** | CRM architecture, lifecycle stages, lead routing, data hygiene rules, offline conversion joins, revenue reporting | Sales and marketing argue about pipeline instead of arguing about whose numbers are right |
| **Consulting** | Discovery, tracking and process audits, roadmap and requirements work, standards ownership, team training | A written plan with priorities, owners, and a way to tell whether it worked |

---

## Selected work

| Sector | Lane | Problem | What I did | Result |
| --- | --- | --- | --- | --- |
| Mid-market e-commerce and lead generation | Measurement | 15 to 30 percent of conversions vanished from ad platforms after privacy changes, while the conversions were still happening | Moved delivery server-side on GCP, routed first-party events through custom subdomains, wired cross-platform Conversions APIs, layered Advanced Consent Mode v2 | 15 to 30 percent of lost conversions recovered per client, with more accurate ROAS reporting |
| A coaching business | Web | Site could take bookings but ranked poorly, loaded slowly, and gave the team no confidence in on-page structure | Rebuilt templates, tightened performance and technical SEO, restructured the booking path and content hierarchy | 40 percent more client bookings, and a site the owner can update without a developer |
| Enterprise accounts at a US digital agency | Measurement, AI | Onboarding audits took three days of senior time and still missed gaps that surfaced weeks later | Broke audits into repeatable checks, ran each through an LLM pipeline with focused prompts and raw API data, required technologist sign-off | Audit cycle cut from 3 days to 2 days, and gaps manual review kept missing are now caught |
| An African fintech remittance company | Marketing, RevOps | Needed growth across paid, organic, and creator channels with no way to see channel-level return | Ran acquisition and lifecycle campaigns, built a UTM and event framework that measured creator ROI, aligned lifecycle stages with the CRM | Audience grew from 45K to 100K followers, 122 percent, with channel ROI visible for the first time |

---

## Impact

| Metric | Value | What it means |
| --- | --- | --- |
| Conversions recovered | 15 to 30% | Lost tracking restored through server-side migrations |
| Audit speed | ~33% faster | Agent cut audits from 3 days to 2 days |
| Bookings | +40% | Rebuild plus technical SEO on a booking-led site |
| Client accounts | 100+ | End-to-end analytics and web engagements |
| Experience | 7+ years | Measurement, web, digital marketing, and technical leadership |

---

## AI systems I build

The agents handle work that is repetitive, checkable, and easy to get subtly wrong. They do not replace judgment on the review side.

```mermaid
flowchart LR
  trigger["New account or scheduled run"] --> checks["Rule-based checks"]
  checks --> llm["LLM pass over raw data"]
  llm --> report["Structured report"]
  report --> human["Technologist review"]
  human -->|"corrections"| checks
  report --> alerts["Volume-drop alerts"]
```

**What they do**

- Audit tracking setups across GA4, GTM, and platform configuration: naming, event coverage, consent state, data-layer integrity, cross-domain behaviour, conversion firing.
- Triage incoming work and replace manual prioritization, saving roughly 20 hours a month.
- Watch event volume and flag drops or broken tracking before a client notices a gap in reporting.

**How they are bounded**

Rule-based checks run before any model sees data. The model reads raw API output and drafts a report; it never writes to a production container. Every output gets human sign-off before it reaches a client. I tuned precision against real false positives for about a month before the team trusted the output, and the first version with too many checks at once was worse than the manual process it replaced.

> Audits used to take three days of senior time. The agent runs the checks, drafts the report, and a technologist reviews it in two hours. It also catches coverage gaps that manual review kept missing.

---

## Current focus

- Building a reusable server-side GTM template library so migrations stop being one-off builds.
- Widening the audit agent beyond precision work into something the team trusts without re-reading every line.
- Moving attribution out of spreadsheets and into BigQuery-first joins.

---

## What I work with

<details>
<summary><strong>Measurement and cloud</strong></summary>

- Server-Side GTM on Google Cloud Platform
- GA4, Google Tag Manager, data layer frameworks
- Conversions APIs and Enhanced Conversions
- Custom ecommerce, cross-domain, and multi-domain tracking
- App analytics and mobile measurement partners

</details>

<details>
<summary><strong>Web development</strong></summary>

- Next.js, React, TypeScript
- WordPress, PHP, Tailwind CSS
- Technical SEO, Core Web Vitals, structured data
- Booking, form, and payment flows
- Accessibility and responsive layout

</details>

<details>
<summary><strong>Data and RevOps</strong></summary>

- BigQuery, SQL, ELT pipelines
- Salesforce, HubSpot, Marketo: CRM architecture and lifecycle stages
- Lead routing, data hygiene rules, offline conversion sync
- Identity matching and attribution modelling
- Looker Studio dashboards for revenue reporting

</details>

<details>
<summary><strong>Automation and AI</strong></summary>

- n8n and Zapier workflow automation
- LLM-powered audit and triage pipelines
- REST APIs and custom webhooks
- Automated monitoring and alerting

</details>

<details>
<summary><strong>Privacy engineering</strong></summary>

- Advanced Consent Mode v2
- GDPR and POPIA aligned setups
- Consent management platform integration
- First-party data strategy

</details>

<details>
<summary><strong>Consulting and delivery</strong></summary>

- Discovery, requirements, and solution architecture
- Tracking and process audits with written findings
- Roadmaps, standards, and documentation systems
- Stakeholder communication across technical and non-technical teams
- Mentoring and team enablement

</details>

---

## Background

Seven years across web development, MarTech, digital marketing, and revenue operations. Started building sites, moved into measurement and marketing systems, and now lead analytics engagements for enterprise clients at a US digital agency while taking on web and consulting work directly. Fully remote from South Africa for four years, overlapping Cape Town mornings with US East Coast hours. I mentor four technologists and own the technical standards for tracking and data quality.

**Certifications:** Google Analytics Individual Qualification, Advanced Google Analytics, Google Ads, Looker Studio, HubSpot Data Integrations, Meta Social Media Marketing Professional.

---

## Let's talk

Four things I get asked about most: a rebuild, a migration, a process nobody trusts, or a plan that needs a second opinion. Fastest route is my portfolio: **[felixkaboto.dev](https://felixkaboto.dev)**

Or reach me directly at [felixkaboto@gmail.com](mailto:felixkaboto@gmail.com), or on [LinkedIn](https://www.linkedin.com/in/felix-kaboto).

<p align="center"><sub>Last updated October 2026</sub></p>
