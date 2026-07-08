# Microsoft Agent 365 가이드북

Agent 365(에이전트를 관찰·관리·보호하는 컨트롤 플레인)를 소개하는 홈과, 세 개의 심화 문서를 서브페이지로 재구현한 단일 GitHub Pages 사이트입니다. 전체 테마는 Agent 365 공식 리소스 톤에 맞췄습니다.

**라이브: https://akimcse.github.io/agent-365-guidebook/**

## 구성

- **홈 (`index.html`)** — [Microsoft Agent 365 공식 개요 페이지](https://www.microsoft.com/ko-kr/microsoft-agent-365)의 전체 내용(개요 · 관찰가능성/거버넌스/보안 3필라 및 12개 기능 · 관리 도구 4종 · M365 E7 · 고객 평가 · FAQ)을 재구성.
- **① 에이전트 유형 분류 (`taxonomy.html`)** — 실행위치(SaaS/Endpoint/Cloud)·역할(Productivity/Action/Automation)·제작방식(Pro-code/Low-code) 3축.
- **② 에이전트 신원 · 위험 (`identity-risk.html`)** — Copilot Studio 에이전트 신원·Sign-in 로그·Risky Agents 흐름.
- **③ 런타임 위협 탐지 (`runtime-security.html`)** — Copilot Studio/Foundry 런타임 위협 탐지 아키텍처.

세 서브페이지는 원본 인터랙티브 문서를 그대로 재구현하여 사이트에 내장했으며(별도 레포/임베드 아님), 공통 사이드바와 통일된 테마를 공유합니다.

## 텍스트본

`content/` 폴더에 홈과 각 서브페이지 내용을 마크다운 텍스트로 정리했습니다.

```
index.html               홈 (공식 개요 전체)
taxonomy.html            ① 에이전트 유형 분류
identity-risk.html       ② 에이전트 신원 · 위험
runtime-security.html    ③ 런타임 위협 탐지
content/*.md             각 페이지 텍스트본
```

## 근거

모든 내용은 Microsoft Learn 공식 문서 및 [Microsoft Agent 365 (ko-kr)](https://www.microsoft.com/ko-kr/microsoft-agent-365)를 기반으로 정리했습니다.
