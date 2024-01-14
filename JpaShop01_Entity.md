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
엔티티 : 그냥 객체다. 근데 JPA의 영속성을 띄는 객체 (프로그램 종료 후에도 저장되는)
<br><br>
엔티티매니저를 통한 데이터변경은 항상 트랜잭션 내에서 이루어져야함. (ACID룰)
<br><br>
원자성 (Atomicity): 트랜잭션의 모든 연산은 원자 단위로 실행되어야 하며, 모두 성공하거나 모두 실패하여 롤백되어야 함
<br><br>
일관성 (Consistency): 트랜잭션이 완료된 후에도 데이터베이스는 일관된 상태를 유지해야 함 즉, 트랜잭션 전후에 데이터베이스의 무결성이 보장되어야 함
<br><br>
고립성 (Isolation): 여러 트랜잭션이 동시에 수행되더라도, 각 트랜잭션은 서로 영향을 주지 않고 독립적으로 실행되는 것처럼 보여야 함.
<br><br>
지속성 (Durability): 트랜잭션이 성공적으로 완료된 후에는 그 결과가 영구적으로 저장되어야 합니다. 시스템이 고장나더라도 트랜잭션의 결과는 보존되어야 함
<br><br>
@Transactional을 통해 이러한 성질을 주입한다.
<br><br><br><br>
다음과 같은 테스트를 돌리면 H2 데이터베이스에 자동으로 Member table이 생성된다.
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/17b64602-bf48-41d2-b3ce-ae18c68d55a0)

<br><br>
이게 JPA의 ORM적인 특성이고, yml 파일에서 auto create 설정을 해놨기 때문이다.
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/5d1584a5-a22c-42a1-91a4-f9a646420f96)

<br><br>
Test에 @Transactional이 붙으면 롤백을 해서 테이블이 비게 된다.
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/a3935493-9433-4a32-9224-6dfa02ffcb1b)

<br><br>
테스트할때 롤백 없애는 방법 : @Rollback(false)
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/7448d70a-a870-4bb8-a614-d6dabb8dd32c)

<br><br>
같은 영속성 컨텍스트 안에서는 id값이 같으면 같은 엔티티이다. 또한 동일 엔티티 조회시 캐싱된 메모리를 사용해 db로의 접근을 줄인다.
<br><br>
# build는 고급언어(Java,Python)등의 언어를 기계어로 변환해 실행할 수 있게 한다.
<br><br>
# Run은 그 파일을 실행하는 것이다.(웹의 경우, 실행하면 접속이 가능하다.)
<br><br>
단일 테이블 전략 : 한 가지의 테이블만을 사용한다
<br><br>
# 테이블이 다대다 관계일 때, 매핑 테이블을 사용하지 않으면 일어나는 일
<br><br>
```
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    student_name VARCHAR(255),
    course_id INT,
    course_name VARCHAR(255)
);
```
<br><br>
```
CREATE TABLE Courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(255),
    student_id INT,
    student_name VARCHAR(255)
);
```
<br><br>
```
-- 예시 데이터
INSERT INTO Students (student_id, student_name, course_id, course_name)
VALUES
    (1, 'Alice', 101, 'Math'),
    (1, 'Alice', 102, 'History'),
    (2, 'Bob', 101, 'Math'),
    (2, 'Bob', 103, 'Science');
```
<br><br>
이처럼 다대다 관계에서 데이터를 쿼리할 때, ID, NAME 등 중복되는 데이터를 여러 번 저장해야 하기 때문에 무결성을 어렵게 한다.
<br><br>
# 개체 무결성(Entity Integrity)
<br><br>

주 키(primary key)를 포함한 각 행은 유일한 값을 가져야 함. 이는 테이블의 각 행이 식별될 수 있도록 하는 규칙이다.

<br><br>
# 외래 키 : 테이블 사이의 연관성을 나타내기 위한 키
<br><br>
```
CREATE TABLE country (
 country_id integer,
 name varchar(50),
 population integer);

CREATE TABLE city (
 city_id integer,
 name varchar(50),
 country_id integer);
```
<br><br>
위 테이블을 사람의 시선으로 보면, 연관되어 있다는 것을 알 수 있지만 컴퓨터는 그러지 못 함.
<br><br>
컴퓨터가 country 테이블에 없는 country_id 값을 city에 넣어버릴 수도 있기 때문에, 그런 불상사를 막기 위해 외래 키를 도입한다.
<br><br>
```
1. country 테이블에 기본 키 생성하기
DROP TABLE country;
CREATE TABLE country(
 country_id integer,
 name varchar(50),
 population integer,
 PRIMARY KEY (country_id) );

2. 기본 키와 외래 키를 정의한 새로운 테이블 생성
DROP TABLE city;
CREATE TABLE city (
 city_id integer,
 name varchar(50),
 country_id integer,
 PRIMARY KEY (city_id),
 FOREIGN KEY (country_id) REFERENCES country(country_id) );
```
<br><br>
부모 테이블 : 더 넓은 정보를 담고 있는 테이블
<br><br>
자식 테이블 : 더 좁은 정보를 담고 있는 테이블
<br><br>
부모 테이블과 자식 테이블 간의 외래 키가 항상 가지는 규칙을 기억하자. 자식 테이블 안의 값이 부모 테이블 안에 언제나 존재해야 한다. 그렇지 않으면 오류임
<br><br>
참조 : https://kimsyoung.tistory.com/entry/SQL-%EC%99%B8%EB%9E%98-%ED%82%A4%EC%97%90-%EB%8C%80%ED%95%9C-%EC%9D%B4%ED%95%B4
<br><br>
연관관계의 주인 : 외래 키가 있는 엔티티에 정의한다.
<br><br>
@Id, @GeneratedValue : 주 키를 설정하고 자동으로 생성한다. (1씩 늘려나감)
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/c9c73d94-a88e-45ce-afc3-df3d7e3594cc)

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




