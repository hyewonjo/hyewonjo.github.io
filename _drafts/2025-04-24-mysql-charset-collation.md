---
layout: posts
title: MySQL Charset / Collation
classes: wide
category: MySQL
---

# charset
문자 인코딩은 사용자가 입력한 문자를 컴퓨터가 이해할 수 있는 포맷으로 만드는 것이다. 이 인코딩과 문자를 해독하는 디코딩을 하기 위해선 미리 **정해진 기준**을 바탕으로 입력과 해독이 처리되어야 하는데 이를 문자열 세트 또는 문자셋이라고 한다.

### 종류
- 한글 기반 서비스에서는 euckr, utf8mb4 사용
- 일본어는 cp932, utf8mb4 사용
- MS949(MSWIN949)
  - 한글 윈도우에서 기본적으로 사용됨
  - euckr 보다는 확장된 형태의 문자 집합
  - 유닉스 계열의 OS에서 사용하는 CP949와 똑같은 문자 집합이다.
- UTF-8
  - 최근에는 여러 나라의 언어를 동시에 지원하기 위해 기본적으로 UTF-8 문자 집합을 사용하는 추세

### MySQL 서버의 UTF-8
MySQL 서버에는 utf8과 utf8mb4 문자 집합이 별도로 존재한다. utf8mb4는 MySQL 5.5 버전부터 지원됐다. 

utf8 문자셋은 한 글자당 최대 3바이트까지만 지원됐다. 하지만 이모티콘의 발전으로 이는 문제가 되어서 MySQL 서버는 utf8mb4라는 새로운 문자 집합을 도입했다. 


출처
- https://ko.wikipedia.org/wiki/%EB%AC%B8%EC%9E%90_%EC%9D%B8%EC%BD%94%EB%94%A9
- Real MySQL 8.0 2권: 개발자와 DBA를 위한 MySQL 실전 가이드