<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
    <img src="assets/banner-light.svg" alt="Felix Kaboto, MarTech engineer, web developer, and RevOps consultant" width="880">
  </picture>
</p>

<p align="center">
  <a href="https://felixkaboto.dev">Portfolio</a> &middot;
  <a href="https://felixkaboto.dev/case-studies">Case studies</a> &middot;
  <a href="https://felixkaboto.dev/assets/felix-kaboto-cv.pdf">CV</a> &middot;
  <a href="https://www.linkedin.com/in/felix-kaboto">LinkedIn</a> &middot;
  <a href="mailto:felixkayz001@gmail.com">Email</a>
</p>

<p align="center">
  <sub><strong>7+ years</strong> across measurement, web, and RevOps &middot; <strong>100+</strong> client accounts &middot; <strong>15 to 30%</strong> of lost conversions recovered &middot; audits cut from <strong>3 days to 2</strong></sub>
</p>

<p align="center">
  <img alt="Server-side GTM" src="https://img.shields.io/badge/Tracking-sGTM-2563eb?style=flat-square&labelColor=18181b">
  <img alt="BigQuery" src="https://img.shields.io/badge/Data-BigQuery-2563eb?style=flat-square&labelColor=18181b">
  <img alt="Next.js" src="https://img.shields.io/badge/Web-Next.js-2563eb?style=flat-square&labelColor=18181b">
  <img alt="n8n" src="https://img.shields.io/badge/Automation-n8n-2563eb?style=flat-square&labelColor=18181b">
  <img alt="Custom agents" src="https://img.shields.io/badge/AI-Custom_Agents-2563eb?style=flat-square&labelColor=18181b">
</p>

> I work on the systems a business runs on, from the site that turns a visitor into a lead, to the tracking that proves the lead was worth having, to the agent that audits all of it while I sleep.

---

<details>
<summary><strong>Selected work</strong> &nbsp;<sub>four engagements, each linking to the full write-up</sub></summary>

| Work | What I did | Result |
| --- | --- | --- |
| **[Recovering lost conversions](https://felixkaboto.dev/case-studies/server-side-tracking-migration)**<br>E-commerce and lead generation | Moved delivery server-side on GCP with first-party routing and cross-platform Conversions APIs | 15 to 30% of lost conversions recovered per client |
| **[Audit time from 3 days to 2 days](https://felixkaboto.dev/case-studies/ai-audit-agent)**<br>Internal tooling at a US agency | Broke audits into repeatable checks, drafted reports with an LLM over raw API data | Senior audit cycle cut by a third, and gaps manual review missed now surface |
| **[Audience from 45K to 100K](https://felixkaboto.dev/case-studies/mama-money-growth)**<br>African fintech remittance | Ran acquisition and lifecycle campaigns, built UTM and creator attribution | 122% growth, with channel ROI visible for the first time |
| **Bookings up 40%**<br>A coaching business | Rebuilt templates, tightened performance and technical SEO, fixed the booking path | 40% more bookings, and the owner can edit the site without me |

Full write-ups, including stack and trade-offs: **[case studies](https://felixkaboto.dev/case-studies)**.

</details>

---

<details>
<summary><strong>How the pieces connect</strong> &nbsp;<sub>architecture diagram</sub></summary>

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

</details>

<details>
<summary><strong>AI, automation, and custom agents</strong> &nbsp;<sub>agents, guardrails, results</sub></summary>

The agents handle work that is repetitive, checkable, and easy to get subtly wrong. They do not replace judgment on the review side.

```mermaid
flowchart LR
  trigger["New account or scheduled run"] --> checks["Rule-based checks"]
  checks --> llm["LLM pass over raw data"]
  llm --> report["Structured report"]
  report --> human["Technologist review"]
  human -->|"corrections"| checks
  report --> alerts["Alerts and CRM tasks"]
```

- **Audit agent** reads GA4, GTM, and platform configuration plus raw API data, then drafts a findings report for review.
- **Prioritization agent** ranks the incoming request queue and states a reason per item, saving roughly 20 hours a month.
- **Monitoring agent** watches event volume, conversion streams, and consent state, flagging drops before a client notices.

Automation around them: offline conversion sync back to ad platforms, lead routing and CRM hygiene rules, scheduled audit runs, Looker Studio refresh alerts, and webhook glue where no native integration exists.

**How they are bounded.** Rule-based checks run before any model sees data. The model reads raw API output and drafts a report; it never writes to a production container. Every output gets human sign-off. I tuned precision against real false positives for about a month, and the first version with too many checks at once was worse than the manual process it replaced.

> Audits used to take three days of senior time. The agent runs the checks and drafts the report, so a technologist spends a day reviewing findings instead of building them from scratch.

</details>

<details>
<summary><strong>How I can help</strong> &nbsp;<sub>five disciplines</sub></summary>

- **Measurement engineering.** Server-side tracking, first-party routing, Conversions APIs, consent configuration, warehouse pipelines.
- **Web development.** Next.js, React, and WordPress builds with performance, technical SEO, and form flows designed in.
- **RevOps.** CRM architecture, lifecycle stages, lead routing, data hygiene, offline conversion joins, revenue reporting.
- **AI and automation.** Custom agents for audit and triage, n8n workflows, LLM pipelines wired to real APIs.
- **Consulting.** Discovery, audits with written findings, roadmaps, standards ownership, and team training.

</details>

<details>
<summary><strong>Web work and side builds</strong> &nbsp;<sub>freelance and personal</sub></summary>

| Build | What it involved |
| --- | --- |
| Revenue marketing agency site | Multi-service site with CAPI, CRM integrations, and analytics from the start |
| Diaspora community platform | Pre-launch platform with 6 content pillars and 500+ early sign-ups |
| Small business rebuilds | WordPress and Next.js rebuilds with measurement designed in before launch |

</details>

<details>
<summary><strong>What I work with</strong> &nbsp;<sub>full stack and tools</sub></summary>

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
<summary><strong>AI and automation</strong></summary>

- Custom agents for audit, triage, and monitoring
- LLM pipelines with focused prompts over real API data
- n8n and Zapier workflow automation
- REST APIs and custom webhooks

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
<summary><strong>Privacy, marketing, and consulting</strong></summary>

- Advanced Consent Mode v2, GDPR and POPIA aligned setups
- SEO, PPC, paid social, email automation
- Discovery, requirements, and solution architecture
- Audits, roadmaps, documentation systems, mentoring

</details>

</details>

<details>
<summary><strong>Background and certifications</strong> &nbsp;<sub>tenure, remote setup, credentials</sub></summary>

Seven years across web development, MarTech, digital marketing, and revenue operations. I lead analytics engagements for enterprise clients at a US digital agency, fully remote from South Africa for four years, overlapping Cape Town mornings with US East Coast hours. I mentor four technologists and own the technical standards for tracking and data quality.

**Certifications:** Google Analytics Individual Qualification, Advanced Google Analytics, Google Ads, Looker Studio, HubSpot Data Integrations, Meta Social Media Marketing Professional.

</details>

---

## Let's talk

A rebuild, a migration, a process nobody trusts, or a repetitive job that should have been automated last year. Start with the **[portfolio](https://felixkaboto.dev)** or the **[case studies](https://felixkaboto.dev/case-studies)**, then reach me at [felixkayz001@gmail.com](mailto:felixkayz001@gmail.com) or on [LinkedIn](https://www.linkedin.com/in/felix-kaboto).

<p align="center"><sub>Last updated October 2026</sub></p>
