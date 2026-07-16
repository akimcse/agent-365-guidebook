# ③ AI 에이전트 런타임 위협 탐지 아키텍처 (텍스트본)

원본 인터랙티브 문서: `runtime-security.html` (레포 내 서브페이지) · 대응 역할: Microsoft Defender 관리자

Copilot Studio / Azure AI Foundry 에이전트의 런타임 위협 탐지·차단은 **서로 다른 3개 계층**에서 일어납니다.

## 3계층 탐지 모델

| 계층 | 무엇을 탐지 | 엔진 | 표출 포털 | Azure 구독 | 라이선스 |
|---|---|---|---|---|---|
| ① Copilot Studio 네이티브 | UPIA·XPIA 인라인 차단(secure by default) | CS 내장 콘텐츠 보호 | CS Security analytics | 불필요 | Copilot Studio 테넌트+User |
| ② Defender for AI Services (MDC) | Jailbreak·Prompt Injection·ASCII Smuggling (모델 레벨) | Prompt Shields + Threat Intel | Defender for Cloud → XDR | **필수** | Azure 구독 + DfC 플랜 |
| ③ Agent 365 · Defender XDR | jailbreak·XPIA·시크릿 유출·tool 오용 (에이전트 런타임) | Agent 365 observability + Defender | Defender XDR | 불필요 | Microsoft Agent 365 (전제 M365 E5) |

**🎯 핵심:** "Agent 365로 jailbreak 탐지"는 Azure 구독 없이 ①+③으로 가능. 모델 수준(②)까지 원하면 Azure 구독 + MDC 플랜 필요.

## 무엇을 검사하나 — 콘텐츠·액션 2-레이어
- **콘텐츠 레이어** — 모델 입출력(프롬프트/응답)에 대한 탐지.
- **액션 레이어** — tool 호출(API contract)에 대한 탐지.
- 각 탐지의 엔진 / 활성 솔루션 / 표출 포털을 매핑.

## Security for AI 설정 컨트롤 플레인
- Defender 포털 "Security for AI" 설정 커넥터(posture · real-time protection · M365 게이트)가 어떻게 엮이는지 정리.
- Copilot Studio 네이티브 인라인 차단(→ CS Security analytics) vs Defender 외부 탐지(→ Defender XDR) 구분.

> ⚠️ 다수 기능이 Preview 상태 — 프로덕션 적용 전 최신 문서 재확인. 문서 근거 없는 항목은 "미명시/추론". (최종 확인: 2026-06)

## Jailbreak · Prompt Injection 탐지 — 계층별 라이선스 전제

"어느 계층에서 탐지하느냐"에 따라 Azure 구독(MDC) 필요 여부가 갈립니다.

| 계층 | 무엇이 탐지 | Azure 구독(MDC) 필요? | 필요 라이선스 |
|---|---|---|---|
| ① Copilot Studio 네이티브 (UPIA·XPIA 인라인 차단) | Copilot Studio 기본 내장("secure by default"), Security analytics 표출 | **아니오** | Copilot Studio 테넌트+User 라이선스 |
| ② Defender for AI Services (MDC, 모델 레벨) | Azure AI Content Safety Prompt Shields + Threat Intel (Azure OpenAI·Foundry 모델) | **예 — 필수** | Azure 구독 + Defender for Cloud 플랜 + Owner/Contributor · 토큰당 과금 |
| ③ Agent 365 / Defender XDR (에이전트 런타임) | Agent 365 observability 기반 Defender XDR, jailbreak·XPIA 등 탐지·실시간 차단 | **아니오** | Microsoft Agent 365 라이선스(사용자당 $15/mo 또는 M365 E7) · 전제 M365 E5 |

**⚠️ 2026.7.1 이관:** Copilot Studio·Foundry의 "에이전트 레벨" 탐지·실시간 보호는 Defender for Cloud Apps/Defender for Cloud에서 빠져 **Agent 365 라이선스로 이관**. 단 **모델 레벨(Azure OpenAI) jailbreak 탐지는 Defender for AI Services(Azure 구독)에 잔류**. 이관일에 기존 Block 규칙이 중단되므로 새 real-time protection 정책으로 재정의 필요.

**🎯 요약:** "Agent 365로 jailbreak 탐지"는 Azure 구독 없이 ①+③으로 가능. 모델 수준(②)까지 원하면 Azure 구독 + MDC 플랜 필요. MDC가 반드시 있어야 탐지되는 것은 아니며 "어느 레이어까지 커버하느냐"가 핵심.

라이선스 출처: [external-security-provider](https://learn.microsoft.com/en-us/microsoft-copilot-studio/external-security-provider) · [ai-threat-protection](https://learn.microsoft.com/en-us/azure/defender-for-cloud/ai-threat-protection) · [ai-agent-detection-protection](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/ai-agent-detection-protection) · [transition-agent-security-to-agent-365](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/transition-agent-security-to-agent-365) · [agent-365/overview](https://learn.microsoft.com/en-us/microsoft-agent-365/overview) · [licensing/faqs/122](https://www.microsoft.com/licensing/faqs/122)

주요 출처: [Copilot Studio — security-agent-runtime-view](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-agent-runtime-view) · [Defender for Cloud Apps — real-time agent protection](https://learn.microsoft.com/en-us/defender-cloud-apps/real-time-agent-protection-during-runtime) · [Defender XDR — ai-agent-detection-protection](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/ai-agent-detection-protection)
