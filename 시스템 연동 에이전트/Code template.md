IFLd7Lvz7ZNTI2qnCnJz8yiYOABJ4sgg

### 첫 번째
1. Get Events - 일반 이벤트 리스트(전체)
   ```
	https://app.ticketmaster.com/discovery/v2/events.json?apikey={YourOwnAPIKey}
   ```

2. Get Events - 일반 이벤트 리스트에 파라미터 추가
 ```
	https://app.ticketmaster.com/discovery/v2/events.json?keyword=BTS&StartDateTime=&city=Seoul&size=2
```

### 두 번째
1. Get Events in Detail - 일반 리스트에서 나온 값을 더 상세하게 조회
```
	https://app.ticketmaster.com/discovery/v2/events/G5vVZbowl3fyp?apikey={YourOwnAPIKey}
```
```
	https://app.ticketmaster.com/discovery/v2/events/{EventId}
```

<img width="557" height="290" alt="image" src="https://github.com/user-attachments/assets/cd1c6c10-e55a-4232-9565-727d24940737" />

</br>

### Get Event in detail

```
kind: TaskDialog
inputs:
  - kind: AutomaticTaskInput
    propertyName: EventId
    description: 공연 또는 이벤트를 상세하게 조회하기 위해 필요한 이벤트 ID입니다.

modelDisplayName: Get Event in detail
modelDescription: |-
이벤트 또는 공연 정보를 상세하게 조회합니다. 다음과 같은 규칙을 따릅니다.
- 결과를 bullet point 형태로 표현합니다.
- 조회된 정보는 모두 빠짐없이 표현합니다.
outputs:
  - propertyName: _embedded.venues

  - propertyName: _links.self.href

  - propertyName: _links.venues

  - propertyName: ageRestrictions.id

  - propertyName: ageRestrictions.legalAgeEnforced

  - propertyName: classifications

  - propertyName: dates.spanMultipleDays

  - propertyName: dates.start.dateTBA

  - propertyName: dates.start.dateTBD

  - propertyName: dates.start.dateTime

  - propertyName: dates.start.localDate

  - propertyName: dates.start.localTime

  - propertyName: dates.start.noSpecificTime

  - propertyName: dates.start.timeTBA

  - propertyName: dates.status.code

  - propertyName: dates.timezone

  - propertyName: id

  - propertyName: images

  - propertyName: info

  - propertyName: locale

  - propertyName: name

  - propertyName: pleaseNote

  - propertyName: promoter.description

  - propertyName: promoter.id

  - propertyName: promoter.name

  - propertyName: promoters

  - propertyName: sales.public.endDateTime

  - propertyName: sales.public.startDateTime

  - propertyName: sales.public.startTBA

  - propertyName: sales.public.startTBD

  - propertyName: test

  - propertyName: ticketing.allInclusivePricing.enabled

  - propertyName: ticketing.id

  - propertyName: ticketing.safeTix.enabled

  - propertyName: ticketLimit.id

  - propertyName: ticketLimit.info

  - propertyName: type

  - propertyName: url

action:
  kind: InvokeConnectorTaskAction
  connectionReference: cr202_ticketMaster.shared_ticket-20master-20v3-5f9f1743201ee220d8-5f8162bc61f529b2c6.cbcd81b8b6c14d5ba0be84972c5e7fab
  connectionProperties:
    mode: Maker

  operationId: GetEventDetail

outputMode: All
```
### Get Events
```
kind: TaskDialog
inputs:
  - kind: AutomaticTaskInput
    propertyName: city
    name: city
    description: |-
      이벤트 또는 공연이 열리는 도시 이름을 인식합니다. 모든 도시의 이름은 영어로 변경되어야 합니다.
      (예: 서울 -> Seoul, 뉴욕 -> New York)

  - kind: AutomaticTaskInput
    propertyName: StartDateTime
    name: StartDateTime
    description: |-
      - 공연 또는 이벤트가 열리는 시작 날짜입니다. 입력된 날짜가 없다면 공백으로 유지합니다.
      - 입력된 날짜가 있다면, 반드시 날짜의 공통 형식인 ISO8601을 따라서 포멧을 변경합니다.
      예 1) ISO8601 형식에서 날짜는 yyyy-MM-ddthh:mm:ssz 으로 표현합니다.
      예 2) 고객이 날짜 형식을 '25-6-15'를 입력했다면? '2025-06-15T00:00:00Z' 으로 표현됩니다.

  - kind: AutomaticTaskInput
    propertyName: keyword
    name: keyword
    description: 공연 및 이벤트, 가수 이름 등의 키워드입니다.
    shouldPromptUser: true

modelDisplayName: Get Events
modelDescription: |-
  Ticketmaster에서 각종 공연 및 이벤트 정보를 조회합니다. 그리고 표현은 다음과 같은 기준을 따릅니다.
- 조회된 정보를 각 공연 또는 이벤트 별로 Bullet Point 형태로 표현합니다.
- 각 Event 별로 Event id는 필수로 표현되어야 합니다.
- 조회된 Event 또는 공연은 빠짐없이 표현합니다.
outputs:
  - propertyName: _embedded.events

  - propertyName: _links.first.href

  - propertyName: _links.last.href

  - propertyName: _links.next.href

  - propertyName: _links.self.href

  - propertyName: page.number

  - propertyName: page.size

  - propertyName: page.totalElements

  - propertyName: page.totalPages

action:
  kind: InvokeConnectorTaskAction
  connectionReference: cr202_ticketMaster.shared_ticket-20master-20v3-5f9f1743201ee220d8-5f8162bc61f529b2c6.cbcd81b8b6c14d5ba0be84972c5e7fab
  connectionProperties:
    mode: Maker

  operationId: GetEvents

outputMode: All
```
