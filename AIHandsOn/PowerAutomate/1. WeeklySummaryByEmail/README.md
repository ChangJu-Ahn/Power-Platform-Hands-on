## 실습: AI 기반 프로젝트 진척사항 정리 프로세스

### 1. 이메일을 대신 정리해 줄 AI Prompt 생성
1. `https://make.powerautomate.com/` 접속
2. 아래와 같이 접속
   <img width="1077" height="1230" alt="image" src="https://github.com/user-attachments/assets/0f1d2133-1441-45fa-b220-b02cf8d0531f" />

3. 메뉴 중에서 prompt 선택
   <img width="1170" height="1097" alt="image" src="https://github.com/user-attachments/assets/592f57aa-49f8-46b1-8e8d-77573d7a2c5a" />

4. 빈 프롬프트 선택
   <img width="1323" height="1214" alt="image" src="https://github.com/user-attachments/assets/4e6fca54-675f-42bb-900b-14cc5c790a0b" />

5. [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/PowerAutomate/1.%20WeeklySummaryByEmail/Files/prompt.txt) 프롬프트를 복사하여 저장합니다. 이때 제목은 `프로젝트 진척사항 요약`로 합니다. 그리고 하단의 `email`이라고 되어있는 텍스트를 지우고 `/`를 누른 뒤 텍스트를 선택해 email 변수를 받도록 설정합니다.
   <img width="920" height="530" alt="image" src="https://github.com/user-attachments/assets/cad10054-f0d8-403c-9df6-563be680fd38" />

6. [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/tree/main/AIHandsOn/PowerAutomate/1.%20WeeklySummaryByEmail/Files) 샘플 이메일을 참고하여 테스트를 진행합니다.
   <img width="1946" height="1202" alt="image" src="https://github.com/user-attachments/assets/f2f6c552-eafa-412f-8ee0-f4c6542b9433" />

7. 내용을 확인한 뒤 이상이 없다면, 최종 Save를 눌러 마무리합니다.

### 2.원드라이브 내 주간보고 엑셀 위치 저장
1. [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/PowerAutomate/1.%20WeeklySummaryByEmail/Files/AI%20Apps%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%20%EC%A7%84%EC%B2%99%EC%82%AC%ED%95%AD.xlsx) 파일을 로컬로 다운로드 한다.

2. `onedrive.com`으로 이동해 로그인한 뒤, 다음과 같이 `My files`에 `Project`라는 폴더를 한 개 생성한다.
   <img width="1277" height="746" alt="image" src="https://github.com/user-attachments/assets/5d181a9c-7934-4153-90ab-761cc9d24b9a" />

3. 그리고 이 안에 다운로드 받은 파일을 업로드한다.
   <img width="1258" height="624" alt="image" src="https://github.com/user-attachments/assets/d5554ea6-56aa-4e9b-a2ce-43b7f2539ee0" />

### 3. AI 기반의 자동화된 워크플로우 생성
1. `https://make.powerautomate.com/` 접속 후 좌측 `create`를 누릅니다.
   <img width="1087" height="1005" alt="image" src="https://github.com/user-attachments/assets/9d9f59ac-4997-486a-95b3-8511ddfa87c4" />

2. `자동화된 클라우드`를 선택 후 다음과 같이 설정한 뒤 `생성` 버튼을 누릅니다.
   <img width="935" height="601" alt="image" src="https://github.com/user-attachments/assets/1a64e355-a82b-4f84-a9d2-78f4707396b6" />

3. 가장 상단의 트리거를 선택 후 `Setting`를 클릭. 이후 다음과 같이 필터구문을 추가합니다.
   <img width="1185" height="1066" alt="image" src="https://github.com/user-attachments/assets/67df6f0d-80fb-45a8-889e-6bc9adea7b1c" />

   ```
     @contains(replace(triggerOutputs()?['body/Subject'], ' ', ''), '주간보고')
   ```
4. + 버튼을 눌러 `AI Builder`를 검색한다. 이후 `Run a prompt`를 클릭한다. 만약 다음과 같이 나온다면, 자신의 이름을 넣고 다시한번 로그인해서 커넥션을 만든다.
   <img width="311" height="296" alt="image" src="https://github.com/user-attachments/assets/ce7374fd-515a-4375-9ba2-fd450b88133e" />

5. 커넥션이 생성되면, 이전에 만들어놨던 프롬프트를 연결한 뒤 이메일 본문을 추가한다.
  <img width="1191" height="1118" alt="image" src="https://github.com/user-attachments/assets/c2a0cad6-16b7-486b-ac11-9b44862b1b2f" />

6. + 버튼을 눌러 `Parse JSON`을 선택하고 Content에는 위에서 동작해서 나온 결과 값 중 `Text`를 추가한다.
     <img width="1054" height="584" alt="image" src="https://github.com/user-attachments/assets/95b35315-8f44-493b-85cc-980913126492" />

7. 그리고 아래 빨간색 테두리 버튼의 `Sample payload`를 선택하고 다음 값을 붙여넣는다.
   <img width="656" height="565" alt="image" src="https://github.com/user-attachments/assets/dd586770-8833-4f11-82ba-a2425bd71e4c" />
   ```
      {
        "주차": "1주차",
        "진척사항": "진척사항 입력 란입니다",
        "이슈": "이슈 입력란입니다",
        "블로커": "블로커 입력란입니다",
        "Flag": "Green"
      }
   ```

8. 다음과 같이 샘플 값 기반으로 정확한 스키마가 연결됐는지 확인합니다.
   <img width="540" height="392" alt="image" src="https://github.com/user-attachments/assets/744916bd-8702-4fb1-96d5-4a1217a8d5bf" />

9. + 버튼을 눌러 `Excel Online (Business)`를 클릭한 뒤 ` Add a row into a table`을 선택한다.
     <img width="1046" height="624" alt="image" src="https://github.com/user-attachments/assets/aa15bfe7-e7ab-4e2c-aac4-01ca44834d9b" />

10. 신규로 연결한다면, 다음과 같이 커넥션을 만든다.
    <img width="262" height="236" alt="image" src="https://github.com/user-attachments/assets/48280edf-8220-490c-8035-8f8c51b5fade" />

11. 커넥션 생성 후 아까 업로드한 엑셀의 경로와 표를 연결한다. 제대로 연결한 뒤 `Show All`을 누르면 아까 각 표에 나왔던 컬럼을 화면에서 확인할 수 있다.
    <img width="1046" height="1129" alt="image" src="https://github.com/user-attachments/assets/93e62b98-b33c-4023-93e4-0aa20ae2ecc3" />

12. 아까 위에서 Parse Json으로 변환했던 값을 각 엑셀의 컬럼에 대입해 준다.
    <img width="316" height="272" alt="image" src="https://github.com/user-attachments/assets/7f91932b-2e40-4763-9c37-63cdecf775ab" />
    
13. 테스트 이메일을 보냈을 때 반영이 잘 되는지 확인.
    <img width="2842" height="1273" alt="image" src="https://github.com/user-attachments/assets/c309f74b-be1a-4c8a-a02d-f57874a81a81" />

14. 테스트를 위한 이메일 본문은 [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/PowerAutomate/1.%20WeeklySummaryByEmail/Files/sampleEmail.md)에서 확인할 수 있고, 오토메이트 필터링에 설정되어 있는 `주간보고` 라는 제목이 아닌 다른 이메일도 여러 개 보내보자. 다른 이메일이라면, 엑셀에 요약되지 않아야 정상이다.



