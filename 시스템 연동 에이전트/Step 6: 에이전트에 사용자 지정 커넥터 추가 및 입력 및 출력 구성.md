Step 6: 에이전트에 사용자 지정 커넥터 추가 및 입력 및 출력 구성
• 주제: Copilot Studio 에이전트와 사용자 지정 커넥터 연동 및 대화 흐름 설정.
• 목표: Step 2에서 생성한 'Ticket Master connector'를 에이전트에 액션으로 추가합니다. City, Keyword, Start Date/Time 각 매개변수에 대한 간략한 설명을 추가합니다. 초기 설정으로 Should prompt user를 기본값(체크됨)으로 두어 사용자가 각 매개변수에 대해 개별적으로 질문받는 동작을 경험하게 합니다. 에이전트가 사용자에게 반환할 이벤트 요약 방식(예: "사용 가능한 이벤트를 글머리 기호 형식으로 요약")을 정의합니다.
• 상세 설명:
    1. Copilot Studio 에이전트의 '액션(Actions)' 섹션으로 이동하여 **'액션 추가(Add an action)'**를 클릭합니다.
    2. 생성한 **'Ticket Master connector' (예: Ticket Master connector 1703 2025)**를 찾아 에이전트에 추가합니다.
    3. 추가된 액션의 세부 설정을 위해 입력(Inputs) 섹션을 구성합니다. 각 입력 매개변수(city, keyword, start date time)에 대한 **설명(description)**을 추가합니다:
        ▪ City: "이벤트가 열릴 도시를 식별합니다. 제공되지 않으면 비워 둡니다."
        ▪ Keyword: "아티스트 이름이 제공되면 포함해야 합니다. 제공되지 않으면 비워 둡니다."
        ▪ Start Date/Time: "이벤트가 발생할 시작 날짜입니다. 예를 들어 5월 1일을 지정하면 5월 1일 이후의 이벤트를 찾습니다. 제공되지 않으면 비워 둡니다."
    4. 초기 설정으로, 각 입력 매개변수의 'Should prompt user' 옵션이 기본적으로 '체크(ticked)'된 상태로 둡니다. (이것은 나중에 사용자 경험을 개선하기 위해 변경될 것입니다).
    5. 출력(Outputs) 섹션에서, 에이전트가 사용자에게 반환할 응답의 요약 방식을 정의합니다. 예를 들어, 설명에 "Ticket Master에서 이벤트를 검색합니다. 사용 가능한 이벤트를 글머리 기호 형식으로 요약합니다(summarize the available events in bullet Mark form)"라고 입력합니다.
