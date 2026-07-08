# Microsoft Agent 365 가이드북

Agent 365(에이전트를 관찰·관리·보호하는 컨트롤 플레인)를 소개하는 홈과, 세 개의 퍼블릭 레포를 심화 서브페이지로 묶은 단일 GitHub Pages 가이드북입니다.

**🔗 라이브: https://akimcse.github.io/agent-365-guidebook/**

## 구성

- **홈** — [Microsoft Agent 365 공식 페이지](https://www.microsoft.com/ko-kr/microsoft-agent-365)의 탭 구성(개요·관찰·거버넌스·보안·라이선스)과 내용을 반영.
- **① 에이전트 유형 분류** — 실행 위치(SaaS/Endpoint/Cloud)·역할(Productivity/Action/Automation)·제작 방식(Pro-code/Low-code) 3축. → [agent-type-taxonomy](https://github.com/akimcse/agent-type-taxonomy)
- **② 에이전트 신원 · 위험** — Copilot Studio 에이전트 신원·Sign-in 로그·Risky Agents 흐름. → [agent-identity-risk](https://github.com/akimcse/agent-identity-risk)
- **③ 런타임 위협 탐지** — Copilot Studio/Foundry 런타임 위협 탐지 아키텍처. → [agent-runtime-security](https://github.com/akimcse/agent-runtime-security)

## 구조

```
index.html            앱 셸 (사이드바 + 탭형 홈 + 마크다운 라우터)
content/home.md       홈 텍스트본
content/taxonomy.md   ① 서브페이지
content/identity-risk.md  ② 서브페이지
content/runtime-security.md ③ 서브페이지
```

각 서브페이지는 마크다운 요약 + 원본 인터랙티브 문서 임베드(iframe)로 구성됩니다.

## 근거

모든 내용은 Microsoft Learn 공식 문서 및 [Microsoft Agent 365 (ko-kr)](https://www.microsoft.com/ko-kr/microsoft-agent-365)를 기반으로 정리했습니다.
