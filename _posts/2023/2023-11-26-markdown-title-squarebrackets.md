---
layout: post
title:  "[Markdown] gitblog title에 대괄호 사용하기"
date:   2023-11-26 21:50:18 +0900
categories: 
    - study
    - blog
---

- Table of Contents
{:toc .large-only}

블로그에 대괄호를 사용하여 title 구분을 하려했는데 아래와 같은 메시지가 발생하면서 적용이 되지 않음.

### 에러메시지
Error: YAML Exception reading ~~~ did not find expected key while parsing a block mapping at line 2 column 1
{:.message}

### 원인
~~~js
// title에 대괄호 작성넣음
---
layout: post
title:  [Git_Error] LF will be replaced by CRLF  the neect time Git touches it
date:   2023-11-22 21:15:18 +0900
categories: Git 2023
tag: Git
---
~~~


### 해결방법
- title을 큰따옴표 ("") 나 작은따옴표 ('')로 감싸준다
~~~js
---
layout: post
title:  "[Git_Error] LF will be replaced by CRLF  the neect time Git touches it"
date:   2023-11-22 21:15:18 +0900
categories: Git 2023
tag: Git
---
~~~
