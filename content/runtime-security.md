# ③ AI 에이전트 런타임 위협 탐지 아키텍처

**라이브 인터랙티브 문서:** [akimcse.github.io/agent-runtime-security](https://akimcse.github.io/agent-runtime-security/) · [GitHub 레포](https://github.com/akimcse/agent-runtime-security)

> 대응 관리자 역할: **Microsoft Defender 관리자** — 포괄적인 보안 태세와 고급 위협 방지를 에이전트까지 확장.

Copilot Studio / Azure AI Foundry 에이전트의 **런타임 위협 탐지·차단** 메커니즘을 한 장으로 정리한 아키텍처 문서입니다.

## 2-레이어 구조

| 레이어 | 대상 | 설명 |
|---|---|---|
| **콘텐츠 레이어** | 모델 입출력 | 프롬프트/응답에 대한 탐지 |
| **액션 레이어** | tool 호출 (API contract) | 에이전트가 수행하는 액션에 대한 탐지 |

각 탐지의 **엔진 / 활성 솔루션 / 표출 포털**을 매핑했습니다.

## Security for AI 설정 컨트롤 플레인

- Defender 포털 **“Security for AI” 설정 커넥터**(posture · real-time protection · M365 게이트)가 어떻게 엮여 합쳐지는지 정리했습니다.
- **Copilot Studio 네이티브 인라인 차단**(→ CS Security analytics)과 **Defender 외부 탐지**(→ Defender XDR)의 구분을 명확히 했습니다.

> ⚠️ 모든 내용은 공식 Microsoft Learn 문서 기반이며, 문서에 근거가 없는 항목(예: Copilot Studio 네이티브 탐지 엔진명)은 “미명시/추론”으로 표기했습니다. 다수 기능이 Preview 상태이므로 프로덕션 적용 전 최신 문서를 재확인하세요. (최종 확인: 2026-06)

## 주요 출처 (Microsoft Learn)

- [Copilot Studio — security-agent-runtime-view](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-agent-runtime-view)
- [Copilot Studio — external-security-provider](https://learn.microsoft.com/en-us/microsoft-copilot-studio/external-security-provider)
- [Copilot Studio — external-security-webhooks-interface-developers](https://learn.microsoft.com/en-us/microsoft-copilot-studio/external-security-webhooks-interface-developers)
- [Defender for Cloud Apps — real-time-agent-protection-during-runtime](https://learn.microsoft.com/en-us/defender-cloud-apps/real-time-agent-protection-during-runtime)
- [Defender for Cloud Apps — ai-agent-inventory](https://learn.microsoft.com/en-us/defender-cloud-apps/ai-agent-inventory)
- [Defender XDR — ai-agent-detection-protection](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/ai-agent-detection-protection)
- [Defender for Cloud — ai-threat-protection](https://learn.microsoft.com/en-us/azure/defender-for-cloud/ai-threat-protection)
- [Defender for Cloud — ai-security-posture](https://learn.microsoft.com/en-us/azure/defender-for-cloud/ai-security-posture)

<div class="embed-wrap"><iframe class="live-embed" src="https://akimcse.github.io/agent-runtime-security/" title="런타임 위협 탐지 인터랙티브 문서" loading="lazy"></iframe></div>
