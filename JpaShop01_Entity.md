![image](https://github.com/domino0628/CS/assets/59598751/2f246da6-2abc-4839-915d-9c1c8eaf0a86)

# 애노테이션 : 주석형태로 특정 기능을 나타내거나 특정 설정을 지정하기 위해 사용되는 메타데이터, 컨테이너에 빈을 등록한다.

<br>

![image](https://github.com/domino0628/CS/assets/59598751/547ff4d7-5d15-4af8-9977-f333074d181d)


<br>

# 제어의 역전(IOC) 컨테이너 : 컨테이너가 빈(컨테이너에 들어가는 객체)의 생성과 소멸을 개발자 대신 관리한다.

<br>

![image](https://github.com/domino0628/CS/assets/59598751/4b95b2b3-e225-47f6-ae46-044aeac331d6)

<br><br>

## 의존성 주입(DI) : 어떤 객체가 다른 객체에 의존하도록 하는 것이다.

<br>

![image](https://github.com/domino0628/CS/assets/59598751/3b105719-9acd-4564-baec-9cf4de4b771c)


<br>

# 주입은 인터페이스형으로 맞춰서 구현체를 갈아끼우기 용이하게 한다. (윗 그림의 밑줄 친 부분을 방지하기 위해)

<br>
참고자료 : https://develogs.tistory.com/19

<br><br>
Component류 어노테이션(Controller,Repository 등)을 붙여 스프링 빈을 스프링 컨테이너에 담아 그때그때 쓰도록 한다. 주로 싱글톤(단 하나의 형식만 스프링 컨테이너에 들어가있음)
<br><br>
이러한 작업은 코드마다 새로 객체를 생성해 코드 가독성을 해치는 경우를 방지함.
<br><br>
@Autowired로 스프링 컨테이너에서 해당 객체를 꺼내 사용한다고 약속한다.
<br><br>
자바 코드로 DI를 실행 시 생성자 주입 방법을 쓴다.
<br><br>
스프링 빈은 내용 변형할 일이 없어 생성자의 기능(한 번 만들어지면 불변함)을 살린 생성자 주입이 좋다.
<br><br>
정형화 된 repository,service,controller 같은 패턴은 컴포넌트스캔이 간편하다. 그러나 상황에 따라 구현 클래스를 변경해야 하면 직접 의존성을 주입하면 수정이 쉽다.
<br><br>
![image](https://github.com/domino0628/Springinfo/assets/59598751/6bf742a7-fa52-42aa-b98c-cb1fcb45eed0)
<br><br>
처음에 저 반환되는 객체는 스프링에서 직접 구현한 단순한 저장소인데, 나중에 실제 DB로 바꾸려면 그 부분만을 바꾸면 된다.
<br><br>
![image](https://github.com/domino0628/Springinfo/assets/59598751/417f9ce9-5d24-408e-a529-e76e86c803d6)
<br>

# 수정할때마다 서버를 껐다 키지 않아도 변경사항이 보이도록하는 방법 : devtools를 build.gradle에 추가한다.

<br>

![image](https://github.com/domino0628/CS/assets/59598751/904c02c7-7696-4e4f-ade0-0402a19731d9)

<br>
<br>

![image](https://github.com/domino0628/CS/assets/59598751/226fef18-4eca-440a-820e-6fbbf7224218)

<br>
위 그림과 같이 안녕!!로 바꾸고, build-> recompile 누르고 웹페이지를 새로고침한다.

<br>

![image](https://github.com/domino0628/CS/assets/59598751/a2402450-dd62-4ad8-be60-12eb15ec3bf3)

<br><br>

# ORM : ORM 기술은 객체(Object)와 DB테이블을 매핑하여 데이터를 객체화하는 기술
<br><br>
SQL문이 아닌 메소드 형식으로 직접 DB데이터 관리가 가능함
<br><br>

# Java Persistence Api : ORM의 일종으로, 프로그램 종료 후에도 영구 저장이 가능하다 
<br><br>
Hibernate는 구현체중 하나
<br><br>
# Example 2 : 간단한 멤버 저장소의 예
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/1eb86626-5433-4984-bf77-51314bcd1ab2)
<br><br>
PersistentContext 어노테이션으로 entityManeger를 주입할 수 있다. 이것은 프로그램 종료시에도 데이터의 영속성을 가질 수 있도록 해주는 관리자라고 생각하면 된다.
<br><br>
엔티티매니저를 통한 데이터변경은 항상 트랜잭션 내에서 이루어져야 한
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




