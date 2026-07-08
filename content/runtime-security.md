# ③ AI 에이전트 런타임 위협 탐지 아키텍처 (텍스트본)

원본 인터랙티브 문서: `runtime-security.html` (레포 내 서브페이지) · 대응 역할: Microsoft Defender 관리자

Copilot Studio / Azure AI Foundry 에이전트의 런타임 위협 탐지·차단 메커니즘을 정리.

## 2-레이어 구조
- **콘텐츠 레이어** — 모델 입출력(프롬프트/응답)에 대한 탐지.
- **액션 레이어** — tool 호출(API contract)에 대한 탐지.
- 각 탐지의 엔진 / 활성 솔루션 / 표출 포털을 매핑.

## Security for AI 설정 컨트롤 플레인
- Defender 포털 "Security for AI" 설정 커넥터(posture · real-time protection · M365 게이트)가 어떻게 엮이는지 정리.
- Copilot Studio 네이티브 인라인 차단(→ CS Security analytics) vs Defender 외부 탐지(→ Defender XDR) 구분.

> ⚠️ 다수 기능이 Preview 상태 — 프로덕션 적용 전 최신 문서 재확인. 문서 근거 없는 항목은 "미명시/추론". (최종 확인: 2026-06)

주요 출처: [Copilot Studio — security-agent-runtime-view](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-agent-runtime-view) · [Defender for Cloud Apps — real-time agent protection](https://learn.microsoft.com/en-us/defender-cloud-apps/real-time-agent-protection-during-runtime) · [Defender XDR — ai-agent-detection-protection](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/ai-agent-detection-protection)
