# ① AI 에이전트 유형 분류

**라이브 인터랙티브 문서:** [akimcse.github.io/agent-type-taxonomy](https://akimcse.github.io/agent-type-taxonomy/) · [GitHub 레포](https://github.com/akimcse/agent-type-taxonomy)

엔터프라이즈 AI 에이전트를 **세 개의 독립적인 축**으로 나눕니다. 각 축은 서로 다른 통제 지점(control surface)과 거버넌스 책임을 드러냅니다. 모든 정의는 Microsoft Learn 공식 문서를 근거로 정리했습니다.

## Axis 01 — 실행 위치 기반: SaaS · Endpoint · Cloud

Microsoft는 에이전트가 “앱(SaaS)·엔드포인트·클라우드에 걸쳐(span apps, endpoints and cloud)” 확산된다고 설명하며, 이 셋을 서로 다른 실행 경계로 다룹니다.

| 유형 | 실행 위치 | 대표 예시 | 핵심 통제 경계 |
|---|---|---|---|
| **SaaS** | SaaS 공급자의 클라우드 컨트롤 플레인/테넌트에서 원격 실행 | Box·Canva·Figma·Zendesk·Zoho 등 파트너 에이전트 | 커넥터·데이터 경계 |
| **Endpoint** | Windows·macOS 디바이스에서 사용자 권한으로 직접 실행 | Claude Code·Codex CLI·Cursor·ChatGPT Desktop·Ollama | 엔드포인트·런타임 경계 |
| **Cloud** | 클라우드 호스팅 에이전트 서비스/Cloud PC에서 분리 세션으로 실행 | Foundry Agent Service·Bedrock·Vertex AI·Windows 365 for Agents | 신원·오케스트레이션 경계 |

Microsoft Defender는 실제로 “클라우드 에이전트” 탭과 “로컬 에이전트” 탭으로 이 둘을 분리해 관리합니다.

## Axis 02 — 역할 기반: Productivity · Action · Automation

Microsoft Cloud Adoption Framework는 “조직이 일반적으로 배포하는 세 가지 에이전트 범주”를 정의하며, 각 범주는 서로 다른 자율성 수준을 가집니다.

- **Productivity** — 정보 검색·종합에 초점을 맞춰 의사결정을 가속(예: Microsoft 365 Copilot Chat).
- **Action** — 정해진 워크플로 안에서 특정 작업을 수행하고 시스템 액션까지 연결(예: Copilot Studio 에이전트).
- **Automation** — 복잡한 다단계 프로세스를 최소한의 감독으로 관리(예: Microsoft Scout). 더 강한 거버넌스가 필요.

지식 지원 → 워크플로 실행 → 프로세스 자율성으로 올라가는 엔터프라이즈 설계 스펙트럼입니다.

## Axis 03 — 제작 방식 기반: Pro-code · Low-code

CAF 기술 계획 문서는 “Copilot Studio의 low-code 에이전트와 Microsoft Foundry의 pro-code 솔루션을 비교하라”고 명시적으로 두 방식을 대비합니다.

- **Pro-code** — 개발자가 SDK·프레임워크·코드로 직접 구현(예: Microsoft Foundry Agent Service, Agent Framework/LangGraph, Google Vertex AI ADK, Amazon Bedrock AgentCore). 자유도↑, 거버넌스 책임을 조직이 직접 진다.
- **Low-code** — 비개발자가 GUI·자연어·커넥터로 조립(예: Microsoft Copilot Studio, Salesforce Agentforce). 속도↑, 거버넌스를 플랫폼에 위임한다.

> 주요 출처: [CAF — AI agents](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/) · [CAF — 기술 솔루션 계획](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/technology-solutions-plan-strategy) · [Defender — Local AI agent discovery](https://learn.microsoft.com/en-us/defender-endpoint/local-agent-discovery-overview) · [Defender XDR — AI agent inventory](https://learn.microsoft.com/en-us/defender-xdr/security-for-ai/ai-agent-inventory)

<div class="embed-wrap"><iframe class="live-embed" src="https://akimcse.github.io/agent-type-taxonomy/?scoutTheme=light" title="AI 에이전트 유형 분류 인터랙티브 문서" loading="lazy"></iframe></div>
