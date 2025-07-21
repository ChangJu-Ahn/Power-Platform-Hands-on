Step 5: Copilot Studio 에이전트 초기 구축
• 주제: Copilot Studio 환경에서 새로운 에이전트 생성 및 기본 설정.
• 목표: Copilot Studio에서 'Events Agent'와 같은 이름으로 새 에이전트를 생성합니다. 에이전트가 수행할 작업(예: "사용자 지정 커넥터를 사용하여 예정된 이벤트에 대한 세부 정보 가져오기")에 대한 초기 지침을 정의합니다. 에이전트가 자체 학습 데이터가 아닌, 구축된 사용자 지정 커넥터에만 의존하도록 일반 지식(general knowledge) 기능을 비활성화합니다.
• 상세 설명:
    1. Copilot Studio 환경으로 이동합니다. 커넥터가 빌드된 동일한 Power Platform 환경(demo Dev 등)에 있는지 확인합니다.
    2. **'새 에이전트(New agent)'**를 생성합니다.
    3. 에이전트 이름을 "Events Agent"와 같이 지정합니다.
    4. 에이전트가 수행할 작업에 대한 초기 지침을 정의합니다. 예를 들어, "이 에이전트는 사용자 지정 커넥터를 사용하여 예정된 이벤트에 대한 세부 정보를 가져올 수 있습니다(this agent will be able to get details about upcoming events using a custom connector)"와 같은 설명을 추가합니다.
    5. 에이전트가 일반적인 지식 데이터(예: 2023년의 Oasis 정보)를 사용하지 않고, 오직 우리가 구축할 사용자 지정 커넥터를 통해서만 실시간 데이터를 조회하도록 '일반 지식(general knowledge)' 기능을 비활성화합니다. 이를 확인하기 위해 "When do Oasis play in Manchester?"와 같은 질문을 했을 때, "실시간 데이터에 접근할 수 없습니다(don't have access to realtime data)"와 같은 응답이 나와야 정상입니다.
