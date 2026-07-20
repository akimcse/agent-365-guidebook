# Microsoft Agent 365 가이드북

Agent 365(에이전트를 관찰·관리·보호하는 컨트롤 플레인)를 소개하는 홈과 심화 문서로 구성된 GitHub Pages 사이트입니다. 모든 내용은 Microsoft Learn 공식 문서와 [Microsoft Agent 365 (ko-kr)](https://www.microsoft.com/ko-kr/microsoft-agent-365)를 근거로 정리했습니다.

**라이브: https://akimcse.github.io/agent-365-guidebook/**

## 구성

| 페이지 | 파일 | 내용 |
|--------|------|------|
| 홈 | `index.html` | Agent 365 공식 개요(관찰가능성·거버넌스·보안 3필라, 관리 도구, FAQ) |
| ① 에이전트 유형 분류 | `taxonomy.html` | 실행위치(SaaS/Endpoint/Cloud)·역할·제작방식(Pro/Low-code) 3축 |
| ② 에이전트 신원 · 위험 | `identity-risk.html` | 에이전트 신원·Sign-in 로그·Risky Agents 흐름 |
| ③ 데이터 보안 · Purview | `data-security.html` | 분류 엔진·라벨·정책(DLP/CC/IRM)·DSPM 집계·Audit/eDiscovery |
| ④ 런타임 위협 탐지 | `runtime-security.html` | Copilot Studio/Foundry 런타임 위협 탐지 3계층 아키텍처 |
| 부록 · 데모 시나리오 | `demo-scenarios.html` | 계층별 탐지 검증 시나리오·커스텀 에이전트 구성 |

모든 페이지는 공통 사이드바와 테마를 공유하며, 일부 페이지의 텍스트본은 `content/*.md`에 있습니다.

## 변경 이력

| 버전 | 날짜 | 요약 | 커밋 | 배포 |
|------|------|------|------|------|
| v1 | 2026-07-08 | 최초 공개본: 홈 + 심화 문서(유형 분류·신원/위험·런타임 위협 탐지) | [`ec29891`](https://github.com/akimcse/agent-365-guidebook/commit/ec29891) | [홈](https://akimcse.github.io/agent-365-guidebook/) |
| v2 | 2026-07-16 | 런타임 위협 탐지를 3계층 탐지 모델로 재구성 | [`d88b6ee`](https://github.com/akimcse/agent-365-guidebook/commit/d88b6ee) | [문서④](https://akimcse.github.io/agent-365-guidebook/runtime-security.html) |
| v3 | 2026-07-19 | 런타임 위협 탐지 실시간보호 vs 탐지·조사 섹션 정리 | [`0fcd4d3`](https://github.com/akimcse/agent-365-guidebook/commit/0fcd4d3) | [문서④](https://akimcse.github.io/agent-365-guidebook/runtime-security.html) |
| v4 | 2026-07-20 | 부록 '데모 시나리오' 추가(4계층 탐지 검증) | [`c74d9ab`](https://github.com/akimcse/agent-365-guidebook/commit/c74d9ab) | [부록](https://akimcse.github.io/agent-365-guidebook/demo-scenarios.html) |
| v5 | 2026-07-20 | 심화 문서 '데이터 보안 · Purview' 추가(런타임 위협 탐지는 ④로 이동) | [`6f39267`](https://github.com/akimcse/agent-365-guidebook/commit/6f39267) | [문서③](https://akimcse.github.io/agent-365-guidebook/data-security.html) |
