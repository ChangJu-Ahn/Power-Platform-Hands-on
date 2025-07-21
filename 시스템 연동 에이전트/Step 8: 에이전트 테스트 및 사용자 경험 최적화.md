Step 8: 에이전트 테스트 및 사용자 경험 최적화
• 주제: 에이전트의 실제 동작 테스트, 문제점 식별 및 개선.
• 목표: "When do Oasis play Manchester?"와 같은 질문을 통해 에이전트를 테스트하고, start date/time 매개변수에 대해 ISO 8601 형식으로 날짜를 입력해야 함을 파악하고 수정합니다. 에이전트가 선택적 매개변수에 대해 계속 질문하는 문제가 발생하면, Step 6의 입력 매개변수 설정에서 Should prompt user 옵션을 **해제(unchecked)**하여 사용자 경험을 개선합니다. "I am traveling to New York in July 2025 are there any baseball tickets available and then I am heading to London in August our Oasis player and then I am heading to Vienna in August what might I go and see"와 같이 여러 개의 의도를 포함하는 복합적인 질문을 통해 생성형 오케스트레이션의 강력한 기능을 시연하고, 에이전트가 각 요청에 대해 정확한 정보를 제공하며 필요한 경우 이벤트 링크를 포함하는지 확인합니다.
• 상세 설명:
    1. 초기 테스트 및 날짜 형식 문제 해결:
        ▪ "When do Oasis play Manchester?"와 같은 질문을 시도합니다.
        ▪ 에이전트가 start date and time을 요구하면, 예를 들어 "17th June 2025"와 같이 입력합니다.
        ▪ API 호출이 400 오류와 함께 실패할 수 있습니다. 이는 start date time 매개변수가 ISO 8601 형식(YYYY-MM-DDTHH:MM:SSZ와 같은 형식, 예: 2025-06-17T00:00:00Z)을 요구하기 때문입니다.
        ▪ 액션의 입력 설정으로 돌아가 start date time 매개변수의 설명에 **"ISO 8601 형식 (예: YYYY-MM-DDTHH:MM:SSZ)"**임을 명시합니다. 이 설명 업데이트 후 다시 시도하면 올바른 형식으로 날짜를 변환하여 이벤트를 조회할 수 있습니다.
    2. 사용자 경험 최적화 (Should prompt user 해제):
        ▪ "Kylie Minogue은 언제 공연하나요?"와 같은 질문을 던졌을 때, 에이전트가 계속해서 start date and time, city와 같은 선택적 매개변수에 대해 반복적으로 질문하는 것을 경험할 수 있습니다. 이는 Should prompt user 옵션이 체크되어 있기 때문입니다.
        ▪ 이러한 반복적인 질문은 사용자 경험을 저해하므로, 액션의 입력(Inputs) 설정으로 돌아가 city, keyword, start date/time 모든 입력 매개변수에 대해 'Should prompt user' 옵션을 '체크 해제(unchecked)' 합니다.
        ▪ 변경 사항을 저장한 후, "다가오는 Oasis 티켓은 언제인가요?"와 같은 질문을 다시 하면, 에이전트가 city나 start date/time에 대해 묻지 않고 바로 결과를 반환하는 것을 확인할 수 있습니다.
    3. 다중 의도(Multi-intent) 쿼리 시연:
        ▪ 생성형 오케스트레이션의 강력한 기능을 시연하기 위해, 다음과 같은 복합적인 질문을 시도합니다: "저는 2025년 7월에 뉴욕으로 여행하는데 야구 티켓이 있나요? 그리고 8월에 런던에 가는데 Oasis가 공연하나요? 그리고 8월에 비엔나에 가는데 무엇을 볼 수 있을까요?"
        ▪ 에이전트는 이 하나의 질문에서 **세 가지 개별적인 요청(뉴욕 야구, 런던 Oasis, 비엔나 이벤트)**을 식별합니다.
        ▪ get events 커넥터가 세 번 실행되고, 각 요청에 대한 결과가 하나의 통합된 응답으로 사용자에게 제공됩니다. 예를 들어, 뉴욕 야구 티켓 없음, 런던 Oasis 공연 정보, 비엔나의 다양한 아티스트 공연 정보가 포함될 수 있습니다.
        ▪ 이 과정은 생성형 오케스트레이션 덕분에 다른 일반 토픽을 비활성화하더라도 언어 모델이 사용자 요청에 따라 최적의 액션을 스스로 판단하고 실행하여 복잡한 대화 흐름을 처리할 수 있음을 보여줍니다.
