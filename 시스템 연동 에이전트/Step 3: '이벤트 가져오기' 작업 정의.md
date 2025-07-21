Step 3: '이벤트 가져오기' 작업 정의
• 주제: 커넥터 내에서 Ticketmaster 이벤트 검색 액션 구성.
• 목표: 커넥터에 'get events'라는 새 액션을 생성하여 Ticketmaster에서 이벤트를 검색하는 기능을 추가합니다. events.json URL과 함께 keyword (예: Oasis), start date/time, city (예: Manchester)와 같은 필수 쿼리 매개변수를 포함하는 요청 샘플을 가져옵니다. 또한, API에서 반환될 데이터의 예시를 제공하기 위해 size를 5로 늘려 더 많은 데이터를 반환하도록 설정한 응답 샘플을 붙여넣고 가져옵니다.
• 상세 설명:
    1. 커넥터의 정의(Definition) 섹션으로 이동하여 **새 액션(new action)**을 생성합니다.
    2. 액션 이름을 "get events"로 지정하고, **작업 ID(Operation ID)**도 "get events"로 설정합니다.
    3. 샘플 요청 생성(Create a sample request) 섹션에서 GET 메서드를 선택하고, URL에 events.json을 입력합니다. 이어서 ?keyword=Oasis&startDateTime=&city=Manchester&size=1와 같이 쿼리 파라미터를 포함한 전체 URL을 입력하고 **'가져오기(Import)'**를 클릭합니다. 이렇게 하면 keyword, start date time, city 등 입력 파라미터가 자동으로 생성됩니다.
    4. 샘플 응답 제공(Supply a sample response) 섹션에서는, 실제 API를 호출하여 얻은 응답 데이터를 활용합니다. size 파라미터 값을 5로 늘린 (예: size=5) 샘플 URL을 브라우저에서 실행하여 더 많은 데이터를 포함하는 JSON 응답을 얻습니다.
    5. 이 JSON 응답 전체를 복사하여 **샘플 응답(sample response) 입력란에 붙여넣고 '가져오기(Import)'**를 클릭합니다. 이렇게 하면 커넥터가 반환할 데이터의 구조를 파악할 수 있게 됩니다.
