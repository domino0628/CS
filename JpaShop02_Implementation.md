<br><br>
```
private final MemberRepository memberRepository;

    @Autowired
    public MemberService(MemberRepository memberRepository) {
        this.memberRepository = memberRepository;
    }
```

<br><br>
위 코드를 @RequiredArgConstructor로 퉁칠 수 있다.
<br><br>
# 테스트를 인메모리로 돌리는 방법
<br><br>
test/resources 디렉토리에 application.yml을 생성하면 테스트는 해당 yml을 기준으로 동작한다.
이때 밑 그림과 같이 주석처리를 해놓으면 자동으로 인메모리 테스트를 시작한다.

<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/ddabc8be-2f5c-4715-9b47-850b0f581402)


<br><br>
다음과 같은 쿼리는 Item 객체 형태의 리스트를 Item이라는 엔티티에서 전부 추출하는 것이다

<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/6aceeafd-e3b4-4601-80de-d0ed8dacd388)

<br><br>
# 정적메소드 : 인스턴스가 사용되지 않더라도 사용할 수 있는 메서드이다.
<br><br>
```
public class MathUtil {
    // 정적 메소드: 두 수를 더한 결과를 반환
    public static int add(int a, int b) {
        return a + b;
    }

    // 정적 메소드: 두 수를 곱한 결과를 반환
    public static int multiply(int a, int b) {
        return a * b;
    }
}

public class Main {
    public static void main(String[] args) {
        // 정적 메소드 호출
        int sum = MathUtil.add(5, 3);
        System.out.println("Sum: " + sum);

        int product = MathUtil.multiply(4, 6);
        System.out.println("Product: " + product);
    }
}
```

<br><br>
이와 반대되는 개념으로, 인스턴스 메서드가 있다.
<br><br>
```
public class Car {
    private String model;

    // 인스턴스 메소드: 모델을 설정하는 메소드
    public void setModel(String newModel) {
        this.model = newModel;
    }

    // 인스턴스 메소드: 현재 모델을 반환하는 메소드
    public String getModel() {
        return model;
    }
}

public class Main {
    public static void main(String[] args) {
        // 인스턴스 생성
        Car myCar = new Car();

        // 인스턴스 메소드 호출
        myCar.setModel("Toyota");
        String currentModel = myCar.getModel();
        System.out.println("Current Model: " + currentModel);
    }
}
```
<br><br>

# MemberForm이라는 클래스를 Member가 있는데도 굳이 만든 이유 : 엔티티에는 핵심 비즈니스 로직만 넣는다. 그렇지 않으면 비즈니스 로직 한 번 호출했는데 화면 관련 로직들도 전부 불러오기 때문이다. (비즈니스 로직 건드렸더니 화면이 깨질 수 있다.)
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/81f6caa2-af7a-47f7-893f-a001cf24086f)

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

