Step 1: Ticketmaster API 탐색 및 기초 이해
• 주제: Ticketmaster API의 구조 및 이벤트 검색 기능 파악.
• 목표: Ticketmaster 개발자 API 문서 중 events API 엔드포인트와 Discovery v2 문서를 검토하고, 샘플 URL을 사용하여 브라우저에서 직접 API를 호출하여 JSON 데이터 구조를 파악합니다. 또한 size, keyword, start date/time, city와 같은 주요 파라미터를 이해하고, 실습에 사용할 API 키를 확보합니다.
• 상세 설명:
    1. 먼저, Ticketmaster 개발자 API 문서를 탐색하여 **이벤트 검색(event search)**에 대한 정보를 확인합니다. 여기에는 API 엔드포인트 (app.ticketmaster.com)와 샘플 URL이 포함되어 있습니다.
    2. 제공된 샘플 URL (app.ticketmaster.com/discovery/v2/events.json)을 브라우저에 붙여넣고 API 키를 추가하여 API를 직접 호출해 봅니다. 초기에는 size=1로 설정되어 있어 하나의 이벤트(예: Sacramento Kings vs. Phoenix Suns 경기) 데이터가 JSON 형식으로 반환되는 것을 확인할 수 있습니다.
    3. 다양한 쿼리 파라미터를 테스트하여 검색 기능을 이해합니다.
        ▪ keyword: &keyword=Oasis를 추가하여 "Oasis" 밴드 이벤트를 검색할 수 있습니다.
        ▪ start date/time: 특정 날짜 이후의 이벤트를 검색하기 위해 사용될 수 있습니다.
        ▪ city: &city=Manchester를 추가하여 특정 도시(예: 맨체스터)에서 열리는 이벤트를 필터링할 수 있습니다. 이러한 파라미터들을 조합하여 원하는 데이터를 얻는 방법을 확인합니다.
