

# Step 5 – Copilot Studio 에이전트 초기 구축

> **목표:** Copilot Studio에서 에이전트(agent)를 만들고, 우리가 만든 \*\*사용자 지정 커넥터(custom connector)\*\*만 사용하도록 초기 설정을 완료합니다. 

---

## 1. Copilot Studio로 이동 및 새 에이전트 만들기

1. **Copilot Studio** 환경으로 이동합니다.
2. **New agent(새 에이전트 만들기)** 클릭 → 에이전트 생성 시작

---

## 3. 에이전트 세부 설정: 일반 지식 비활성화

1. 상단의 **설정(Setting)** 메뉴로 이동합니다.

![설정 메뉴 진입](https://github.com/user-attachments/assets/43f74733-73b0-4b00-b637-b0358966fd87)

2. **생성형 AI 설정**에서 **일반 참조 자료 사용(General knowledge)** 옵션을 \*\*끄기(Off)\*\*로 변경 후 저장합니다.

   * 이렇게 하면 에이전트는 일반 웹 지식이나 오래된 정보(예: 2023년 Oasis 정보) 대신, **오직 사용자 지정 커넥터**를 통해 실시간 데이터를 조회합니다.

![일반 참조 자료 사용 끄기](https://github.com/user-attachments/assets/5d89be62-fa61-42f8-a230-e35e7a641f5e)

---

> 이제 Copilot Studio 에이전트가 준비되었습니다. 다음 단계에서 이 에이전트에 **‘이벤트 가져오기(GetEvents)’ 작업**을 연결해 실제로 대화 중 이벤트 정보를 조회할 수 있도록 구성하세요.
