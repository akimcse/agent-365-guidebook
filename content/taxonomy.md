# ① AI 에이전트 유형 분류 (텍스트본)

원본 인터랙티브 문서: `taxonomy.html` (레포 내 서브페이지)

엔터프라이즈 AI 에이전트를 세 개의 독립적인 축으로 분류. 모든 정의는 Microsoft Learn 공식 문서 근거.

## Axis 01 — 실행 위치 기반: SaaS · Endpoint · Cloud
- **SaaS** — SaaS 공급자의 클라우드 컨트롤 플레인/테넌트에서 원격 실행 (Box·Canva·Figma 등). 통제 경계: 커넥터·데이터.
- **Endpoint** — Windows/macOS 디바이스에서 사용자 권한으로 직접 실행 (Claude Code·Cursor·ChatGPT Desktop 등). 통제 경계: 엔드포인트·런타임.
- **Cloud** — 클라우드 호스팅 에이전트 서비스/Cloud PC에서 분리 세션 실행 (Foundry·Bedrock·Vertex AI). 통제 경계: 신원·오케스트레이션.

## Axis 02 — 역할 기반: Productivity · Action · Automation
- **Productivity** — 정보 검색·종합 (예: M365 Copilot Chat).
- **Action** — 워크플로 내 특정 작업 수행 (예: Copilot Studio 에이전트).
- **Automation** — 다단계 프로세스를 최소 감독으로 관리 (예: Microsoft Scout).

## Axis 03 — 제작 방식 기반: Pro-code · Low-code
- **Pro-code** — SDK·프레임워크·코드로 직접 구현 (Foundry Agent Service, Vertex AI ADK, Bedrock AgentCore). 자유도↑, 거버넌스 책임 조직.
- **Low-code** — GUI·자연어·커넥터로 조립 (Copilot Studio, Agentforce). 속도↑, 거버넌스 플랫폼 위임.

주요 출처: [CAF — AI agents](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/) · [CAF 기술 솔루션 계획](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/technology-solutions-plan-strategy) · [Defender — Local AI agent discovery](https://learn.microsoft.com/en-us/defender-endpoint/local-agent-discovery-overview)
