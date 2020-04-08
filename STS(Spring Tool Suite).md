## STS(Spring Tool Suite)

- 컨트롤+스페이스
  - 편한 명령어
  - 자동완성 기능
    - import 및 자동 함수 생성

- charAt()

  > () 안에 있는 번째만큼 가서 바로 그 뒤에 문자를 빼오는 것

  ```java
  public void setSsn(String ssn) {
  	this.ssn = ssn;
  	char flag = this.ssn.charAt(6); // 6번째 문자 or 숫자 바로 뒤 하나를 빼오는 것
  	if(flag == '1' || flag == '3') {
  		setGender('남');
  	}
  	else if(flag == '2' || flag == '4') {
  		setGender('여');
  	}
  }
  ```

- Collection

  - 값만 받음

  - List

    > 순서가 유지됨, 중복이 허용됨
    >
    > 제너릭스

    - ArrayList 대표적
      - thread - safe하지 않음 멀티스레드 할 시 따로 해줘야함 대신 속도가 빠름
    - Vector 초기
      - thread - safe하게 구현되있지만 seqeantial하게 처리하므로 느림

  - set

    > 순서 유지X, 중복 X

    - Hashset

- map

  - 키와 값을 둘다 받음
  - HashMap
    - non-safe
  - Hashtable 초창기
    - safe

- 클래스 다이어그램 용어
  - # 
    - protected
  - 기울어진 글자
    - 추상클래스 or 추상메소드
  
- interface
  
  - 바디가 있는 메소드 원래는 허용x 지금은 허용
  
- 추상 메소드
  
  - 바디가 있어도 없어도 상관 없음





