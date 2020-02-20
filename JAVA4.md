## Java4

### 메소드

- 메소드 선언부 (signature)
- 매개변수가 적을수록 좋다.

- 메소드 이름은 알아 볼 수 있는게 좋다.
- 로컬변수
  - 로컬을 벗어나면 다른 곳에 영향을 미치지 않는다.
- 전개 연산자를 이용한 가변데이터 사용

```java
int add (int...values) {
        int result = 0;
        for (int value : values)
            result += value;

            return result;

    }
```

- 접근제한자(modifier)

  - 순서
    - private < protected <  X(default) < public
  - private
    - 같은 class만
  - X(default)
    - 같은 class + 같은 package(폴더)
  - protected
    - 같은 class + 같은 package + 다른 package(단, 상속관계)
  - public
    - 같은 class + 같은 package + 다른 package 보안 X, export의 개념

  ```java
  public Student(String name, int kor, int eng, int mat) {
      this.name = name;
      this.kor = kor;
      this.eng = eng;
      this.mat = mat;
  }// 다른 package에서도 사용가능하게 만든 예시
  ```

 - import 사용 시 package 이름과 클래스 명시

    ```java
    import com.example.day2.Student;
    ```

- 생략된 toString()

  ```java
  System.out.println(stu);    // println(stu.toString()); 이 생략 되어있음
  ```

- overriding

  ```java
  Student -> Object (method) -> toString -> 다시 정의 (overriding)
  ```

  부모가 가진 메소드 이름이랑 동일해야함

  - @override (어노테이션)

    - 코드가 짧아질 수 있고 코드의 의도 전달의 장점

    - 함수 위에 쓰면 된다.
    - equals()나 toString()을 재정의 할때 유용함

- 알트+insert 키

  - implement Methods 로 구현할 메소드를 찾아서 넣을 수 있음

- .compareTo();

  - ()안의 값으로 비교

  - 예제

    ```java
    if (s1.getAvg() > s2.getAvg()){
                return -1;
            }
            else if (s1.getAvg() < s2.getAvg()){
                return 1;
            }
            else {
                return s1.getName().compareTo(s2.getName());
            }
    ```

- sort

  - Comparable이 선언 되어 있어야 사용 가능

  - ex) 선언

    ```java
    public class MyComparator implements Comparator<Student>
    ```
    전달

    ```java
    Arrays.sort(students, new MyComparator());
    ```

- static

  - 인스턴스 없이 사용하기 위함
  - 재사용 가능
  - 공용 데이터 사용하기 위함
  - 메모리 확보
  - 정적 변수

- 싱글톤

  - ```java
    Calendar cal = Calendar.getInstance();
    ```

- final
  - 바꿀 수 없다.