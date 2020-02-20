## Java3

- equals()
  - 내용이 같은지 묻는 함수
  - new로 선언 했던 것이라도 안에 내용이 같으면 true로 나온다.
- String 변수 초기값으로 null 대입
- 참조를 잃은 String 객체는 쓰레기 수집기로 메모리에서 자동 제거



- NullPointerException 오류

  ```java
  name = null;
          System.out.println(name);
          System.out.println(name.length());  //
  ```

  null인 데이터를 사용했기 때문에 오류가 뜸

- breakpoint
  - Debug로 실행
  - intellij에서 Debug 모양이 벌레인 이유는 벌레를 잡는다는 뜻

### 배열

- 같은 타입의 데이터만 저장 가능
- 한 번 생성되면 길이를 늘리거나 줄일 수 없음



- 방식

  ```java
     scores = {1,2,3,4,5,6,7};
          scores = new int[]{1,2,3,4,5,6,7};
  ```

  ```java
  animals[4] = "cat";
          animals[3] = new String("dog");
  ```

- index 필요한 경우 or 그렇지 않은 경우, for each문

  ```java
   for (int i = 0; i < animals.length; i++) {
              System.out.println(animals[i]);
          }
  
  
          int index = 0;
          for(String a : animals) {   //for each 함수 꺼낼 데이터 : 배열 전체 
              System.out.println(index++ + a);//배열 값을 순차적으로 가져온다.
          }
  ```

- 배열복사
  - System.arraycopy([Object](https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/Object.html) src, int srcPos, [Object](https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/Object.html) dest, int destPos, int length)
  - 변수 값이 알아서 지정 되기 때문에 입력 하지 않고 value 값만 입력해도 된다.





로또

1~45 사이의 6개 번호 입력

자동으로 당첨 로또 번호 6개 생성 (1~45, 중복 X)

로또 번호와 입력 번호 비교, 몇개 숫자 일치하는지 출력

- 랜덤함수

```java
for (int i=0; i<10; i++) {
//            double value = Math.random();
//            System.out.println(value *45 + 1);

        Random r = new Random();	//() 안에 시드값을 주면 똑같은 난수가 나온다.
    //() 안에 System.currentTimeMillis()를 넣으면? 같은 값이 안나옴
        int intVal = r.nextInt(45) + 1;	// 0~44 -> 1~45
        System.out.println(intVal);
        }


        System.out.println("번호 6개 입력 : ");
        Scanner n = new Scanner (System.in);
        Integer intN = n.nextInt();
```

### 객체와 클래스

- 클래스는 자바의 설계도

- 속성(필드+동작(메소드))로 구성



- nested class, field, methods, constructor method 특징

  ```java
  // nested class 중첩 클래스
      class VipMember{
          
      }
      // field 가지고 있는 특징 및 데이터
      int age = 10;
      String name = "Java";
      // methods
      void 메소드이름() { // 반환값을 주지 않는다면 void를 쓴다
          
      }
      int 메소드이름2() { // 반환값이 있으므로 return을 해줘야 한다.
          return 1;
      }
      // (optional)constructor method 생성자 메소드 단한번 호출 클래스 이름과 동일
  ```

- 역 컴파일 명령어

  - javap

- public의 특징

```java
public class Member {   //main이 없으므로 실행 불가능     public이 하나 있으면 여러개의 클래스를 가질 수 있음
    String name;
    int age;
    Project finalProject;       //Project class와 집합관계 {Project[] finalProject도 가능
    Project semiproject;
    
    void displayInfo() {
        System.out.println(String.format("이름은 %s이고, 나이는 %s 입니다.", name, age));
    }
}

class Project {
    String name;
    String period;
    void budget() {
        
    }
}

```

- OverLoading

  ```java
  // OverLoading(같은 이름의 클래스가 여러개) -> 같은 클래스에서 메소드이름은 같고, 파라미터의 타입이나 개수가 다름
  Member(int age) {
          this.age = age;
      }
      
  Member(String name) {
      this.name = name;
  }
  
  Member(String name, int age) {  // ()안의 값을 메소드의 시그니처
      this.name = name; // 전체 클래스 블럭에 있는 name을 지칭
      this.age = age;
  }
  ```

  반환 값은 의미가 없다.

- 리팩토링

  ```java
   public Blog(int id, String category, String title, String author, String contents, String link, int is_private) {
          this.id = id;
          this.category = category;
          this.title = title;
          this.author = author;
          this.contents = contents;
          this.link = link;
          this.is_private = is_private;
      }
  
      public Blog(String category, String title, String author, String contents, String link, int is_private) {
          this(0, category, title, author, contents, link, is_private);
      }
  ```

  this라는 함수를 써서 코드를 줄일 수 있다.