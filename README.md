# 데이터베이스 생성 실습

목적) mysql과 postman을 활용한 데이터베이스 생성 과정 실습

1) DB 생성 과정

   
 1- DB 이름 설정 및 저장

   
![db1](https://github.com/user-attachments/assets/ad3e4f37-8ad4-4dda-85b3-85f9d2346460)


2- 이름 저장 후 테이블 생성


![스크린샷 2025-05-17 231255](https://github.com/user-attachments/assets/f7f7d0f6-eee4-41a7-9d74-519633d1963e)





2) sever.js 코드 짜기

1- 

node.js에서 express 프레임워크 이용하여 서버 구축

  mysql 데이터베이스와 연결



![스크린샷 2025-05-19 185452](https://github.com/user-attachments/assets/d387932d-25ca-48b4-8855-2b0238e154ee)



2- JSON 데이터 파싱을 위한 설정 추가




![스크린샷 2025-05-19 185502](https://github.com/user-attachments/assets/16cd5cce-5c8a-48fc-a468-cfe56c8b663a)




3- post 요청




![스크린샷 2025-05-19 185511](https://github.com/user-attachments/assets/968be13f-2f80-447a-b0a7-f870e336e5c2)




4- get 요청



![스크린샷 2025-05-19 185532](https://github.com/user-attachments/assets/864e31c4-a2a1-4980-a54f-f58c9b661b1a)



5- 서버 실행



![스크린샷 2025-05-19 185538](https://github.com/user-attachments/assets/8ef72ff7-8a02-42ba-8d51-2aac0e16f058)






3) postman 생성 후 연결


<img width="950" alt="스크린샷 2025-05-19 184652" src="https://github.com/user-attachments/assets/04f37c58-f1b0-43a6-a621-23678d5440fd" />


http://localhost:3000/db 및 아이디/비번 코드 입력

Body-raw-JSON 선택 후 Send 누르기




4) 결과 확인


<img width="509" alt="스크린샷 2025-05-19 185042" src="https://github.com/user-attachments/assets/9d91e193-e91d-423d-a707-06193df4c4a2" />







요약 및 결과) 

mysql을 통해 데이버베이스 및 테이블 구축 성공

express 설정과 mysql 연결을 통해 서버 구축

postman에서 post,get 요청

서버 실행을 통해 결과 확인



