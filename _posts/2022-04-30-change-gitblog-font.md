---
layout: posts
title: jekyll-now theme 폰트 바꾸기
category: gitblog
classes: wide
---

## style.scss 파일 수정
### 1. 파일 상단에 아래 내용 추가
```scss
@import url('https://fonts.googleapis.com/css2?family=Nanum+Gothic&display=swap');
```
원하는 폰트 import 경로는 구글 폰트에서 가져오면 된다.

#### before
```scss
// in style.scss

...

/**************/
/* BASE RULES */
/**************/

html {
```

#### after
```scss
// in style.scss

...

/**************/
/* BASE RULES */
/**************/

@import url('https://fonts.googleapis.com/css2?family=Nanum+Gothic&display=swap');

html {
```

### 2. html 태그에 font-family 추가

#### before
```scss
// in style.scss

...

html {
  font-size: 100%;
}
```

#### after
```scss
// in style.scss

...

html {
  font-size: 100%;
  font-family: Nanum Gothic, sans-serif;
}
```

### 3. body 태그 font 수정

#### before
```scss
// in style.css

...

body {
  background: $white;
  font: 18px/1.4 $helvetica;
  color: $darkGray;
}
```

#### after
```scss
// in style.css

...

body {
  background: $white;
  font: 18px/1.4 Nanum Gothic, sans-serif;
  color: $darkGray;
}
```


### 4. font-family 설정된 부분 제거

```scss
// in style.scss

...

h1, h2, h3, h4, h5, h6 {
  font-family: $helveticaNeue; // 제거
  ...
}

.site-name {
  ...
  font-family: $helveticaNeue; // 제거
  ...
}

nav {
  ...
  font-family: $helveticaNeue; // 제거
  ...
```