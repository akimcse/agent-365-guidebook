# ③ AI 에이전트 런타임 위협 탐지 아키텍처 (텍스트본)

원본 인터랙티브 문서: `runtime-security.html` (레포 내 서브페이지) · 대응 역할: Microsoft Defender 관리자

Copilot Studio / Azure AI Foundry 에이전트의 런타임 위협 탐지·차단은 **서로 다른 3개 계층**에서 일어납니다. 계층마다 탐지 엔진 · 커넥터 · 시그널 흐름 · 표출 포털 · 라이선스가 다릅니다.

## SECTION 01 — 3계층 탐지 아키텍처 (시그널 소스 → 탐지 엔진 → 커넥터 게이트 → 표출 포털)

- **시그널 소스**: 에이전트 런타임 파이프라인 (입력 프롬프트 → 모델 생성·응답 → 툴 선택 → 툴 실행) · 콘텐츠 축 / 액션 축.
- **Layer 1 콘텐츠(CS 네이티브)** → 커넥터 불필요 → CS Security analytics.
- **Layer 2 모델(Prompt Shields → Defender for AI)** → Defender for Cloud 플랜(Azure) → Defender XDR.
- **Layer 3 액션(Agent 365 · XDR)** → Copilot Studio RTP 커넥터(PPAC) / Agent 365·M365 App 커넥터 → Defender XDR.
- **M365 App Connector = linchpin**: 이 게이트를 통과해야 alert·조사·Advanced Hunting 표출 (Agent 365 observability 로그 수집).

## SECTION 02 — 계층별 상세

| 계층 | 탐지·엔진 | 표출 포털 | Azure 구독 | 라이선스 |
|---|---|---|---|---|
| 1. Copilot Studio 네이티브 | UPIA·XPIA 인라인 차단(secure by default) · **엔진 공식 미명시**(Prompt Shields 여부 미확인) | CS Security analytics | 불필요 | Copilot Studio 테넌트+User |
| 2. Prompt Shields → Defender for AI (모델 레벨, MDC) | **탐지·차단: Azure AI Content Safety Prompt Shields**(UPIA·XPIA·ASCII Smuggling) → **알림: Defender for AI**가 "blocked/detected by Prompt Shields" alert 표출 | Defender for Cloud → XDR | **필수** + DfC 플랜·토큰과금 | Azure 구독 + Owner/Contributor |
| 3. Agent 365 · Defender XDR (에이전트 런타임) | Agent 365 observability 기반 Defender 분석 · jailbreak·XPIA·시크릿 유출·tool 오용 · 실시간 차단 | Defender XDR (Incidents·Advanced Hunting) | 불필요 (M365 커넥터 기반) | Microsoft Agent 365 (전제 M365 E5) |

**핵심:** "Agent 365로 jailbreak 탐지"는 Azure 구독 없이 1+3으로 가능. 모델 수준(2)까지 원하면 Azure 구독 + MDC 플랜 필요. **중요:** Layer 2에서 실제 탐지·차단은 **Prompt Shields(Azure AI Content Safety)** 가 하고, **Defender for AI**는 그 결과를 alert로 표출하는 **별개 서비스**입니다 — 하나로 합쳐 이해하면 안 됩니다. (BLOCKED/DETECTED 알림 분리가 그 증거)

**2026.7.1 이관(검증됨):** 에이전트 레벨(Copilot Studio·Foundry 에이전트) 탐지·실시간 보호는 Defender for Cloud Apps/Defender for Cloud → **Agent 365 라이선스로 이관**. 단 **모델 레벨(Azure OpenAI 등 Foundry Models) jailbreak 탐지는 Defender for AI Services(Azure 구독)에 잔류**. 이관일에 기존 Block 규칙 중단 → 새 real-time protection 정책으로 재정의 필요.

출처: [external-security-provider](https://learn.microsoft.com/en-us/microsoft-copilot-studio/external-security-provider) · [ai-threat-protection](https://learn.microsoft.com/en-us/azure/defender-for-cloud/ai-threat-protection) · [alerts-ai-workloads](https://learn.microsoft.com/en-us/azure/defender-for-cloud/alerts-ai-workloads) · [content-safety/jailbreak-detection](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/concepts/jailbreak-detection) · [ai-agent-detection-protection](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/ai-agent-detection-protection) · [transition-agent-security-to-agent-365](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/transition-agent-security-to-agent-365) · [agent-365/overview](https://learn.microsoft.com/en-us/microsoft-agent-365/overview) · [licensing/faqs/122](https://www.microsoft.com/licensing/faqs/122)

## SECTION 03 — Defender "Security for AI" 설정 커넥터

- Defender 포털 System > Settings > Security for AI: posture 그룹 + real-time protection 그룹, 각 그룹에 에이전트 유형별 커넥터.
- **M365 App 커넥터 = linchpin** — Agent 365 observability 로그(CS·Foundry 에이전트 신호)를 수집해 alert·조사·Advanced Hunting을 Defender 포털로 통합.

> Preview 상태 기능 다수 — 프로덕션 적용 전 최신 문서 재확인. (최종 확인: 2026-07)

주요 출처: [security-agent-runtime-view](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-agent-runtime-view) · [real-time-agent-protection-during-runtime](https://learn.microsoft.com/en-us/defender-cloud-apps/real-time-agent-protection-during-runtime) · [ai-agent-detection-protection](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/ai-agent-detection-protection)