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

## 변경 이력 (Changelog)

푸시마다 갱신됩니다.

| 버전 | 날짜 | 요약 | 커밋 |
|------|------|------|------|
| v1 | 2026-07-08 | 최초 공개본: 공식 Agent 365 개요를 반영한 탭형 홈(3필라·12기능·FAQ) + 3개 심화 서브페이지(에이전트 유형 분류 · 신원/위험 · 런타임 위협 탐지) 네이티브 재구현 · A365 공식 톤 테마 통일 · 사이드바 네비게이션 · 다크모드 토글 · 전 항목 공식 출처 명시 | — |
| v2 | 2026-07-16 | 문서③ 런타임 위협 탐지를 3계층 탐지 모델(Copilot Studio 네이티브 · Defender for AI Services/MDC · Agent 365·Defender XDR)로 재구성 + 계층별 라이선스·Azure 구독·2026.7.1 이관 표 추가 | — |
| v3 | 2026-07-19 | 문서③ SECTION 03·04 정리: 실시간보호vs탐지 표에 위협 유형(차단 4종/탐지 2갈래) 통합 + MDC 알림 카탈로그 접이식 + "왜 CS jailbreak가 Defender 알림에 안 뜨나"(모델 소유권·Prompt Shields 미지원·차단규칙 억제) 3원인 카드 · SECTION 04를 온보딩/규칙/prompt evidence 단일 카드로 압축 · 종합 노트 정리 | — |
| v4 | 2026-07-20 | 문서3 SECTION 04에 '차단↔알림 설계가 층마다 다름' 콜아웃 추가: 모델-콘텐츠 층(MDC/Prompt Shields)은 차단해도 알림(Blocked/Detected 분리), 에이전트 행위 층(Agent 365 실시간 규칙)은 차단 시 알림 대신 BehaviorInfo 기록·알림은 audit 모드에서만 — 공식문서 재검증 | — |
| v5 | 2026-07-20 | 문서2(신원·위험) 제너럴 가이드화: 전체 흐름 아키텍처를 최상단으로 이동 + Sign-in 로그 4탭 섹션을 '포털에서 확인'으로 개명·최하단 배치 · 실측/데모 테넌트 내용 전량 제거 · signInSpike 테스트 특화 서술 삭제 · 각 섹션에 공식문서 출처 부착 · 핵심 원리 섹션을 넘버링 리스트로 재포맷 | — |

