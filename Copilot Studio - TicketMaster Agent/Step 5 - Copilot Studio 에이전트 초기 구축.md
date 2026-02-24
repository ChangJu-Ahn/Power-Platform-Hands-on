

# Step 5 – Copilot Studio 에이전트 초기 구축

> **목표:** Copilot Studio에서 에이전트(agent)를 만들고, 우리가 만든 \*\*사용자 지정 커넥터(custom connector)\*\*만 사용하도록 초기 설정을 완료합니다. 

---

## 1. Copilot Studio로 이동 및 새 에이전트 만들기

1. **Copilot Studio** 환경으로 이동합니다.

   * 반드시 사용자 지정 커넥터를 만든 **동일한 Power Platform 환경**(예: `copilot workshop12`)인지 확인하세요.
2. **Create blank Agent 우측 버튼** 클릭 → **고급 생성**을 선택

<img width="1713" height="470" alt="image" src="https://github.com/user-attachments/assets/d9279a66-c697-40c1-a400-c690d58d67a2" />

3. 에이전트 설정에서 다음과 같이 입력
- 언어: 한국어
- 솔루션: 이미 개인 별로 만든 솔루션
<img width="679" height="537" alt="image" src="https://github.com/user-attachments/assets/c0b32594-dbcf-4d83-82d6-601e03f4a4d1" />


---

## 2. 에이전트 세부 설정: 일반 지식 비활성화

1. 상단의 편집을 눌러서 다음과 같이 4가지 항목을 진행합니다.
1) 편집을 눌러 내용을 수정합니다
2) 에이전트 이름을 변경합니다. 여기서는 다음과 같이 입력합니다.
   ```
     Ticket Master Event Agent - ChangjuAhn
   ```
3) Description을 입력합니다. 여기서는 다음과 같이 입력합니다.
   ```
    공연 및 이벤트에 관련된 정보를 제공하는 에이전트입니다. 사용자에게 이벤트 정보를 제공하고, 필요한 정보를 검색하며 이벤트 관련 질문에 대답합니다.
   ```
4) 커스텀 커넥터를 만들 때 다운로드 받은 이미지를 입력합니다.

<img width="960" height="225" alt="image" src="https://github.com/user-attachments/assets/d392df8b-88fe-41d5-b07b-bcae9632799c" />


2. **생성형 AI 설정**에서 **일반 참조 자료 사용(General knowledge)** 옵션을 \*\*끄기(Off)\*\*로 변경 후 저장합니다.

   * 이렇게 하면 에이전트는 일반 웹 지식이나 오래된 정보(예: 2023년 Oasis 정보) 대신, **오직 사용자 지정 커넥터**를 통해 실시간 데이터를 조회합니다.

<img width="977" height="509" alt="image" src="https://github.com/user-attachments/assets/2dfed526-2be5-43f7-83a5-454a06768708" />

---

> 이제 Copilot Studio 에이전트가 준비되었습니다. 다음 단계에서 이 에이전트에 **‘이벤트 가져오기(GetEvents)’ 작업**을 연결해 실제로 대화 중 이벤트 정보를 조회할 수 있도록 구성하세요.
