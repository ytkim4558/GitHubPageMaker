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
    AWS Cloud Support Engineer and OpenSearch SME with experience across customer troubleshooting,
    analytics workloads, enterprise data platforms, mobile apps, backend systems, and AI-assisted
    support engineering workflows.
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
  <a href="#automation">Automation</a>
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

<h1 id="profile">Profile</h1>

- Name: Yongtak Kim
- Role: AWS Cloud Support Engineer / OpenSearch SME
- GitHub: [ytkim4558](https://github.com/ytkim4558/)
- LinkedIn: [Yongtak Kim](https://www.linkedin.com/in/yongtak-kim-b7553727/)
- Email: ytkim4558@gmail.com
- Korean full portfolio: [Portfolio](/portfolio/)

<h1 id="experience">Experience</h1>

<div class="company-heading">
  <img src="/assets/images/company/aws.svg" alt="AWS logo tile" loading="lazy">
  <h2>Amazon Web Services <small>Cloud Support Engineer II / Analytics · 2022-Present</small></h2>
</div>

- Provide technical support for AWS Analytics services, especially Amazon OpenSearch Service.
- Troubleshoot customer issues involving distributed systems, analytics workloads, performance, indexing, query behavior, and operational incidents.
- Collaborate with AWS service teams and internal engineers for escalation, mitigation, and long-term resolution.
- Recognized as an AWS Certified OpenSearch Subject Matter Expert in 2023.

<div class="company-heading">
  <img src="/assets/images/company/cj-olive.svg" alt="CJ OliveNetworks logo tile" loading="lazy">
  <h2>CJ OliveNetworks <small>Data Platform Senior Engineer · 2019-2022</small></h2>
</div>

- Worked on enterprise data platform migration and operation.
- Contributed to IBM Cloud Pak for Data and OpenShift migration work for a large media data platform.
- Built and maintained data collection, search, visualization, and operational components involving Solr, MongoDB, Redis, Impala, Hive, MariaDB, OpenShift, and Kubernetes.

<div class="company-heading">
  <img src="/assets/images/company/gbike.svg" alt="G.Bike logo tile" loading="lazy">
  <h2>G.Bike <small>Software Engineer · 2018-2019</small></h2>
</div>

- Developed Android/iOS app features, backend APIs, database changes, and admin tools for mobility services.
- Built and maintained scooter rental/return flows, driver-license verification, payout workflows, and manager tools.

<div class="company-heading">
  <img src="/assets/images/company/teamnova.svg" alt="Teamnova logo tile" loading="lazy">
  <h2>Teamnova <small>Mobile Development Lead · 2017-2018</small></h2>
</div>

- Led Android/iOS app development for Popiece, a travel utility app.
- Worked on exchange-rate features, crash fixes, memory-leak analysis, iOS prototype work, calendar UI, widgets, and team coordination.

<div class="company-heading">
  <img src="/assets/images/company/diotek.svg" alt="DioTek logo tile" loading="lazy">
  <h2>DioTek <small>Image Processing Engineer · 2013-2015</small></h2>
</div>

- Researched and implemented OCR and image-processing algorithms for Korean, Japanese, and Chinese text images.
- Worked on handwritten/printed text classification, ruled-line detection/removal, color enhancement, and dithering.

<div class="company-heading">
  <img src="/assets/images/company/digitalaria.svg" alt="Digital Aria logo tile" loading="lazy">
  <h2>Digital Aria <small>Software Engineer · 2011-2013</small></h2>
</div>

- Built rendering test automation and worked on context-aware smart 3D GUI research projects.
- Managed a government-funded R&D project and implemented motion/face/finger recognition related features.

<h1 id="automation">Support Automation</h1>

I design AI-assisted support workflows that connect customer context, official documentation,
internal knowledge, ticket history, and operational signals while keeping human review explicit.

- MCP workflows connecting Slack, Outlook, wiki knowledge, ticket search, and local tools.
- Support-agent persona design for customer-response drafting and troubleshooting guidance.
- Grounding rules using official documentation, URL existence checks, similar-document search, and similar-ticket search.
- Verification logic to check whether a draft answer actually matches the customer context.
- Customer issue reproduction workflows.
- Case aging triage using LLM summaries, missing-step detection, internal-note review, and escalation-readiness checks.
- Slack bot workflow that periodically summarizes cases and guides engineer or manager follow-up.

<h1 id="tools">AI Tools</h1>

## [`claude-resume`](https://github.com/ytkim4558/claude-resume)

LLM-summary-based TUI for finding and resuming Claude Code sessions. It uses a two-panel interface
and background summaries so past work can be found by meaning, not just by session ID.

## [`codex-resume`](https://github.com/ytkim4558/codex-resume)

Windows-friendly TUI for searching and resuming OpenAI Codex CLI sessions. It indexes local Codex
JSONL sessions, shows previews, and hands off to native `codex resume`.

## [`linkedin-posting-mcp`](https://github.com/ytkim4558/linkedin-posting-mcp)

Unofficial local MCP server for user-approved LinkedIn posting workflows. It is intentionally limited
to documented OAuth/profile/posting endpoints and avoids cookies, scraping, DMs, and connection automation.

<h1 id="background">Background</h1>

My career started in mobile app and backend product development, expanded into image processing and
data platforms, and now focuses on AWS analytics support and AI-assisted support engineering workflows.

The common thread is practical engineering: identify the repeated failure pattern, turn it into a tool
or operating rule, and leave enough documentation for the next human or AI agent to continue safely.
