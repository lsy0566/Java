## BufferedReader/BufferedWriter

> 입력 데이터가 중간에 버퍼링이 된 후에 전달
>
> 출력 데이터도 버퍼를 거쳐 간접적으로 출력장치로 전달되므로
>
> 데이터처리 효율성 증가
>
> 즉 버퍼에 입력받은 데이터를 모아뒀다가 한번에 보내면 속도가 현저히 빠르기 때문이다.

### BufferedReader

> Scanner는 Space Enter 모두 경계로 인식하여 데이터 가공하기 편리함에 반해 
> BufferedReader는 Enter만 경계로 인식하고 받은 데이터가 String으로 고정되므로
>
> 입력 데이터를 변환해야 하는 경우가 있다.

**사용법**

```java
BufferedReader bf = new BufferedReader(new InputStreamReader(System.in)); //선언
String s = bf.readLine(); //String시
int i = Integer.parseInt(bf.readLine()); //Int -> String이 아닌 데이터의 형변환 예시
```

입력시 readLine(); 메서드 활용

* 주의점
  * readLine()시 리턴값을 String으로 고정되므로 String이 아닌 다른타입으로 입력 받기 위해서는 형변환
  * 예외처리를 해주어야 함 -> readLine 할때 마다 try & catch 해도 되지만 보통 throws IOException 사용

**Read한 데이터 가공**

```java
StringTokenizer st = new StringTokenizer(s); //StringTokenizer인자값에 입력 문자열 삽입
int a = Integer.parseInt(st.nextToken()); //첫번째 호출
int b = Integer.parseInt(st.nextToken()); //두번째 호출

String array[] = s.split(" "); //공백마다 데이터를 끊어서 배열에 삽입
```

### BufferedWriter

> 일반적으로 출력  시 System.out.println("") 사용
>
> 많은 양의 출력에서는 입력과 같이 Buffer를 활용하는 것이 좋다.

**사용법**

```java
BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out)); //선언
String s = "abcdefg"; //출력할 문자열
bw.write(s+"\n"); //출력
bw.newLine(); //개행(줄바꿈)
bw.flush(); //남아있는 데이터를 모두 출력
bw.close(); //스트림을 닫음
```

> 이 경우 버퍼를 잡아놓았기 때문에 반드시 flush() / close() 호출하여 뒤처리를 해야한다.
>
> bw.write에는 System.out.println();과 같이 자동개행기능이 없으므로 할 경우 \n을 통해 따로 처리해야함

- 개행문자

  > newline 새줄문자 다음 줄로 이동하는 것

