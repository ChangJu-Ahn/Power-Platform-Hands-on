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
  
3. [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/1.%20PowerApps/2.MultiDataSource/Files/hr-api-openapi.json) 파일의 OpenAPI 파일을 다운로드

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


### 2. 다양한 데이터소스가 결합된 간단한 앱 만들기
1. `http://make.powerapps.com/` 접속
   
2. 다음과 같이 신규 앱 생성을 위한 버튼을 누릅니다.
   <img width="2253" height="1258" alt="image" src="https://github.com/user-attachments/assets/b33e7345-a899-4380-97dd-294660ed8766" />
   
3. 테블릿 어플리케이션 레이아웃을 누릅니다. (아무거나 클릭해도 되지만, 이번 시나리오는 HR 직원관리 전용 앱 입니다)
   <img width="1186" height="624" alt="image" src="https://github.com/user-attachments/assets/a940c323-0230-44a2-b258-77c6e8886bb4" />

4. 신규 데이터소스에 위에서 만든 데이터 소스 2개를 우선 추가합니다.
   <img width="516" height="619" alt="image" src="https://github.com/user-attachments/assets/cbbe0cbd-fc40-4e09-bd39-58a04b325632" />

5. 시스템에 저장되어 있지 않고, HR 담당자만 가지고 있는 가상의 엑셀파일을 [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/1.%20PowerApps/2.MultiDataSource/Files/HR%20Employee%20Excel.xlsx)에서 다운로드 후 바탕화면에 저장한다.

6. 방금 다운로드 받은 샘플 액셀을 연결하기 위해 다음과 같이 검색 후 추가한다. Import할 때 `표1`을 선택해서 마무리한다.
   <img width="287" height="492" alt="image" src="https://github.com/user-attachments/assets/d65db43a-258e-4466-a6b9-508f9d4276f8" />
   <img width="275" height="334" alt="image" src="https://github.com/user-attachments/assets/9937ee51-740b-44f6-93bb-b099c5bc2ad8" />

7. 화면에 다음과 같이 `Vertical Gallery` 두 개를 추가한다. 아직 데이터 소스는 신경쓰지 않아도 되고, 두 개가 겹치지 않도록 배치한다.
   <img width="1680" height="1049" alt="image" src="https://github.com/user-attachments/assets/1d703358-00c0-4a8d-bb07-14c5094f3060" />

8. 왼쪽 갤러리에는 HR 시스템에서 API로 반환하는 값을 바인당한다. 갤러리를 선택 후 *Items*의 속성으로 이동하여 아래 Power Fx를 입력한다. 이때 앞에 `HRAPI`는 데이터소스 이름이다.
   ```
      HRAPI.GetEmployees().data
   ```
   <img width="1660" height="1122" alt="image" src="https://github.com/user-attachments/assets/c1a77e9a-52a0-41b1-95ca-58ffdf30e681" />

9. 다음과 같이 가장 갤러리 가장 상단에서 내가 보고싶은 항목을 입력한다. 텍스트 레이블을 지정해서 작업할 수 있다.
    <img width="1465" height="948" alt="image" src="https://github.com/user-attachments/assets/12676c2d-84dd-4f65-a9f8-8668fba4c466" />

10. 마찬가지로 우측 갤러리에도 데이터 소스를 '표1'이라는 엑셀을 연결한다.
    <img width="2213" height="1184" alt="image" src="https://github.com/user-attachments/assets/7ef699e7-3bb8-4621-ab5f-e400b40d47f8" />

11. 이 또한, 8번을 참고해서 필요한 정보를 보일 수 있게 바인딩한다.
    <img width="2245" height="1250" alt="image" src="https://github.com/user-attachments/assets/b83b54c3-9466-48b3-a37e-3232ddb4b6e5" />

12. AI 코파일럿을 사용해서 Power Fx를 자동으로 제안받아 추가로 형태를 변경해 본다.
    <img width="2203" height="578" alt="image" src="https://github.com/user-attachments/assets/a4097bb7-99e1-4390-bbed-33820b3e2efc" />
    <img width="1780" height="442" alt="image" src="https://github.com/user-attachments/assets/6995d895-1e0b-4529-82f3-32cfc4d2dc83" />
    <img width="1817" height="400" alt="image" src="https://github.com/user-attachments/assets/7a7dd35c-9e4a-4d0f-928a-0abe47d3a807" />

13. 서로 다른 데이터소스가 바인딩된 갤러리를 조인해 본다. 우측 갤러리를 선택하고 다음과 같이 Items 바인딩 값을 변경한다.
    ```
      Filter(표1, Employee = Gallery1.Selected.employee_id)
    ```
   <img width="2178" height="1175" alt="image" src="https://github.com/user-attachments/assets/40fe85fe-e8f6-4562-932f-5ce71db4673e" />

14. 우측 상단의 재생 버튼을 눌러 테스트해 본다. 좌측 갤러리의 값을 선택할 때마다 이에 따른 우측 값이 필터링되어 보이게 된다.
    이처럼 1,400개 이상의 커넥터와 Custom Connector로 서로 다른 데이터를 연결해서 어플리케이션을 손 쉽게 만들고, 서로 연동되어 동작할 수 있음을 확인할 수 있다.
    <img width="2178" height="1175" alt="image" src="https://github.com/user-attachments/assets/6dd5252b-35a4-4a49-bcf2-0babdce5a625" />
