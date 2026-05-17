---
layout: page
current: english
cover:  assets/images/covers/portfolio-systems.svg
title: Portfolio
navigation: true
class: page-template
subclass: 'post page portfolio-page english-page'
---

<div id="portfolio-top" class="anchor-target"></div>

<section class="portfolio-hero">
  <p class="portfolio-eyebrow">OpenSearch · Support Automation · AI Workflow</p>
  <h2>A support engineer who turns repeated troubleshooting patterns into reliable tools.</h2>
  <p>
    AWS Cloud Support Engineer and OpenSearch SME with a background in mobile apps,
    backend systems, data platforms, and AI-assisted support engineering workflows.
  </p>
  <div class="portfolio-actions">
    <a href="https://github.com/ytkim4558/">GitHub</a>
    <a href="https://www.linkedin.com/in/yongtak-kim-b7553727/">LinkedIn</a>
    <a href="/portfolio/">Korean Portfolio</a>
  </div>
</section>

<section class="portfolio-metrics">
  <div><strong>4+ yrs</strong><span>AWS Analytics Support</span></div>
  <div><strong>OpenSearch</strong><span>Subject Matter Expert</span></div>
  <div><strong>AI</strong><span>Support Workflow Tooling</span></div>
</section>

<nav class="portfolio-toc">
  <a href="#profile">Profile</a>
  <a href="#experience">Experience</a>
  <a href="#automation">Support Automation</a>
  <a href="#tools">AI Tools</a>
  <a href="#background">Background</a>
</nav>

<aside class="portfolio-floating-nav" aria-label="Portfolio quick navigation">
  <a href="#profile">Profile</a>
  <a href="#experience">Experience</a>
  <a href="#automation">Automation</a>
  <a href="#tools">Tools</a>
  <a href="#portfolio-top">Top</a>
</aside>

# Profile

- Name: Yongtak Kim
- Role: AWS Cloud Support Engineer / OpenSearch SME
- GitHub: [ytkim4558](https://github.com/ytkim4558/)
- LinkedIn: [Yongtak Kim](https://www.linkedin.com/in/yongtak-kim-b7553727/)
- Email: ytkim4558@gmail.com
- Korean full portfolio: [Portfolio](/portfolio/)

# Experience

## Amazon Web Services

- Provide technical support for AWS analytics services, especially Amazon OpenSearch.
- Troubleshoot customer issues involving distributed systems, analytics workloads, performance, and operational behavior.
- Collaborate with service teams and internal engineers for issue escalation and long-term resolution.
- Recognized as an AWS Certified OpenSearch Subject Matter Expert in 2023.

## Data Platform / Backend / Mobile Background

- Built and operated enterprise data platform components before joining AWS.
- Worked on OpenShift migration, data pipeline operations, search systems, crawler development, and visualization systems.
- Previously developed commercial Android/iOS apps, backend features, admin tools, and image-processing related systems.

# Support Automation

Designed support-agent workflows that connect AI agents with internal knowledge and operational signals while keeping the human approval path explicit.

- MCP workflows connecting Slack, Outlook, wiki knowledge, ticket search, and local tools
- Support-agent persona design for customer-response drafting and troubleshooting guidance
- Source-grounding rules using official documentation, URL existence checks, similar-document search, and similar-ticket search
- Answer verification logic to check whether a draft actually matches the customer context
- Customer issue reproduction workflows
- Case aging triage using LLM summaries, missing-step detection, internal-note review, and escalation-readiness checks
- Slack bot workflow that periodically summarizes cases and guides engineer/manager follow-up

# AI Tools

## [`claude-resume`](https://github.com/ytkim4558/claude-resume)

LLM-summary-based TUI for finding and resuming Claude Code sessions. It uses a
two-panel interface and background summaries so past work can be found by
meaning, not just by session ID.

## [`codex-resume`](https://github.com/ytkim4558/codex-resume)

Windows-friendly TUI for searching and resuming OpenAI Codex CLI sessions. It
indexes local Codex JSONL sessions, shows previews, and hands off to native
`codex resume`.

## [`linkedin-posting-mcp`](https://github.com/ytkim4558/linkedin-posting-mcp)

Unofficial local MCP server for user-approved LinkedIn posting workflows. It is
intentionally limited to documented OAuth/profile/posting endpoints and avoids
cookies, scraping, DMs, and connection automation.

# Background

My career started in mobile app and backend product development, expanded into
image processing and data platforms, and now focuses on AWS analytics support
and AI-assisted support engineering workflows.

The common thread is practical engineering: understand the repeated failure
pattern, turn it into a tool or operating rule, and leave enough documentation
for the next human or AI agent to continue safely.
