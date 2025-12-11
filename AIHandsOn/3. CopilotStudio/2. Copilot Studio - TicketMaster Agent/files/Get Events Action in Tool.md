```
kind: TaskDialog
inputs:
  - kind: AutomaticTaskInput
    propertyName: city
    name: city
    description: |-
      이벤트 또는 공연이 열리는 도시 이름을 인식합니다. 
      모든 도시의 이름은 영어로 변경되어야 하고, 입력된 값이 없다면 공백으로 유지합니다.
      (예: 서울 -> Seoul, 뉴욕 -> New York)
    shouldPromptUser: false

  - kind: AutomaticTaskInput
    propertyName: keyword
    name: keyword
    description: 공연 및 이벤트, 가수 이름 등의 검색 키워드를 인식합니다. 입력 값이 없다면 공백으로 유지합니다.
    shouldPromptUser: false

  - kind: AutomaticTaskInput
    propertyName: StartDateTime
    name: StartDateTime
    description: |-
      공연 또는 이벤트가 열리는 시작 날짜를 인식합니다. 입력 값이 없다면 공백으로 유지합니다.
      만약 날짜를 인식했다면, 날짜 ISO8601의 날짜 형식을 참고합니다.
      - 예시: yyyy-MM-ddthh:mm:ssz
    shouldPromptUser: false

modelDisplayName: Get Events
modelDescription: |-
  Ticketmaster에서 각종 공연 및 이벤트 정보를 조회합니다. 그리고 표현은 다음과 같은 기준을 따릅니다.

   - 조회된 정보를 각 공연 또는 이벤트 별로 Bullet Point 형태로 요약하여 표현합니다.
  - 각 내용에 Event Id는 필수로 표시합니다. 아이디는 url을 파싱하면 정확하게 알 수 있습니다.
  예를 들면, https://www.ticketmaster.com/event/Z7r9jZ1A7bZr3 URL의 Event ID는 Z7r9jZ1A7bZr3 입니다.
  - 조회된 Event 또는 공연은 간단하게라도 최대한 많이 표현합니다.
  - 이미지가 있다면, 최소 한 개는 표현합니다.
outputs:
  - propertyName: _embedded.events

  - propertyName: _links.first.href

  - propertyName: _links.last.href

  - propertyName: _links.next.href

  - propertyName: _links.self.href

  - propertyName: page.number

  - propertyName: page.totalElements

  - propertyName: page.totalPages

action:
  kind: InvokeConnectorTaskAction
  connectionReference: cr202_ticketMaster.shared_ticket-20master-20v5-5f9f1743201ee220d8-5f8162bc61f529b2c6.5944f2a81c724c719bc9f570894cff27
  connectionProperties:
    mode: Invoker

  operationId: GetEvents

outputMode: All
```
