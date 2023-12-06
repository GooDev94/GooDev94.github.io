---
layout: post
title:  "[Java_Error] ~ cannot be cast to java.lang.Integer"
date:   2023-12-04 11:48:00 +0900
categories: 
    - dev
    - java
tag: Java
related_posts:
  - _posts/2023/2023-12-04-java-tostring-valueof.md
  - _posts/2023/2023-12-04-java-error-cast-string.md
---

- Table of Contents
{:toc .large-only}

### 에러메시지
java.math.BigDecimal cannotbe cast to java.lang.Integer 
<br>
java.lang.Long cannotbe cast to java.lang.Integer
{:.message}

### 원인
강제로 Integer로 casting했기 때문

### 해결방법
변환하려는 객체를 먼저 **String.valueOf()**를 사용하여 String으로 변환하고 **Integer.parseInt**를 사용하여 Integer 형식으로 변환

~~~java
//오류 발생
int num = (Integer) map.get("bno");

//우선 해당 오브젝트를 String으로 변환한 후 Integer.parseInt
int num = Integer.parseInt(String.valueOf(map.get("bno")));
~~~
