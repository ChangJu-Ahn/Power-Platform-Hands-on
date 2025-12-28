

# Step 1 - Ticketmaster Discovery v2 API 이해 & 실습 가이드

> 이 README는 **고객이 바로 따라할 수 있도록** 구성되었습니다.  
> 모든 예시는 복사·붙여넣기만 해도 동작하도록 작성했으며, `{apikey}` 부분만 여러분의 실제 키로 교체하세요.
---

## 🔧 준비물 (Prerequisites)

- Ticketmaster 개발자 계정 및 **API Key**
- 웹 브라우저 (Chrome, Edge 등)
- (선택) 터미널 또는 Postman, curl 등 API 호출 도구
---

## 1. 공식 문서로 API 개념 파악하기

Ticketmaster Discovery v2 API에서 우리가 사용할 엔드포인트는 **Event Search**입니다.  
문서를 먼저 확인해 주세요.

- **공식 문서:**  
  https://developer.ticketmaster.com/products-and-docs/apis/discovery-api/v2/#search-events-v2
![Event Search 문서 예시](https://github.com/user-attachments/assets/deba8f78-ac7d-4dbf-af8b-e77bf04a6887)

> 💡 **TIP**: 문서에서 “Query Parameters” 섹션을 꼭 읽어보세요. 검색 필터(예: `keyword`, `city`)를 편하게 이해할 수 있습니다.
---
## 2. 샘플 URL로 직접 호출해 JSON 구조 파악하기

브라우저 주소창에 아래 URL을 입력해보세요.  
`{apikey}` 부분을 반드시 **본인의 API Key로 교체**해야 합니다.

```text
https://app.ticketmaster.com/discovery/v2/events.json?size=1&apikey={apikey}
https://app.ticketmaster.com/discovery/v2/events.json?size=1&apikey=IFLd7Lvz7ZNTI2qnCnJz8yiYOABJ4sgg
````

![size=1 결과 JSON](https://github.com/user-attachments/assets/33016025-d5e9-44f6-aefb-1ba95c71d4c5)

* `size=1`로 설정되어 있으므로, **이벤트 한 건**(예: Sacramento Kings vs. Phoenix Suns)에 대한 JSON 응답을 확인할 수 있습니다.
* JSON의 최상단 `_embedded.events[0]` 구조를 확인해, 우리가 필요한 필드(이벤트 이름, url 등)를 파악해보세요.
</br>

---
## 3. 다양한 쿼리 파라미터 테스트해보기

문서에 있는 **Query Parameters**를 URL 쿼리스트링에 추가하여 동작을 확인해 보세요.
아래는 예시입니다.

### 예시 1) `keyword` 파라미터로 검색하기

```text
https://app.ticketmaster.com/discovery/v2/events.json?size=1&keyword=Oasis&apikey={apikey}
https://app.ticketmaster.com/discovery/v2/events.json?size=1&keyword=Oasis&apikey=IFLd7Lvz7ZNTI2qnCnJz8yiYOABJ4sgg
```

* `"Oasis"` 관련 이벤트를 찾는 검색입니다.

### 예시 2) `city` 파라미터로 특정 도시 이벤트 찾기

```text
https://app.ticketmaster.com/discovery/v2/events.json?size=1&city=Manchester&apikey={apikey}
https://app.ticketmaster.com/discovery/v2/events.json?size=1&city=Manchester&apikey=IFLd7Lvz7ZNTI2qnCnJz8yiYOABJ4sgg
```

* `"Manchester"`에서 열리는 이벤트를 찾는 검색입니다.



### 📌 자주 쓰는 Query Parameter 요약

| Parameter            | 설명                                 | 예시 값                    | 예시 URL 추가분                            |
| -------------------- | ---------------------------------- | ----------------------- | ------------------------------------- |
| `keyword`            | 이벤트명/아티스트/팀명 등 키워드 검색              | `Oasis`, `Taylor Swift` | `&keyword=Oasis`                      |
| `city`               | 도시 이름                              | `Manchester`, `Seoul`   | `&city=Manchester`                    |
| `countryCode`        | ISO 2자리 국가 코드                      | `US`, `GB`, `KR`        | `&countryCode=KR`                     |
| `classificationName` | 장르 분류                              | `Music`, `Sports`       | `&classificationName=Music`           |
| `startDateTime`      | 시작 날짜/시간 (UTC, ISO8601)            | `2025-07-24T00:00:00Z`  | `&startDateTime=2025-07-24T00:00:00Z` |
| `endDateTime`        | 종료 날짜/시간 (UTC, ISO8601)            | `2025-07-31T23:59:59Z`  | `&endDateTime=2025-07-31T23:59:59Z`   |
| `size`               | 페이지당 결과 수 (기본 20, 최대 200)          | `1`, `50`               | `&size=50`                            |
| `page`               | 페이지 번호 (0부터 시작)                    | `0`, `1`                | `&page=1`                             |
| `sort`               | 정렬 기준 (예: `date,asc`, `name,desc`) | `date,asc`              | `&sort=date,asc`                      |

> 💡 **팁**: 여러 파라미터를 조합할 때는 `&`로만 이어 붙이면 됩니다.
> 예: `...?size=50&keyword=Oasis&city=Manchester&apikey={apikey}`
> 예: `...?size=50&keyword=Oasis&city=Manchester&apikey=IFLd7Lvz7ZNTI2qnCnJz8yiYOABJ4sgg`



---

## 📎 부록: 문제 발생 시 체크리스트

* ❓ **401 Unauthorized**: API Key가 잘못됐거나 누락된 경우입니다. `{apikey}`를 다시 확인하세요.
* ❓ **400 Bad Request**: 쿼리 파라미터가 잘못되었을 수 있습니다. 공식 문서에서 가능한 값을 확인하세요.
* ❓ 응답이 비어있거나 `_embedded`가 없는 경우: 검색 조건이 너무 엄격하거나 해당 조건에 맞는 결과가 없는 것입니다. 조건을 완화해보세요.



> 👏 수고하셨습니다! 다음 Step에서 **Copilot Studio**와 연동하는 과정을 이어갈게요.
