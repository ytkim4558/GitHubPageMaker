---
layout: page
current: profile
cover:  assets/images/covers/profile-ai-support.svg
title: Profile
navigation: true
class: page-template
subclass: 'post page profile-page'
---

<section class="share-profile-hero">
  <p class="profile-eyebrow">Yongtak Kim · 김용탁</p>
  <h1>AWS CSE / OpenSearch SME who builds practical AI workflows for support engineering.</h1>
  <p>
    AWS Cloud Support Engineer로 OpenSearch 고객 트러블슈팅과 분석 워크로드 지원을 하며,
    MCP 기반 support-agent, Slack bot, 케이스 aging triage, 응답 검증, 이슈 재현 자동화 같은
    실무형 AI 워크플로를 설계하고 구현합니다.
  </p>
  <p class="profile-en">
    AWS Cloud Support Engineer and OpenSearch SME focused on customer troubleshooting,
    analytics support, and AI-assisted support engineering workflows.
  </p>
  <div class="profile-actions">
    <a href="https://github.com/ytkim4558/">GitHub</a>
    <a href="https://www.linkedin.com/in/yongtak-kim-b7553727/">LinkedIn</a>
    <a href="/portfolio/">Portfolio</a>
    <a href="/en/portfolio/">English Portfolio</a>
  </div>
</section>

<section class="profile-assistant" aria-label="Ask about Yongtak Kim">
  <div>
    <p class="profile-eyebrow">Ask this profile</p>
    <h2>이 프로필에 대해 질문하기</h2>
    <p>공개 프로필에 적힌 범위 안에서만 답하는 프로필 어시스턴트입니다. 실제 LLM API 키는 브라우저에 노출하지 않고, 백엔드가 없을 때는 정적 답변으로 동작합니다.</p>
  </div>
  <div class="profile-assistant-box">
    <div class="profile-assistant-prompts">
      <button type="button" data-profile-question="OpenSearch와 AWS Support 경험을 요약해줘">OpenSearch 경험</button>
      <button type="button" data-profile-question="AI workflow와 MCP 자동화 경험이 뭐야?">AI workflow</button>
      <button type="button" data-profile-question="대표 프로젝트를 알려줘">대표 프로젝트</button>
      <button type="button" data-profile-question="대학과 학력을 알려줘">학력</button>
    </div>
    <label for="profile-question">Question</label>
    <textarea id="profile-question" rows="3" placeholder="예: 어떤 사람인지 짧게 설명해줘"></textarea>
    <button type="button" class="profile-assistant-submit">Ask</button>
    <div class="profile-assistant-answer" aria-live="polite">
      질문을 입력하면 이 사이트에 공개된 프로필 정보를 바탕으로 답변합니다.
    </div>
  </div>
</section>

<section class="profile-grid">
  <article>
    <span>01</span>
    <h2>OpenSearch / AWS Support</h2>
    <p>
      OpenSearch SME로 고객 이슈를 분석하고, 분석 워크로드·운영 문제·에스컬레이션 흐름을 다룹니다.
    </p>
  </article>
  <article>
    <span>02</span>
    <h2>Support Agent Workflow</h2>
    <p>
      Slack, Outlook, wiki, ticket search, local tools를 MCP로 연결하고 persona·검증 규칙을 설계했습니다.
    </p>
  </article>
  <article>
    <span>03</span>
    <h2>Case Aging Triage</h2>
    <p>
      LLM 요약, 누락 단계 탐지, internal note 검토, escalation readiness check를 Slack bot으로 자동화했습니다.
    </p>
  </article>
  <article>
    <span>04</span>
    <h2>Developer Tooling</h2>
    <p>
      Claude Code와 Codex CLI 세션을 찾고 이어가기 위한 TUI 도구와 AI workflow 문서화 체계를 만들었습니다.
    </p>
  </article>
</section>

<section class="profile-featured">
  <div>
    <p class="profile-eyebrow">Selected Work</p>
    <h2>대표 작업물</h2>
  </div>
  <a href="https://github.com/ytkim4558/claude-resume">
    <strong>claude-resume</strong>
    <span>LLM 요약 기반 Claude Code 세션 피커 TUI</span>
  </a>
  <a href="https://github.com/ytkim4558/codex-resume">
    <strong>codex-resume</strong>
    <span>Windows 친화형 OpenAI Codex CLI 세션 검색/재개 도구</span>
  </a>
  <a href="https://github.com/ytkim4558/linkedin-posting-mcp">
    <strong>linkedin-posting-mcp</strong>
    <span>승인 기반 LinkedIn posting workflow용 로컬 MCP 서버</span>
  </a>
  <a href="/#engineering-notes">
    <strong>Engineering Notes</strong>
    <span>홈의 슬라이드 카드에서 AI Workflow와 최근 글을 바로 보기</span>
  </a>
</section>

<section class="profile-contact">
  <h2>공유용 링크</h2>
  <p>
    이 페이지는 제 작업을 빠르게 파악할 수 있는 공유용 프로필입니다.
    더 자세한 이력은 <a href="/portfolio/">Portfolio</a>, 영문 요약은 <a href="/en/portfolio/">English Portfolio</a>에서 확인할 수 있습니다.
  </p>
</section>
