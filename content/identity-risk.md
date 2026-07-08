# ② Copilot Studio 에이전트 — 신원·Sign-in·Risky Agents (텍스트본)

원본 인터랙티브 문서: `identity-risk.html` (레포 내 서브페이지) · 대응 역할: Microsoft Entra 관리자

Copilot Studio 에이전트가 어떤 신원으로 인증하고, 그 sign-in이 어떤 로그 탭에 찍히며, 어떤 위험 리포트로 라우팅되는지를 정리.

## 신원 3축
- **사용자 대신 (OBO)** — 위임 권한으로 동작, 위험이 사용자에게 귀속.
- **자체 신원 (app-only)** — 에이전트 자신의 신원, Entra Agent ID.
- **사용자로서 (Digital Worker)** — 독립 디지털 워커 계정(`agentUser`).

## Sign-in logs 4개 탭 → 위험 라우팅
- 라우팅 기준은 탭 위치가 아니라 **Entra 객체 타입**.
- 표면(채널) → 인증 신원 → sign-in 탭 → 위험 리포트 전체 흐름을 SVG로 시각화.

## Risky Agents 탐지
- `signInSpike` 등 탐지 목록 + 유발 공식.
- 데모 테넌트 실측 + Microsoft Learn 문서 근거를 태그로 구분. 문서 근거 없는 항목은 "갭/미확정".

> ⚠️ 다수 Graph API가 `/beta` 상태 — 프로덕션 적용 전 최신 문서 재확인. (최종 확인: 2026-07-01)

주요 출처: [Entra — CA for agents](https://learn.microsoft.com/en-us/entra/identity/conditional-access/agent-id) · [Entra ID Protection — risky agents](https://learn.microsoft.com/en-us/entra/id-protection/concept-risky-agents) · [Graph — riskyAgent (beta)](https://learn.microsoft.com/en-us/graph/api/resources/riskyagent)
