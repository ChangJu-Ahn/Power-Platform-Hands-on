여기서 내보내기는 **이미 만들어 둔 에이전트를 내보낸다는 가정**입니다

---


# 내보내기

1. https://copilotstudio.microsoft.com/ 접속 후 내가 작업한 환경으로 이동
2. 환경으로 이동 후 다음과 같은 경로로 Solution 항목으로 이동
    <img width="702" height="995" alt="image" src="https://github.com/user-attachments/assets/7b314972-3096-4cd1-afa3-a72c27dbebb9" />

3. 신규 솔루션을 생성합니다. 이 솔루션은 에이전트 및 모든 리소스를 담는 도구라고 볼 수 있습니다.
   <img width="1428" height="768" alt="image" src="https://github.com/user-attachments/assets/cd53eb26-e584-4562-a016-910d337f30d7" />

4. 신규 솔루션을 생성할 필요한 정보를 입력합니다. 
   <img width="526" height="842" alt="image" src="https://github.com/user-attachments/assets/4120103b-fd83-4e50-86e3-6082d83c3d81" />

6. 신규 솔루션을 만들었다면, 안에 내용이 아무것도 없습니다. 이때 내가 만든 에이전트를 다음과 같이 선택하여 가져옵니다.
   <img width="526" height="842" alt="image" src="https://github.com/user-attachments/assets/b5dada08-2d23-47a4-9b71-e657cd17203a" />
   <img width="1734" height="1226" alt="image" src="https://github.com/user-attachments/assets/75f5614d-9650-4ddc-a315-6ed117703229" />
   > 그럼 기본적으로 에이전트에 필요한 구성요소가 함께 따라옵니다.

8. 이후 다시한번 에이전트 탭에서 내가 추가한 에이전트를 선택하고, 다음 이미지와 같이 누락된 요소가 없는지 확인합니다. 
   <img width="1397" height="791" alt="image" src="https://github.com/user-attachments/assets/d72c9f2e-9269-4fa9-aa8c-5b3215d7598d" />

9. 최종 추가가 되었다면, 해당 솔루션 내의 overview 화면으로 이동합니다. 이동하는 아이콘은 다음과 같습니다.
    <img width="824" height="633" alt="image" src="https://github.com/user-attachments/assets/0d6fa5ff-0d9b-4af7-adc7-aced766611ca" />

10. 그리고 해당 화면에서 다음 순서로 실행합니다. 1항은 내보내기 전 수정본을 반영하는 내용이고, 2항은 실제 내보내기 작업입니다. 
    <img width="1974" height="780" alt="image" src="https://github.com/user-attachments/assets/1f5a2ff2-d9a5-498d-9b02-418161f98af9" />

11.  (2)항을 선택하게 되면, 내보내기 전 사전 작업이 진행되는 화면입니다. **내보내기 할 때는 Unmanaged**로 내보낼 수 있도록 합니다.
    <img width="536" height="1205" alt="image" src="https://github.com/user-attachments/assets/af33477e-fbe4-45dd-8869-f107125c6d59" />
    
    > 중요: Managed는 해당 파일을 원본 외 다른 곳에서는 수정할 수 없도록 잠금하는 기능입니다. 하여, 외부에서도 수정이 필요할 때는 Unmanaged로 선택합니다.   

12. 이후 다음과 같은 이미지로 내보내기 작업이 실행됩니다. 만약 내보낼 때 **오류**가 발생하면, 아래 다음 이미지에서 발생한 오류가 표현됩니다.
    <img width="536" height="1205" alt="image" src="https://github.com/user-attachments/assets/af33477e-fbe4-45dd-8869-f107125c6d59" />

13. 최종 다운로드가 되었다면, 아래와 같이 팝업이 출력되고 다운로드를 하게 되면 **Zip** file을 다운로드 받을 수 있습니다.
    <img width="2210" height="374" alt="image" src="https://github.com/user-attachments/assets/235afb43-0273-49e7-94df-920f3413e46e" />

---

# 가져오기
1. 위에서 다운로드 받은 Zip 파일 위치를 확인합니다.
2. **가져오기** 하고자 하는 환경으로 이동한 다음 다시한번 솔루션 화면으로 이동합니다.
3. 그리고 다음과 같이 **Import** 버튼을 클릭합니다.
   <img width="2214" height="168" alt="image" src="https://github.com/user-attachments/assets/989f59ec-79a4-40e9-895a-be0cdc185b20" />
4. 이전에 내보내기한 Zip 파일을 선택 후 다음으로 넘어갑니다.
   <img width="836" height="411" alt="image" src="https://github.com/user-attachments/assets/a814ea17-7cf2-48bb-9f2b-49cb0cce8c0b" />
5. 그리고 정보가 다 올바르다면, 최종 Import를 눌러 마무리합니다.
   <img width="506" height="1199" alt="image" src="https://github.com/user-attachments/assets/7f56c669-313c-4f54-8dc9-180d11d5aa01" />

