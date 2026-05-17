# Zero-Cost AI-Driven Lead Qualification Pipeline

A fully automated, no-code lead qualification pipeline built with free tools for early-stage startups. Designed to qualify B2B hydrogen industry vendors and pass only best-fit leads to a sales CRM. But this can be extended or adapted to other domains too.

[Workflow Diagram](https://miro.com/app/board/uXjVIqjpoh4=/?share_link_id=861433035153)

---

## What it does

Captures leads from multiple sources, scores them using a pre-trained NLP model for intent, filters for hydrogen-related vendors, and sends hot leads to HubSpot for sales follow-up — built entirely with no-code tools on free-tier services.

```
Lead Capture → Airtable → AI Scoring → Qualified Leads → HubSpot → Sales → Outcome Sync → Airtable
```

---

## Tech Stack (All Free Tier)

| Tool | Purpose |
|---|---|
| Airtable | Central lead database |
| Fillout / Tally.so | Website lead capture forms |
| Voiceflow | Chatbot for lead collection |
| BizConnect | Business card scanning at trade fairs |
| HubSpot Free | CRM for sales follow-up |
| Make.com | Automation between Airtable and HubSpot |
| facebook/bart-mini | Open-source NLP model for intent scoring |

---

## End-to-End Flow

### 1. Lead Collection

Leads enter from four sources: a website form (Fillout or Tally), a Voiceflow chatbot, BizConnect at events, and direct contact or social outreach.

### 2. Storage in Airtable

All incoming leads land in a Raw Leads table with metadata captured at source — message, company name, source channel, and any context from the chatbot.

### 3. AI Scoring & Filtering

A pre-trained `facebook/bart-mini` model classifies message intent. Leads are also filtered firmographically for hydrogen-related keywords (electrolyzer, fuel cell, etc.). Qualifying leads are tagged and routed to the Qualified Vendors view.

### 4. HubSpot Integration via Make.com

Only hot leads are pushed to HubSpot, where they are auto-assigned to a sales rep and managed through follow-up stages.

### 5. Outcome Logging

Closed-Won or Lost outcomes are synced back from HubSpot to Airtable for review. Cold leads can optionally be re-entered into a nurture sequence via MailerLite.

---

## Airtable Views

| View | Purpose |
|---|---|
| Raw Leads | All unprocessed incoming leads |
| Qualified Vendors | AI-scored and hydrogen-validated |
| Cold Leads | No response, available for re-nurturing |
| Closed Deals | Deal stage synced back from HubSpot |

---

## Repo Structure

```text
├── assets/
│   ├── lead_workflow_diagram.png     # Visual overview of the pipeline
│   └── screenshot_airtable.png       # Example Airtable view
├── docs/
│   └── project_info.md               # Setup and replication guide
├── README.md
└── LICENSE
```

---

## What this demonstrates

- End-to-end pipeline design across multiple tools and data sources
- Practical use of a pre-trained NLP model (BART) in a no-code workflow
- CRM integration with conditional routing logic
- Feedback loop design (outcome sync back to source database)
- Building production-style tooling with zero infrastructure cost
