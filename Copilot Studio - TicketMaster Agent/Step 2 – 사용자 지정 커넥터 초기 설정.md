# Step 2 – 사용자 지정 커넥터 초기 설정

> **Step 1을 완료하셨나요?**  
> 이제 Power Platform에서 **Ticketmaster API를 호출할 사용자 지정 커넥터**를 만들어 봅니다.  
> **모든 스텝은 실제 화면을 기준으로 작성**했으며, 스크린샷/아이콘 링크도 함께 제공합니다.

---

## 🔧 준비물 (Prerequisites)

- Power Platform(또는 Power Apps / Power Automate) 접근 권한
- Ticketmaster **API Key** (Step 1에서 발급받은 키)
- 사용할 **아이콘 이미지** (예: Ticketmaster 로고)

---

## 1. Power Platform에서 새 사용자 지정 커넥터 만들기

1. **Power Platform** 포털에 접속합니다.  
2. **새 사용자 지정 커넥터(New custom connector)** 생성 > **빈 상태에서 만들기(Blank)** 선택  
3. 이름을 식별 가능하게 지정합니다.  
   - 예: `TicketMaster20250724`

![새 커넥터 만들기](https://github.com/user-attachments/assets/873057cc-f1ee-4101-a992-76984ef4e7d3)
![빈 상태에서 만들기 선택](https://github.com/user-attachments/assets/1d14efc6-a3ca-450e-8788-b1e138c6213a)




---

## 2. 일반(General) 탭 – 기본 정보 입력

- **Host(기본 호스트 URL)**: `app.ticketmaster.com`  
- **Icon**: 아래 링크에서 Ticketmaster 로고를 다운받아 업로드합니다.  
  - 로고 다운로드: https://github.com/monator16/CPS_handson/blob/main/ti7179b1bb-ticketmaster-logo-brand-assets-ticketmaster-uk-business.png

![일반 탭 설정 예시](https://github.com/user-attachments/assets/66c93e0e-0a5b-453a-a209-06e6dbb4adf4)


---

## 3. 보안(Security) 탭 – API Key 인증 설정

1. **API로 구현되는 인증 선택(Authentication Type)**을 **API 키(API key)**로 선택합니다.  
2. Ticketmaster 문서에 따라 **매개 변수 레이블(Parameter label)**과 **매개 변수 이름(Parameter name)**을 `apikey`로 설정합니다.  
3. **매개 변수 위치(Pass in)**는  **쿼리(Query)**로 지정합니다.


![API 키 인증 설정](https://github.com/user-attachments/assets/67616b9d-b223-46ca-9503-761230ddefc3)



> ⚠️ **중요**: `apikey` 철자를 정확하게 입력하세요. 오타가 나면 인증이 되지 않습니다.

---
