Step 2: 사용자 지정 커넥터 초기 설정
• 주제: Power Platform에서 Ticketmaster API를 위한 사용자 지정 커넥터 생성.
• 목표: Power Platform에서 새 사용자 지정 커넥터를 빈 상태에서 생성하고, 식별 가능한 이름(예: "Ticket Master connector 17th March 2025")을 지정합니다. Ticketmaster API의 루트 API 엔드포인트인 app.ticketmaster.com을 기본 호스트 URL로 설정합니다. API 키 인증을 사용하여 보안을 구성하며, 초기에는 헤더(header)로 설정하지만, 필요에 따라 쿼리(query) 매개변수로 변경할 수 있음을 인지합니다.
• 상세 설명:
    1. Power Platform에서 새 사용자 지정 커넥터를 '빈 상태에서 생성(create from blank)' 합니다.
    2. 커넥터에 "Ticket Master connector 17th March 2025"와 같이 이름을 지정하여 나중에 쉽게 식별할 수 있도록 합니다.
    3. Ticketmaster API의 루트 API 엔드포인트인 app.ticketmaster.com을 기본 호스트 URL로 설정합니다.
    4. 보안(Security) 설정으로 이동하여 **'API 키 인증(API key authentication)'**을 선택합니다.
        ▪ 매개변수 레이블(Parameter label) 및 **매개변수 이름(Parameter name)**을 지정합니다.
        ▪ **API 키가 전달될 위치(Pass in)**를 선택하는데, 처음에는 '헤더(header)'로 설정합니다. (나중에 이 설정이 잘못되었음을 알게 될 수 있으므로, 쿼리로 변경할 가능성을 열어둡니다).
