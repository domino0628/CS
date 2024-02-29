# API로 렌더링 vs 템플릿 엔진으로 렌더링의 차이? : api를 사용하면 서버는 데이터를 제공하고 클라이언트가 렌더링함
<br><br>
# 템플릿 엔진 렌더링은 return으로 html 반환하는 단순한 형태
<br><br>
# API에서 파라미터는 엔티티를 받는게 아니라 DTO형태로 받는게 좋다, 왜냐하면 API 스펙을 직관적으로 알 수 있기 때문이다.
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/8551ab1e-6725-42fc-be4e-68ec8949bc59)

<br><br>
위의 그림에서 CreateMemberRequest라는 DTO를 만들었고, name만이 전달됨을 가독성 좋게 알 수 있다.
<br><br>
# application.yml : ddl auto를 None으로 설정하면 애플리케이션이 다시 시작되도 데이터베이스가 초기화 되지 않는다.
<br><br>
일대 다 관계에서, 일 다 양쪽 모두 외래 키(다른 테이블을 식별할 수 있는 참조 데이터)를 설정할 수 있지만, 일반적으로 다에 설정한다.
<br><br>
# 양방향 연관관계에서 발생할 수 있는 문제 : 반복적인 호출 order -> member -> orders -> ...
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/ad34fe8b-8981-434c-abe6-a2fbfefb9656)

<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/14d475fc-221f-440a-8f27-2a0efe79465c)

<br><br>
해결방법 : Jsonignore 삽입
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/ca90da3b-b844-474e-89da-30d7a984e87e)

<br><br>

프록시 : 성능 향상을 위한 가상의 객체, 원래 jpa로 프로그램을 짜면 객체를 로딩할 때 연관된 객체를 전부 로딩해야 하지만,
<br><br>
프록시로 땜빵을 하고 필요핱 순간에 실제 객체를 가져온다.
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/4781246a-70b6-4708-9e81-a3226ac209b6)

<br><br>
지연로딩으로 조회를 하면null값이 나온다.
<br><br>
# V1,V2 모두 order,member,delivery 라는 테이블을 조회하기 때문에 느리다
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/009aa9cc-55f6-4411-b2b8-1c6d1d341299)
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/cbb6f73b-ccec-4bc7-bea4-2c04ee83b427)
<br><br>
Lazy 초기화 :  Lazy 초기화는 연관된 엔티티를 실제로 사용하는 시점에 쿼리하여 가져오는 것을 의미, 아래 그림에서 실제로 getmember, getdelivery로 데이터를 가져오기 전까지는 하이버네이트가 프록시객체를 이용해 프로그램을 돌림(로딩을 지연시키는 것). 그러다 필요할때 진퉁 데이터를 가져온다. 
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/cc7c42db-624b-4806-b1ef-9b056007c40c)

<br><br>

# N+1 쿼리 문제 : 주문이 2개라 가정시
<br><br>
orders 가져올때 쿼리 1번, getmember 2 getDelivery 2번 총 5번의 쿼리가 나가 성능이 떨어진다.
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/906fd50c-5a61-4640-a6ba-1118246db3a6)

<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/846602ab-e75b-4198-aa34-d0824a110df7)

<br><br>

# N+1 쿼리 최적화 : fetch join
<br><br>임. Member에서 Order를 참조하면 양방향 관계가 되어야 하므로 불필요한 관계가 발생할 수 있다
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
<br><br>
