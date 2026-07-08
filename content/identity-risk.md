# ② Copilot Studio 에이전트 — 신원 · Sign-in 로그 · Risky Agents

**라이브 인터랙티브 문서:** [akimcse.github.io/agent-identity-risk](https://akimcse.github.io/agent-identity-risk/) · [GitHub 레포](https://github.com/akimcse/agent-identity-risk)

> 대응 관리자 역할: **Microsoft Entra 관리자** — 에이전트 ID를 보호하고, 리소스/인터넷/다른 에이전트에 대한 액세스를 안전하게 관리.

Copilot Studio 에이전트가 **어떤 신원으로 인증하고**, 그 sign-in이 **어떤 로그 탭에 찍히며**, 최종적으로 **어떤 위험 리포트(Risky Users vs Risky Agents)로 라우팅되는지**를 한 장으로 정리한 문서입니다.

## 신원 3축

| 신원 패턴 | 설명 | Entra 표기 |
|---|---|---|
| **사용자 대신 (OBO)** | 사용자를 대신해(on-behalf-of) 위임 권한으로 동작 | 위험이 사용자에게 귀속 |
| **자체 신원 (app-only)** | 에이전트 자신의 신원으로 동작 | Entra Agent ID |
| **사용자로서 (Digital Worker)** | 독립된 디지털 워커 계정으로 동작 | `agentUser` |

## Agents ▸ Sign-in logs 4개 탭 → 위험 라우팅

- Entra의 **Sign-in logs**는 4개 탭으로 구분되며, 각 sign-in이 어느 위험 리포트로 라우팅되는지는 **탭 위치가 아니라 Entra 객체 타입**으로 결정됩니다.
- 표면(채널) → 인증 신원 → sign-in 탭 → 위험 리포트로 이어지는 **전체 흐름**을 SVG로 시각화했습니다.

## Risky Agents 탐지

- `signInSpike` 등 **Risky Agents 탐지 목록**과 각 탐지의 유발 공식을 정리했습니다.
- **데모 테넌트 실측**(M365CPI66527359, Contoso Helper) 결과와 **Microsoft Learn 문서** 근거를 태그로 구분 표기했습니다. 문서 근거가 없는 항목은 “갭/미확정”으로 명시했습니다.

> ⚠️ 다수 Graph API가 `/beta` 상태이므로 프로덕션 적용 전 최신 문서를 재확인하세요. (최종 확인: 2026-07-01)

## 주요 출처 (Microsoft Learn)

- [Entra — Conditional Access for agents (agent-id)](https://learn.microsoft.com/en-us/entra/identity/conditional-access/agent-id)
- [Entra Agent ID — design patterns](https://learn.microsoft.com/en-us/entra/agent-id/concept-agent-id-design-patterns)
- [Entra Agent ID — agent-users](https://learn.microsoft.com/en-us/entra/agent-id/agent-users)
- [Entra Agent ID — sign-in & audit logs for agents](https://learn.microsoft.com/en-us/entra/agent-id/identity-professional/sign-in-audit-logs-agents)
- [Entra ID Protection — concept-risky-agents](https://learn.microsoft.com/en-us/entra/id-protection/concept-risky-agents)
- [Entra CA — policy-autonomous-agents](https://learn.microsoft.com/en-us/entra/identity/conditional-access/policy-autonomous-agents)
- [Microsoft Graph — riskyAgent (beta)](https://learn.microsoft.com/en-us/graph/api/resources/riskyagent)
- [Microsoft Graph — agentUser](https://learn.microsoft.com/en-us/graph/api/resources/agentuser)
- [Copilot Studio — certificates configuration values](https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-certificates-configuration-values)

<div class="embed-wrap"><iframe class="live-embed" src="https://akimcse.github.io/agent-identity-risk/" title="에이전트 신원·위험 인터랙티브 문서" loading="lazy"></iframe></div>
