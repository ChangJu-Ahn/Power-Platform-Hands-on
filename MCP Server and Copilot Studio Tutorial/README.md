# Microsoft Copilot Studio ❤️ MCP
Microsoft Copilot Studio ❤️ MCP 랩에 오신 것을 환영합니다. 이 랩에서는 MCP 서버를 배포하는 방법과 Microsoft Copilot Studio에 추가하는 방법을 학습합니다.

## ❓ What is MCP?
[Model Context Protocol (MCP)](https://modelcontextprotocol.io/introduction)는 애플리케이션이 LLM에 컨텍스트를 제공하는 방법을 표준화하는 오픈 프로토콜입니다. 이 프로토콜은 [Anthropic](https://www.anthropic.com/)에서 정의했습니다. MCP는 AI 모델을 다양한 데이터 소스와 도구에 연결하는 표준화된 방법을 제공합니다. 이를 통해 제작자는 기존 지식 서버와 API를 Copilot Studio에 직접 통합할 수 있습니다.
현재, Copilot Studio는 Tools(도구)만 지원합니다. 현재 기능에 대한 자세한 내용은 [aka.ms/mcsmcp](https://aka.ms/mcsmcp)를 참고하세요. 현재 알려진 문제점과 향후 개선 사항은 [여기](#known-issues-and-planned-improvements)에서 확인할 수 있습니다.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8e074fea-dcb6-49f5-8bc2-e6d476b42e94" />

> 이미지와 관련된 원본은 [여기](https://www.claudemcp.com/ko/blog/mcp-vs-api)에서 참고할 수 있습니다.

## 🆚 MCP vs Connectors
✅ MCP는 언제 사용하나요?

AI 모델과 다양한 데이터 소스 또는 도구를 표준화된 방식으로 연결해야 할 때 사용합니다.
예를 들어, Copilot Studio에서 외부 API나 지식 서버를 직접 통합하고 싶을 때 MCP가 적합합니다.
MCP는 Model Context Protocol을 기반으로 하며, LLM이 컨텍스트를 이해하고 활용할 수 있도록 돕습니다.


✅ 커넥터는 언제 사용하나요?

Power Platform에서 기존의 **데이터 소스(예: Dynamics 365, SharePoint, SQL 등)**와 연결할 때 사용합니다.
커넥터는 비즈니스 애플리케이션 통합에 특화되어 있으며, 데이터 작업과 워크플로우 자동화에 강점이 있습니다.


✅ MCP가 커넥터를 대체하나요?

아니요. MCP는 커넥터를 대체하지 않습니다.
MCP 서버는 **커넥터 인프라**를 기반으로 제공되므로, 두 기술은 함께 사용됩니다.
MCP 서버는 커넥터 인프라를 활용해 엔터프라이즈 보안 및 거버넌스 제어를 적용할 수 있습니다:

- V-net 통합 기능: https://learn.microsoft.com/power-platform/admin/vnet-support-overview
- Power Platform DLP 정책: https://learn.microsoft.com/power-platform/admin/wp-data-loss-prevention
- Custom Connector 보호: https://learn.microsoft.com/connectors/custom-connectors/#2-secure-your-api


따라서 **MCP + 커넥터** = 더 강력한 통합입니다.

## ⚙️ Prerequisites

- Visual Studio Code installed ([link](https://code.visualstudio.com/download))
- Node v22 (ideally installed via [nvm for Windows](https://github.com/coreybutler/nvm-windows) or [nvm](https://github.com/nvm-sh/nvm))
- Git installed ([link](https://git-scm.com/downloads))
- Docker installed ([link](http://aka.ms/azure-dev/docker-install))
- Azure Developer CLI installed ([link](https://learn.microsoft.com/azure/developer/azure-developer-cli/install-azd))
- Azure Subscription (with payment method added)
- GitHub account
- Copilot Studio trial or developer account

## ➕ 템플릿 기반의 신규 깃럽 리포 생성하기

1. https://github.com/microsoft/mcsmcp 깃헙 리포 접속
1. `Use this template` 선택
   <img width="1710" height="516" alt="image" src="https://github.com/user-attachments/assets/35c54192-462b-4feb-b199-d586963b631f" />

3. `Create a new repository` 선택

    <img width="357" height="237" alt="image" src="https://github.com/user-attachments/assets/b614bb38-b73e-441d-9e0b-172addb1b255" />


1. 알맞은 `Owner`를 선택(보통은 다음과 같이 본인으로 지정)
   <img width="806" height="275" alt="image" src="https://github.com/user-attachments/assets/27800d87-c2ee-4e44-ac59-23ac88cf703a" />

1. Give it a `Repository name`
1. Optionally you can give it a `Description`
1. Select `Private`
1. Select `Create repository`

    This will take a little while. After it's done, you will be directed to the newly created repository.
