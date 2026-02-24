

# Step 6 – 에이전트에 사용자 지정 커넥터 추가 및 입력/출력 구성

> **목표:** Copilot Studio 에이전트에 **사용자 지정 커넥터**(Ticketmaster)를 도구(Tool)로 추가하고, **입력(Inputs)·출력(Outputs) 구성**을 설정합니다.

---

## 1. 도구(Tool) 추가

1. 상단의 **도구(Tools)** 섹션으로 이동합니다.
2. **도구 추가(Add a tool)** 버튼을 클릭합니다.

![도구 추가 화면](https://github.com/user-attachments/assets/b13435fb-cde3-4e04-8fdb-0dcd4014ef73)

3. 생성해 둔 **Ticket Master 커넥터**(예: `Ticketmaster20250724`)를 찾아 선택 후 에이전트에 추가합니다.

![커넥터 선택 화면](https://github.com/user-attachments/assets/e0f16c33-e549-4b39-9990-09989f007542)

---

## 2. 도구 세부 설정

1. 추가된 커넥터 목록에서 **“이벤트 가져오기”** 동작을 클릭합니다.

![이벤트 가져오기 클릭](https://github.com/user-attachments/assets/d5edef74-1edc-442b-9cc5-a1abdc7368e1)

2. **설명(Description)** 영역에 에이전트가 이 도구로부터 받은 결과를 **어떻게 요약/표현할지**를 작성합니다.

   * 예: “이벤트 내용을 불렛 포인트로 요약합니다. 요약하는 내용에는 이벤트의 이름, 날짜, 시간대, 티켓 링크를 포함합니다. ”

![설명 작성 예시](https://github.com/user-attachments/assets/6955e4a2-a92f-411d-9faa-8792e5f4127a)

3. **추가 정보**탭에서 사용할 인증을 다음과 같이 '유저 -> 제작자'로 변경합니다.
   <img width="892" height="867" alt="image" src="https://github.com/user-attachments/assets/d92372ed-34d8-4618-91c4-426178fb6c34" />

---

## 입력(Inputs) 설정

1. **Inputs** 섹션에서 각 매개변수에 대한 \*\*설명(Description)\*\*을 추가합니다. 대표적으로 다음과 같이 작성할 수 있습니다.

![입력 설정 화면 1](https://github.com/user-attachments/assets/dd3ba87f-2595-4373-b78c-adbfc42bb5ca)
![입력 설정 화면 2](https://github.com/user-attachments/assets/60e75626-11b0-48d6-a654-5043c3887f07)

* **City(도시)**: “이벤트가 열릴 도시를 식별합니다. 제공되지 않으면 비워 둡니다.”


* **Keyword(키워드)**: “아티스트(또는 팀) 이름이 제공되면 포함해야 합니다. 제공되지 않으면 비워 둡니다.”


* **Start Date/Time(시작 날짜/시간)**: “이벤트가 발생할 시작 날짜입니다. 예를 들어 5월 1일을 지정하면 5월 1일 이후의 이벤트를 찾습니다. 제공되지 않으면 비워 둡니다. 날짜의 형식은 ISO 8601 형식 (예: YYYY-MM-DDTHH:MM:SSZ)입니다.”
  ![Start Date/Time 설명 예시](https://github.com/user-attachments/assets/ca5bcc99-aaf3-4d76-8cbe-229f3f2d51ad)


2. 각 입력 매개변수의 **‘사용자에게 프롬프트헤야 합니다(Should prompt user)’** 옵션은 체크하지 않은 상태로 둡니다.

   * 사용자 경험 개선을 위해 현재 실습 단계에서는 체크하지 않은 상태로 두었지만, 이후 설정을 변경할 수 있습니다.

---

## 입력 매개변수의 필수 값 제거
1. 위에서 설정한 Tool을 기준으로 다음과 같이 코드를 볼 수 있는 화면으로 이동합니다.
   <img width="1538" height="784" alt="image" src="https://github.com/user-attachments/assets/35ea2a1d-5a95-4733-8194-a2289053b373" />

2. 이미 설정된 코드를 기준으로 아래 빨간색 영역이 없다면, 입력해 줍니다.
   <img width="1453" height="1219" alt="image" src="https://github.com/user-attachments/assets/0bb2e0c0-ccaa-4e1a-a276-f1ce5d8fed62" />

  **⚠️ IMPORTANT**   
  아래 코드를 복사하여 붙여넣을 수 있는데, 들여쓰기를 주의해야 합니다. 들여쓰기는 Description 라인에 맞춰주세요.
  ```
  shouldPromptUser: false
  ```

--- 

##  결과

런던 혹은 뉴욕에서 열리는 공연, 더 나아가 날짜 및 키워드로 물어보면 답을 얻을 수 있습니다!   
그리고 다음과 같이 실제 검색된 공연은 실시간 공연 예매 사이트에서도 동일하게 확인할 수 있습니다.

<img width="1689" height="1230" alt="image" src="https://github.com/user-attachments/assets/6071e629-b607-4a12-a939-046f1ecc56e0" />
<img width="1976" height="1221" alt="image" src="https://github.com/user-attachments/assets/8e471ffe-8e50-426a-b857-61646c748fbc" />

