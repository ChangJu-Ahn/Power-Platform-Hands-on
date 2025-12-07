## 실습: GPT를 활용하여 'AI 현장 안전가이드 앱 만들기'

### 1. 멀티모달이 가능한 AI Prompt 생성
1. `http://make.powerapps.com/` 접속
2. 아래와 같이 접속
   <img width="933" height="1268" alt="image" src="https://github.com/user-attachments/assets/0ac4fc0f-a8aa-48e2-a77f-628af608ef60" />
  
3. 메뉴 중에서 prompt로 접속
   <img width="1567" height="1053" alt="image" src="https://github.com/user-attachments/assets/2837bae7-4168-4b02-96ee-76a0f4d0e1fc" />

4. 빈 프롬프트 선택
   <img width="1092" height="936" alt="image" src="https://github.com/user-attachments/assets/07f6bb1b-68f4-4d40-91ee-2476e4fe13f2" />

5. 아래 프롬프트 입력. 그리고 프롬프트 제목을 '현장 사고사진 분석'으로 입력
   ```
       현장 안전 전문가로서 물류창고의 사고 사진을 분석하는 AI 어시스턴트를 위한 프롬프트를 생성합니다.
       이 프롬프트는 바닥에 흰색 또는 노란색으로 표시된 지정된 물건의 구획선을 기준으로, 그 외에 구획선 밖에 위치한 물건이나 위험 요소를 식별하고, 안전 관련 가이드를 제공하는 데 목적이 있습니다.
       답변은 모두 한국어로 작성되어야 합니다.
        
        ---
        ## 프롬프트 구성
        
        ### 1. 상황 설명 (Context)
        - 물류창고 현장의 사고 사진을 분석합니다.
        - 바닥에는 흰색 또는 노란색으로 지정된 물건의 구획선이 표시되어 있습니다.
        - 구획선 내외의 물건 위치를 파악하여 안전 문제를 진단합니다.
        
        ### 2. 지시사항 (Instructions)
        1. 사진에서 바닥에 표시된 흰색 또는 노란색 구획선을 인식합니다.
        2. 각 구획선 내부에 위치한 물건과 구획선 외부에 위치한 물건을 구분합니다.
        3. 구획선 밖에 위치한 물건이 있으면 이를 식별하고, 그로 인한 잠재적 안전 위험을 평가합니다.
        4. 물류창고 안전을 위해 필요한 조치나 개선사항을 구체적으로 제안합니다.
        5. 분석 결과와 안전 가이드는 한국어로 명확하고 간결하게 작성합니다.
        
        ### 3. 분석 및 판단 기준 (Rationale)
        - 구획선은 물건의 적재 및 이동 구역을 명확히 구분하기 위한 안전 기준입니다.
        - 구획선 밖에 물건이 위치하면 작업자의 이동 경로 방해, 사고 위험 증가 등의 문제가 발생할 수 있습니다.
        - 따라서 구획선 내외 물건 위치를 정확히 파악하고, 위험 요소를 조기에 발견하는 것이 중요합니다.
        
        ### 4. 출력 형식 (Output Format)
        - 분석 요약: 사진 내 구획선과 물건 위치 상태 간단히 설명
        - 위험 요소 식별: 구획선 밖에 위치한 물건 및 그 위험성 기술
        - 안전 가이드: 구체적이고 실행 가능한 안전 개선 조치 제안
        
        예시:
          분석 요약: 사진에서 노란색 구획선 내에 5개의 박스가 적재되어 있으며, 2개의 박스가 구획선 밖에 위치해 있습니다.
          위험 요소: 구획선 밖 박스는 작업자의 이동 경로를 방해하여 넘어짐 사고 위험이 있습니다.
          안전 가이드: 구획선 밖 박스는 즉시 구획선 내로 이동시키고, 정기적으로 구획선 준수 여부를 점검하는 절차를 마련하세요
        
        ---
        
        ## 최종 프롬프트 예시
        
        당신은 물류창고 현장의 안전을 책임지는 전문가입니다. 아래 사진을 분석하여 다음 사항을 한국어로 답변해 주세요.
        
        1. 사진에서 바닥에 표시된 흰색 또는 노란색 구획선을 인식하고, 각 구획선 내외에 위치한 물건을 구분해 주세요.
        2. 구획선 밖에 위치한 물건이 있다면 이를 식별하고, 그로 인한 잠재적 안전 위험을 평가해 주세요.
        3. 물류창고 안전을 위해 필요한 구체적인 조치나 개선사항을 제안해 주세요.
        4. 위험 분석 결과항목은 '예' 또는 '아니오'로 요약해서 대답해 주세요.
        
        분석 결과는 다음 형식으로 작성해 주세요.
        
        [1. 위험 분석 결과]
        - {내용}
        [2. 분석 요약]
        - {내용}
        [3. 위험 요소]
        - {내용}
        [4. 안전 가이드]
        - {내용}
        
        사진: 사고 사진
    ```

6. 프롬프트 하단의 '사고 사진'을 지우고 다음과 같이 실제 변수를 입력할 수 있도록 입력합니다.
   <img width="753" height="805" alt="image" src="https://github.com/user-attachments/assets/50e84a3b-13e7-4494-b916-6895d56f03d7" />
   <img width="1166" height="1077" alt="image" src="https://github.com/user-attachments/assets/19758e8e-af42-4450-960d-5885f67e3ed6" />

7. 그리고 [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/Files/%EA%B5%AC%ED%9A%8D%20%EC%84%A0%EC%97%86%EC%9D%8C.png) 링크에 사진을 다운로드받아서 확인해 봅니다.

8. 다음과 같이 직접 이미지를 입력해서 테스트를 했을 때 결과가 잘 나오는지 확인해 본다. 이 예시의 사진은 '정리되지 않은 현장' 이므로 아래와 같이 나오는 게 맞다.
   <img width="2207" height="1229" alt="image" src="https://github.com/user-attachments/assets/b20e8b6c-2fdb-4f52-b285-ffa0ed158c7c" />

</br>
</br>

## 2. 모바일 어플리케이션 생성
1. `http://make.powerapps.com/` 접속
   
2. 다음과 같이 신규 앱 생성을 위한 버튼을 누릅니다.
   <img width="2253" height="1258" alt="image" src="https://github.com/user-attachments/assets/b33e7345-a899-4380-97dd-294660ed8766" />
   
3. 모바일 어플리케이션 레이아웃을 누릅니다. (아무거나 클릭해도 되지만, 이번 시나리오는 모바일 현장관리 앱 입니다)
   <img width="2251" height="1269" alt="image" src="https://github.com/user-attachments/assets/f240a298-2e1c-4c12-8f04-9b3107ed3621" />

4. 다음과 같이 방금 만든 프롬프트가 검색되는지 확인하고, 검색된 Data Source를 추가합니다.
   <img width="400" height="404" alt="image" src="https://github.com/user-attachments/assets/12e116a9-2f2c-4b6a-8cb0-4053f1a43277" />
   <img width="605" height="664" alt="image" src="https://github.com/user-attachments/assets/99a01dc8-9cb4-4240-9950-cdd8cc58b2f3" />

5. 사진을 찍어 자동으로 이미지로 바꿔주는 컨트롤을 추가하기 위해 'Add picture'를 검색해서 추가합니다.
   <img width="909" height="826" alt="image" src="https://github.com/user-attachments/assets/944154c6-5dfd-4601-a0f9-b756cbf41806" />

6. 버튼을 눌렀을 때 AI Prompt를 호출하기 위해 'Button' 컨트롤을 추가합니다.
   <img width="570" height="681" alt="image" src="https://github.com/user-attachments/assets/6bbd9991-0f9c-4e83-800a-2ef150f4d836" />

7. AI가 반환한 값을 보여주기 위해 'Text Label' 컨트롤을 추가합니다.
   <img width="785" height="882" alt="image" src="https://github.com/user-attachments/assets/7c7cdb1a-ca7f-43f3-87ef-f48b406637ff" />
 
8. 그래서 위 3개를 조합한 최종 디자인 화면은 다음과 같습니다.
   <img width="1578" height="1170" alt="image" src="https://github.com/user-attachments/assets/b9d50244-b227-40d0-966b-743407677b60" />

9. 버튼 컨트롤을 눌렀을 때 수행할 Power Fx를 입력합니다.
    ```
      Set(result, '현장 사고사진 분석'.Predict(UploadedImage1.Image))
    ```
    <img width="1858" height="966" alt="image" src="https://github.com/user-attachments/assets/5c14916c-522f-4876-b71c-8fa1f213a223" />

10. 반환된 값을 Text Labeling에서 보여줄 수 있도록 다음과 같이 Power Fx를 입력합니다.
    ```
      result.Text
    ```
    <img width="1503" height="1198" alt="image" src="https://github.com/user-attachments/assets/870f0029-e566-46fd-b4cc-dad50cd53c9a" />

11. 테스트를 위해 다음과 같이 재생 버튼을 눌러서 테스트 모드로 진입합니다.
    <img width="735" height="490" alt="image" src="https://github.com/user-attachments/assets/ac3f6b5b-d05d-4463-99fc-0f44197a3757" />

12. 가운데 영역을 클릭 후 사진을 업로드 후 버튼을 눌러봅니다.
    <img width="880" height="1071" alt="image" src="https://github.com/user-attachments/assets/1469c5cb-2c50-4297-93a4-4f9ad00b9504" />
    <img width="687" height="1095" alt="image" src="https://github.com/user-attachments/assets/9c7ad58b-dd90-4199-b5a6-56424048f790" />

13. AI Prompt에서 반환된 전체 값을 보는 방법(디버깅은)은 다음과 같습니다.
    <img width="1362" height="1039" alt="image" src="https://github.com/user-attachments/assets/e34c8ff9-d3f6-4faf-a51e-11546a1347d4" />
    <img width="1495" height="698" alt="image" src="https://github.com/user-attachments/assets/313d25c1-394a-4366-9836-e1950ff31a29" />

14. 그리고 나머지 사진도 [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/AIHandsOn/Files)에에 업로드 되어있으니 테스트해 봅니다.

15. 아래와 같이 정리가 잘 된 사진을 업로드 하면, 결과 값으로 '위험하지 않다고' 값을 잘 반환하는 걸 볼 수 있습니다.
    <img width="866" height="1184" alt="image" src="https://github.com/user-attachments/assets/37c6ad8f-d3ce-4e5e-9a6b-9611a6398113" />


 
