## JAVA

- String
  - Method
  - field
- escape 문자 \
  -  \ " , \ '
  - \t, \r
- 데이터형 저장 및 변환

```java
//        float pi = 3.14;    //실수형 -> double
        // float pi ( 4 byte ) = 3.14 (8 bytes)
float pi = 3.14; // 오류
double pi = 3.14;
float pi2 = 3.14f;

float pi3 = (float)3.14; //(캐스팅)big -> small 데이터 손실 가능성
```

- 논리 (boolean)
  - java에서는 0과1을 쓸 수 없고 true, false만 가능
- 문자 -> 숫자
  - Integer.parseInt("123") => int a = 123
  - 웹 상에서 문자형태로 받아오기 때문에 사용
  - 숫자처럼 생긴 데이터만 가능
- Alt+Enter
  - import 외워서 하는 것은 좋으나 사용하면 자동적으로 import 생성
- Scanner
  - 화면에 입력 받을 때 사용
  - 표준 출력 = 모니터
  - 표준 입력 = 키보드

```java
Scanner s = new Scanner(System.in);
System.out.print("국어점수 = ");
String strKor = s.next();  // holding, breaking... 입력 받기위함
```

- ```java
  float avg = total / 3;	//정수를 정수로 나눈 것
  float avg = total / 3f;
  float avg = (float)total / 3;
  ```
  - 정수를 정수형 데이터로 나누면 소수점까지 안나옴

- nextInt() 함수
- String.valueOf() 함수

- equals()함수

  - 같은지 다른지

- instanceof

  - true 반환값으로 어디에 속해있는지 확인가능.

  - ```java
    List list1 = new ArrayList();
    Collection list2 = new ArrayList();
    System.out.println(list1 instanceof List);
    System.out.println(list1 instanceof Collection);
    ```

- currentTimeMillis()

  - ```java
    long startTime = System.currentTimeMillis(); //지금 시간의 밀리세컨드 반환
    ```

- nanoTime()
  - 더 작은 시간
- 문자형으로도 switch 받아 볼 수 있음

```java
String type = "FETCH_POST";
switch(type) {     //
    case "FETCH_POST":
    case "DETAIL_POST":
        System.out.println("A");
        break;
    case "CREATE_POST":
        System.out.println("B");
        break;
    case "DELETE_POST":
        System.out.println("C");
        break;
    default:
        System.out.println("D");
        break;
}
```

- psvm
  - public static void main() 매크로

- sout
  - println 매크로

- primitive type 기본 타입
  - 정수, 실수, 논리
  - 그 외는 참조 타입
- JVM 스택 영역
  - 스택 영역
  - 힙 영역
    - 사라지지 않는 것은 gabage collector = gc()가 삭제 시켜줌