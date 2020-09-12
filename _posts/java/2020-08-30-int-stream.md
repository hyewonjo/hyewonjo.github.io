---
title: "IntStream"
categories:
    - Java
tags:
    - Java
last_modified_at: 2020-08-30
layout: single
classes: wide
---

# IntStream
## Stream
- Stream은 람다를 활용할 수 있는 기술 중 하나.
- 자바 8 이전에 배열 또는 컬렉션을 다루는 방법은 for 또는 foreach 문을 돌면서 요소 하나씩 꺼내서 다루었음.
  - 로직이 복잡해지면 루프를 여러 번 도는 경우가 발생
- Stream은 데이터의 흐름
- 배열 또는 컬렉션에 함수 여러 개를 조합하여 원하는 결과를 필터링하고 가공된 결과를 얻을 수 있다.
- 람다를 이용하여 코드를 간결하게 표현할 수 있다.
- 병렬처리가 가능하다.
  - .parallel() / .parallelStream() 만 추가하면 thread safe 한 병렬처리가 진행됨.

## Stream 단계
1. 생성하기 : 스트림 인스턴스 생성
2. 가공하기 : 필터링(filtering) 및 맵핑(mapping) 등
3. 결과 만들기

## boxed 메소드
- boxed() 메서드는 int, long, double 요소를 Integer, Long, Double 요소로 박싱해서 Stream을 생성한다.

###### 출처
- <small><http://dveamer.github.io/java/WhyDoWeNeedJava8.html></small>
- <small><https://futurecreator.github.io/2018/08/26/java-8-streams/></small>
- <small><https://cornswrold.tistory.com/297></small>