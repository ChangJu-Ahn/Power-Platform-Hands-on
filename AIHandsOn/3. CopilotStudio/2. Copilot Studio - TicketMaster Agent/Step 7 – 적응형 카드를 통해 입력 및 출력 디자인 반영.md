7. 상단에 토픽바로 이동 후 신규 토픽 생성
   <img width="1157" height="310" alt="image" src="https://github.com/user-attachments/assets/6a5f3872-45f0-4e38-bc7c-ae293991ad21" />

2. 상단에 '이 토픽이 언제 실행되어야 하는지'에 대한 설명 기술
    ```
    이 토픽은 예약 또는 예매를 위한 신청 토픽입니다. 사용자가 예매하고 싶다는 내용, 혹은 예약하고 싶다는 내용이 있다면 이 토픽을 실행합니다.
    ```

3. 바로 하단의 (+) 버튼을 눌러 적응형카드로 물어보기를 선택(= Ask with Adaptive Card)
   <img width="478" height="647" alt="image" src="https://github.com/user-attachments/assets/8e207ac5-15d8-48bb-9146-ba5267a30434" />

5. 편집을 위해 가운데 톱니바퀴 아이콘 클릭 후 적응형 카드 수정버튼을 클릭
   <img width="749" height="705" alt="image" src="https://github.com/user-attachments/assets/7e4bec27-53ca-4dfa-98bc-23567f673eab" />

7. [여기](https://github.com/ChangJu-Ahn/Power-Platform-Hands-on/blob/main/Copilot%20Studio%20-%20TicketMaster%20Agent/files/Adaptive%20Card%20JSON.json) 템플릿 코드를 아래 빨간색 영역의 템플릿 코드를 삭제 후 복사 후 붙여넣기
   <img width="1670" height="1273" alt="image" src="https://github.com/user-attachments/assets/99529ef9-e1f6-4022-bfdf-36b24eac0086" />

    > 다양한 적응형카드의 예시는 https://adaptivecards.microsoft.com/ 에서 참고할 수 있습니다.   
    > 여기서는 코파일럿을 통해 자연어 기반의 적응형 카드를 바로 만들었습니다.
    > <img width="911" height="713" alt="image" src="https://github.com/user-attachments/assets/f791ab51-35ca-4e11-883b-c156a55b55c5" />
    > <img width="611" height="560" alt="image" src="https://github.com/user-attachments/assets/32917438-e03e-4700-a7e2-418b428de413" />

8. 입력된 값을 확인할 수 있도록 다시 하위 노드에서 (+) 버튼을 눌러서 메시지 보내기를 선택합니다.

9. 다음과 같이 입력합니다. 이때 빨간색 영역의 변수는 우측 {x} 아이콘을 클릭해서 넣을 수 있습니다.
    <img width="446" height="461" alt="image" src="https://github.com/user-attachments/assets/fde1aab1-d44f-4053-9ad0-ae1848c1ebd7" />

11. 다 입력되었다면, 저장 후 다음과 같이 테스트를 해 봅니다.
      a. 예매를 하고 싶다는 비슷한 의미를 입력
      b. 방금 생성한 토픽이 반응했다면, 만들었던 적응형 카드가 질문
      c. 입력한 적응형 카드에 값이 아래 잘 나오는지 확인
    <img width="606" height="1252" alt="image" src="https://github.com/user-attachments/assets/e302a910-51ed-4da9-9048-76222e474b9c" />

12. 적응형 카드에는 정규식에 의해 검증이 가능합니다. 아래 적응형 카드 중 **전화번호** 란 에는 정규식 검증이 들어가 있습니다.
    때문에, 000-0000-0000와 같은 형식이 들어오지 않으면, 저장이 되지 않으니 테스트도 한번 해 봅니다.
    
    <img width="507" height="576" alt="image" src="https://github.com/user-attachments/assets/ddd0f0af-a62e-4363-a8bc-ba33f032c5f2" />
