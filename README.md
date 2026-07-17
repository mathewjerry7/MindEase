# MindEase

A privacy-first GenAI mental wellness platform. MindEase uses LLM orchestration to provide supportive, safety-guarded conversations without ever storing chat content server-side — summaries are encrypted on-device, so raw conversations never leave the user's control.

## Why

Most AI wellness tools log full conversation history server-side, which is a hard sell for anything health-adjacent. MindEase is built around data minimization from the ground up: the system is designed so there's nothing sensitive sitting in a database to breach in the first place.

## Design Principles

- **Zero server-side chat storage** — conversations are never persisted in raw form on the backend
- **On-device encrypted summaries** — only encrypted summaries leave the device, enforcing data minimization
- **HIPAA-inspired & MHMD-aligned handling** — privacy practices modeled on health-data handling standards, though the platform is not a certified medical device
- **AI safety by default** — every LLM response passes through guardrails before reaching the user

## Architecture

Built on Azure's GenAI stack:

- **Azure OpenAI** — core LLM for conversation
- **Azure Functions** — orchestration layer for prompt pipelines and guardrail checks
- **Key Vault** — secrets and encryption key management
- **Content Safety** — response-level moderation
- **Analytics pipeline** — aggregated, anonymized usage metrics to track scalability, latency, and safety KPIs without touching individual conversation content

## Safety & Guardrails

- Prompt-engineering pipeline with embedded escalation logic for crisis-adjacent language
- Hallucination-risk controls to reduce confident-but-wrong responses in a health-adjacent context
- Defined latency, scalability, and safety KPIs to inform what ships vs. what needs more guardrail work first

## Status

Architecture and orchestration design complete; iterating toward a deployable build. Not yet handling real user data in production.

## Tech Stack

`Azure OpenAI` `Azure Functions` `Key Vault` `Azure Content Safety` `Python` `Prompt Engineering`
