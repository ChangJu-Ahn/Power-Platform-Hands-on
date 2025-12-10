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

### 2. AI 기반의 자동화된 워크플로우 생성
1. `https://make.powerautomate.com/` 접속 후 좌측 `create`를 누릅니다.
   <img width="1087" height="1005" alt="image" src="https://github.com/user-attachments/assets/9d9f59ac-4997-486a-95b3-8511ddfa87c4" />

2. `자동화된 클라우드`를 선택 후 다음과 같이 설정한 뒤 `생성` 버튼을 누릅니다.
   <img width="935" height="601" alt="image" src="https://github.com/user-attachments/assets/1a64e355-a82b-4f84-a9d2-78f4707396b6" />

3. 가장 상단의 트리거를 선택 후 `Subject Filter`를 클릭. 이후 다음과 같이 필터구문을 추가합니다.
   <img width="1141" height="1149" alt="image" src="https://github.com/user-attachments/assets/a69be59c-f90d-4ffd-8ade-459bee8dc74c" />
   ```
      contains(
        toLower(
          replace(
            triggerOutputs()?['body/Subject'],
            ' ',
            ''
          )
        ),
        '주간보고'
      )

   @contains(replace(triggerOutputs()?['body/Subject'],' ',''), '주간보고)
   ```


<img width="311" height="296" alt="image" src="https://github.com/user-attachments/assets/ce7374fd-515a-4375-9ba2-fd450b88133e" />
