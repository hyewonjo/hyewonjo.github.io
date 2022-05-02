---
layout: posts
title: 클린 코더스 강의3. Function - The First Rule Of Functions
classes: wide
category: refactoring
---
출처 : [클린 코더스 강의3. Function](https://www.youtube.com/watch?v=GYNT7O3rLhU)

- 더 이상 작아질 수 없을 만큼 작아야 한다.
  - if, else, while 문장 등의 내부 블록은 한줄이어야 함
    - 괄호가 없어야 함
    - 함수 호출일 것
  - 함수는 중컵 구조를 가질 만큼 크면 안된다
    - indenting 은 한두단계 정도만
- 큰 함수를 보면 클래스로 추출할 생각을 해야함
- 클래스는 일련의 변수들에 동작하는 기능의 집합
- 큰 함수도 파라미터와 그 함수 내의 로컬 변수들에 동작하는 기능의 집합
  - 큰 함수는 클래스로 추출할 수 있다.

### 리팩토링 순서
1. extract method object
2. extract field
   1. 함수의 여러 곳에서 사용되는 변수는 필드로 추출 가능
   2. 필드로 변환함으로써
      1. 메소드의 파라미터 개수를 줄일 수 있다
      2. IDE 의 extract method 기능 사용시 2개 이상의 변수가 수정되어 메소드 추출이 불가능한 경우를 방지할 수 있다.
3. extract method
   1. 추출 후 불필요한 괄호 제거
      1. 괄호는 하나 이상의 책임을 갖는다는 증후
   2. inline variables 
   3. ```java
      // before
      if (includeSuiteSetup) {
           String pageName = SuiteResponder.SUITE_SETUP_NAME;
           String mode = "setup";
           includeInherited(pageName, mode);
       }
      ```
   4. ```java
      // after
      if (includeSuiteSetup)
           includeInherited(SuiteResponder.SUITE_SETUP_NAME, "setup");
      ```
4. 메서드 이름과 메서드 바디가 재인용하는 수준까지 가기 전까지 extract method
   1. 함수의 각 스텝들이 함수 이름이 갖는 추샇와 수준보다 한 단계 낮은 것으로만 이루어졌다면 함수는 한가지 일만 하는 것
   2. ```java
      // ok
      if (ifTestPage())
          surroundPageWithSetUpsAndTearDowns();
      ```
   3. ```java
      // not ok
      surroundPageWithSetUpsAndTearDownsWhenIfTestPage();
      ```


위 예제에서 나온 가장 긴 메서드명 : surroundPageWithSetUpsAndTestDowns()