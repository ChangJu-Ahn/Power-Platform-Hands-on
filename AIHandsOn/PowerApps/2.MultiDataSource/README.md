## 실습: 서로 다른 데이터소스가 연결된 AI 앱 만들기
- 아래 API는 실습을 위해 GitHub Copilot + Azure Container Apps로 만든 임시 백엔드 서버입니다. (처음에는 Azure Function으로 하려고 했으나..)
- Swagger 테스트는 `https://hr-api-app.politefield-8ac4922f.koreacentral.azurecontainerapps.io/docs` 를 참고합니다.
<img width="1718" height="1002" alt="image" src="https://github.com/user-attachments/assets/3cb8efc8-99c3-45a9-af9a-737569d52f62" />

---

### 1. 외부 시스템을 API 기반으로 연동할 수 있도록 Custom Connector 만들기
*:question: Custom Connector란? 외부 API를 우리 회사의 COnnector 처럼 만드는 작업. 즉, Rest API로 호출할 수 있는 모든 시스템을 연결할 수 있음 :question:*

1. `http://make.powerapps.com/` 접속

2. 아래와 같이 접속
   <img width="2182" height="1266" alt="image" src="https://github.com/user-attachments/assets/b4e4351b-fe4f-4626-b4fb-08bee69a48a6" />
  
3. [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/PowerApps/2.MultiDataSource/Files/hr-api-openapi.json) 파일의 OpenAPI 파일을 다운로드

4. Custom Connector 화면에서 아래 링크를 클릭. 그리고 위에서 다운로드 받은 파일을 Import. 그리고 이름은 xx-hr-api로 저장
   <img width="1940" height="552" alt="image" src="https://github.com/user-attachments/assets/ec40ad54-01ac-4a41-955d-ae86060bcfd2" />
   <img width="1211" height="505" alt="image" src="https://github.com/user-attachments/assets/a4af0b36-0399-420d-bf37-195a3050a465" />

5. OpenAPI 스펙으로 업로드된 Custom Connector를 다음 버튼을 눌러 신규 생성.
   <img width="1801" height="863" alt="image" src="https://github.com/user-attachments/assets/1b989dbd-78b3-4370-a772-0726cbc5298b" />

6. 신규 생성된 커넥터를 테스트하기 위해 다음과 같이 *테스트* 항목으로 이동한다.
   <img width="935" height="519" alt="image" src="https://github.com/user-attachments/assets/52876ecf-301b-4a7c-bcbf-b5ea49003225" />

7. 그리고 안전한 연결을 위한 *New Connection*을 생성한다. 이때 입력한 할 값은 *changjuahn* 이다.
   <img width="1752" height="423" alt="image" src="https://github.com/user-attachments/assets/1784a0d0-6d86-4ced-b2dc-65da9d5fc743" />

8. 아래와 같이 잘 생성됨을 확인한다면, 뒤로가기 해서 다시 테스트 화면으로 이동한다.
   <img width="1392" height="704" alt="image" src="https://github.com/user-attachments/assets/947135f3-daad-4aa4-ae96-dd48229d2484" />

9. 다음과 같이 커넥션이 잘 연결되어있다면, 연결이 잘 된 것이다. 만약 보이지 않는다면 우측 상단의 새로고침 버튼을 눌러서 Connection이 바인딩되도록 한다.
    <img width="1640" height="367" alt="image" src="https://github.com/user-attachments/assets/6b15d294-da40-4186-a073-e3a7ee2386b7" />

10. 아래와 같이 Test Operation을 눌렀을 때 값이 잘 반환된다면, 정상적으로 외부 API를 호출할 수 있는 커넥터를 만든 것이다.
    <img width="1663" height="1281" alt="image" src="https://github.com/user-attachments/assets/5b432a8a-fab1-4af4-a7d9-e8832c843b77" />


### 2. AI를 이용한 AI Prompt 만들기
1. `http://make.powerapps.com/` 접속
2. 아래와 같이 접속
   <img width="933" height="1268" alt="image" src="https://github.com/user-attachments/assets/0ac4fc0f-a8aa-48e2-a77f-628af608ef60" />
  
3. 메뉴 중에서 prompt로 접속
   <img width="1567" height="1053" alt="image" src="https://github.com/user-attachments/assets/2837bae7-4168-4b02-96ee-76a0f4d0e1fc" />

4. 빈 프롬프트 선택
   <img width="1092" height="936" alt="image" src="https://github.com/user-attachments/assets/07f6bb1b-68f4-4d40-91ee-2476e4fe13f2" />

5. [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/PowerApps/2.MultiDataSource/Files/AIPrompt.txt) 프롬프트 입력. 그리고 프롬프트 제목을 'HR 신규 입사자 추출'으로 입력
