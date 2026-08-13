# AI-Powered Sales Automation System

End-to-end sales automation system built with **n8n**, covering the full sales pipeline from lead generation to contract handling.

## Overview

This system automates the entire sales workflow — from finding leads to sending a signed contract — while keeping a human in the loop at every critical decision point (sending emails, approving proposals, handling contracts).

## Pipeline Stages

1. **Lead Generation** — Sourced leads via Apollo, extracted using Apify.
2. **AI-Driven Research & Personalization** — Scraped each lead's website (HTML → key pages filtered by LLM → converted to Markdown), then used an LLM to generate a personalized outreach email.
3. **Human-in-the-Loop Review** — Generated emails are sent to a Google Sheet for staff review and approval before sending, reducing the risk of AI hallucination reaching a real inbox.
4. **CRM Tracking** — Built a lightweight CRM in Notion to track each lead's status through the pipeline.
5. **Reply Handling** — Incoming replies are analyzed by an LLM to detect interest. Interested leads automatically receive a meeting booking link; uninterested leads are updated in the CRM.
6. **Meeting Handoff** — After a meeting is booked, staff is notified via Telegram and the lead receives a post-meeting form to collect details needed for the proposal.
7. **Proposal & Contract Automation** — Form data is processed by an LLM into a structured proposal draft, sent to staff for review before sending. The same approach applies to contract generation.
8. **Smart Follow-up System** — Inactive leads are automatically re-engaged with a follow-up message after a set period. High-value leads that go silent are escalated to staff instead of being handled automatically.
9. **Cost Optimization** — LLM calls are used selectively across the pipeline to keep operational cost low.

## Tools & Technologies

- **Automation:** n8n
- **Lead Sourcing:** Apollo, Apify
- **AI/LLM:** Prompt engineering, RAG-style content processing
- **Messaging:** WhatsApp, Telegram, Messenger APIs
- **Data & Integration:** HTTP requests, Webhooks, REST APIs
- **Storage/CRM:** Notion, Google Sheets
- **Database:** PostgreSQL, Supabase

## Note

This system was built and tested using a small-scale sample dataset and a personal CRM setup to validate the logic and reliability of each stage, rather than on live production data.
