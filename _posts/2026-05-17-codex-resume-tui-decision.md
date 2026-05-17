---
layout: post
current: post
cover:  assets/images/blog-cover.jpg
navigation: True
title: codex-resume TUI를 만들면서 외부 TUI 라이브러리를 쓰기로 바꾼 이유
date: 2026-05-17 14:30:00
tags: ai-workflow
class: post-template
subclass: 'post'
author: ytkim4558
---

`claude-resume`를 만들 때 가장 중요했던 기능은 단순히 과거 세션 목록을 보여주는 것이 아니었다.
핵심은 **예전 대화가 무슨 작업이었는지 LLM 요약으로 바로 알아보고, 필요한 세션으로 이어가는 것**이었다.

Claude Code의 기본 resume 화면은 세션 ID와 시간 중심이라 대화가 많아지면 찾기가 어렵다.
그래서 `claude-resume`에서는 Python Textual로 두 패널 TUI를 만들고, 백그라운드에서 `claude -p`를 호출해 각 세션을 한 줄로 요약하게 했다.
왼쪽에는 요약된 히스토리 목록을 두고, 오른쪽에는 선택한 세션의 전체 대화 내용을 보여주는 구조였다.

![claude-resume의 두 패널 TUI와 LLM 요약 화면](/assets/images/codex-resume/claude-resume-redacted.png)

위 화면처럼 왼쪽 목록은 단순 파일명이 아니라 "무슨 작업이었는지"를 보여주고, 오른쪽은 선택한 세션의 실제 대화 흐름을 바로 확인할 수 있게 했다.
민감한 세션명은 공개용 이미지에서 일반화했지만, 핵심은 **요약된 목록과 상세 대화가 동시에 보이는 구조**다.

이 방식이 좋았던 이유는 명확했다.

- 세션 ID가 아니라 "무슨 일을 하던 대화였는지"를 기준으로 찾을 수 있다.
- 긴 JSONL 로그를 직접 열어보지 않아도 된다.
- 요약은 캐시되므로 다음 실행부터 빠르게 볼 수 있다.
- UI가 두 패널로 나뉘어 있어 목록과 상세 내용을 동시에 비교할 수 있다.

## codex-resume의 첫 구현

OpenAI Codex CLI용으로 비슷한 도구인 `codex-resume`를 만들 때는 처음에 반대로 접근했다.
외부 의존성을 최소화하고 Node.js 기본 모듈만으로 동작하는 MVP를 먼저 만들었다.

처음 구현한 기능은 다음과 같았다.

- `%USERPROFILE%\.codex\sessions` 아래 JSONL 로그 스캔
- `session_meta`, `user_message`, `response_item`, `event_msg` 파싱
- 첫 사용자 메시지와 마지막 assistant 메시지로 preview 생성
- `codex resume <session-id>`로 handoff
- PowerShell/CMD wrapper 제공

이 접근은 빠르게 동작하는 장점이 있었다.
설치가 거의 필요 없고, 실제 Codex 세션을 읽어 `list`, `doctor`, `index`, `resume` 명령을 바로 검증할 수 있었다.

하지만 실제 화면을 캡처해서 보니 문제가 분명해졌다.

## 실제 화면에서 보인 문제

PowerShell에서 직접 실행한 화면은 기능적으로는 동작했지만, 도구라고 부르기엔 부족했다.

![초기 codex-resume의 dependency-free raw TUI 화면](/assets/images/codex-resume/codex-resume-raw-redacted.png)

첫 번째 문제는 **표시 폭 계산**이었다.
한글, 긴 경로, 이미지 파일명, 긴 사용자 요청이 섞이자 좌우 구분선과 텍스트가 겹쳤다.
문자열 길이와 터미널 표시 폭이 다르기 때문에 단순 `length` 기준으로는 안정적인 레이아웃을 만들기 어렵다.

두 번째 문제는 **세션 의미 파악이 어렵다**는 점이었다.
첫 사용자 메시지와 마지막 응답을 그냥 잘라 보여주면, 결국 raw 로그를 조금 예쁘게 보여주는 정도에 그친다.
`claude-resume`에서 좋았던 것은 raw preview가 아니라 LLM이 요약한 "이 세션의 의미"였다.

세 번째 문제는 **TUI 상호작용의 완성도**였다.
스크롤, 포커스, 선택 상태, 검색 입력, 상세 패널 표시 같은 요소는 직접 만들 수는 있지만, 계속 보수해야 한다.
처음부터 도구의 핵심이 TUI라면 검증된 TUI 라이브러리를 쓰는 편이 맞다.

## 결론: 외부 TUI 라이브러리는 필요하다

처음에는 dependency-free 구현이 더 단순하고 배포하기 쉽다고 봤다.
하지만 실제 화면을 보고 판단이 바뀌었다.

`codex-resume`는 단순 CLI가 아니라 **과거 AI 작업 히스토리를 찾는 브라우저**다.
그렇다면 화면 품질은 부가 기능이 아니라 핵심 기능이다.

그래서 기본 UI는 Node.js TUI 라이브러리인 `blessed` 기반으로 바꾸고, 기존 의존성 없는 picker는 fallback으로 남기는 방향으로 수정했다.

이 결정은 `claude-resume`에서 Textual을 사용한 이유와 같다.

- 목록과 상세를 안정적으로 분리하기 위해
- 키보드 이동, 스크롤, 포커스 상태를 직접 유지보수하지 않기 위해
- 세션 요약을 중심에 둔 UI를 만들기 위해
- Windows Terminal / PowerShell에서 실제로 보기 좋은 도구로 만들기 위해

## 다음 과제

`codex-resume`의 다음 단계는 `claude-resume`처럼 LLM 요약 캐시를 붙이는 것이다.

Codex 세션 로그는 `~/.codex/sessions/YYYY/MM/DD/*.jsonl` 형태로 저장되어 있고, 실제 대화는 `user_message`, `response_item`, `event_msg` 안에 들어 있다.
이 내용을 요약 provider에 넘기고, 결과를 `%USERPROFILE%\.codex\codex-resume\session-index.json` 또는 별도 summary cache에 저장하면 된다.

요약 provider는 처음부터 하나로 고정하지 않는 편이 좋다.

- OpenAI API를 쓰는 방식
- Codex CLI가 제공하는 비대화형 호출을 쓰는 방식
- 사용자가 이미 가진 다른 LLM CLI를 쓰는 방식
- 요약 없이 heuristic summary만 쓰는 fallback

중요한 것은 요약 자체보다도, 사용자가 "그때 무슨 작업을 하던 세션이지?"를 바로 알 수 있게 만드는 것이다.
`claude-resume`에서 얻은 교훈은 결국 이거였다.

세션 복구 도구의 본질은 ID를 보여주는 것이 아니라, **작업 기억을 다시 찾게 해주는 것**이다.

## 다른 AI 에이전트에게 남기는 메모

이 작업을 이어받는 AI 에이전트는 `codex-resume`를 단순 세션 ID picker로 보지 말고, **AI 작업 히스토리 브라우저**로 봐야 한다.

- 기본 TUI는 `blessed` 기반 split-pane 구조를 유지한다.
- dependency-free picker는 fallback으로만 둔다.
- 다음 핵심 작업은 LLM 요약 캐시다.
- 공개용 스크린샷은 반드시 민감한 세션명, 로컬 경로, 개인 파일명을 가린다.
- 관련 문서는 `claude-toolkit`과 `GitHubPageMaker`의 AI Workflow 글에 같이 남긴다.
