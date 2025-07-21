[마이크로소프트 안창주 Solution Engineer]

**Origin 1. 👉 https://www.youtube.com/watch?v=ZcUUv39dcig**   
**Origin 2. 👉 https://www.linkedin.com/in/damobird365/**

---

# 고객 핸즈온 세션: Power Platform Ticketmaster 에이전트 구축

이 핸즈온 세션에서는 **Ticketmaster API와 Power Platform을 활용하여 실시간 이벤트 정보를 검색할 수 있는 지능형 에이전트를 구축하는 방법**을 단계별로 학습합니다.

**사전 준비:**
*   Ticketmaster 개발자 계정 및 **API 키** (API key).

---

## Step 1: Ticketmaster API 탐색 및 기초 이해

*   **주제:** Ticketmaster API의 구조 및 이벤트 검색 기능 파악.
*   **목표:** Ticketmaster 개발자 API 문서 중 **`events` API 엔드포인트**와 **`Discovery v2` 문서**를 검토합니다. 샘플 URL을 사용하여 브라우저에서 직접 API를 호출하고 반환되는 JSON 데이터의 구조를 파악하며, `size`, `keyword`, `start date/time`, `city`와 같은 **주요 파라미터**를 이해합니다. 실습에 사용할 **API 키를 확보**합니다.

## Step 2: 사용자 지정 커넥터 초기 설정

*   **주제:** Power Platform에서 Ticketmaster API를 위한 사용자 지정 커넥터 생성.
*   **목표:** Power Platform에서 **새 사용자 지정 커넥터**를 빈 상태에서 생성하고, 식별 가능한 이름(`Ticket Master connector`)을 지정합니다. Ticketmaster API의 **루트 API 엔드포인트**인 `app.ticketmaster.com`을 **기본 호스트 URL**로 설정합니다. API 키 인증을 사용하여 보안을 구성하며, 초기에는 헤더(header)로 설정하지만, 필요에 따라 **쿼리(query) 매개변수로 변경할 수 있음**을 인지합니다.

## Step 3: '이벤트 가져오기' 작업 정의

*   **주제:** 커넥터 내에서 Ticketmaster 이벤트 검색 액션 구성.
*   **목표:** 커넥터에 'get events'라는 **새 액션**을 생성하여 Ticketmaster에서 이벤트를 검색하는 기능을 추가합니다. `events.json` URL과 함께 `keyword` (예: Oasis), `start date/time`, `city` (예: Manchester)와 같은 **필수 쿼리 매개변수**를 포함하는 **요청 샘플**을 가져옵니다. 또한, API에서 반환될 데이터의 예시를 제공하기 위해 `size`를 5로 늘려 더 많은 데이터를 반환하도록 설정한 **응답 샘플**을 붙여넣고 가져옵니다.

## Step 4: 사용자 지정 커넥터 테스트 및 보안 문제 해결

*   **주제:** 생성된 커넥터의 기능 및 API 키 인증 유효성 검증.
*   **목표:** API 키를 사용하여 **새 연결을 생성**합니다. 'Oasis'와 같은 키워드를 사용하여 커넥터가 올바르게 작동하는지 **작업을 테스트**합니다. 만약 API 키 관련 오류(`401` 또는 `400`)가 발생하면, Step 2에서 설정한 API 키의 `Pass in` 위치를 **헤더에서 쿼리로 수정**하고 다시 테스트하여 성공적인 응답을 받습니다.

## Step 5: Copilot Studio 에이전트 초기 구축

*   **주제:** Copilot Studio 환경에서 새로운 에이전트 생성 및 기본 설정.
*   **목표:** Copilot Studio에서 'Events Agent'와 같은 이름으로 **새 에이전트를 생성**합니다. 에이전트가 수행할 작업(예: "사용자 지정 커넥터를 사용하여 예정된 이벤트에 대한 세부 정보 가져오기")에 대한 **초기 지침**을 정의합니다. 에이전트가 자체 학습 데이터가 아닌, 구축된 사용자 지정 커넥터에만 의존하도록 **일반 지식(general knowledge) 기능을 비활성화**합니다.

## Step 6: 에이전트에 사용자 지정 커넥터 추가 및 입력/출력 구성

*   **주제:** Copilot Studio 에이전트와 사용자 지정 커넥터 연동 및 대화 흐름 설정.
*   **목표:** Step 2에서 생성한 'Ticket Master connector'를 에이전트에 **액션으로 추가**합니다. `City`, `Keyword`, `Start Date/Time` 각 매개변수에 대한 간략한 설명을 추가합니다. **초기 설정**으로 `Should prompt user`를 기본값(체크됨)으로 두어 사용자가 각 매개변수에 대해 개별적으로 질문받는 동작을 경험하게 합니다. 에이전트가 사용자에게 반환할 이벤트 요약 방식(예: "사용 가능한 이벤트를 글머리 기호 형식으로 요약")을 정의합니다.

## Step 7: 생성형 오케스트레이션 활성화

*   **주제:** Copilot Studio 에이전트의 지능형 대화 및 액션 연동 기능 이해 및 적용.
*   **목표:** 사용자 지정 액션이 트리거되고 언어 모델이 사용자 요청을 기반으로 계획을 수립할 수 있도록 **생성형 오케스트레이션(Generative Orchestration)이 필수적임**을 이해합니다. Copilot Studio 설정에서 'Generative' 오케스트레이션 토글을 켜고 저장합니다.

## Step 8: 에이전트 테스트 및 사용자 경험 최적화

*   **주제:** 에이전트의 실제 동작 테스트, 문제점 식별 및 개선.
*   **목표:** "When do Oasis play Manchester?"와 같은 질문을 통해 에이전트를 테스트하고, `start date/time` 매개변수에 대해 **ISO 8601 형식**으로 날짜를 입력해야 함을 파악하고 수정합니다. 에이전트가 선택적 매개변수에 대해 계속 질문하는 문제가 발생하면, Step 6의 입력 매개변수 설정에서 `Should prompt user` 옵션을 **해제(unchecked)**하여 사용자 경험을 개선합니다. "I am traveling to New York in July 2025 are there any baseball tickets available and then I am heading to London in August our Oasis player and then I am heading to Vienna in August what might I go and see"와 같이 **여러 개의 의도를 포함하는 복합적인 질문**을 통해 생성형 오케스트레이션의 강력한 기능을 시연하고, 에이전트가 각 요청에 대해 정확한 정보를 제공하며 필요한 경우 이벤트 링크를 포함하는지 확인합니다.

---
