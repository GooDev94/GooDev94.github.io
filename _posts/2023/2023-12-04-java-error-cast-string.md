---
layout: post
title:  "[Java_Error] ~ cannot be cast to java.lang.String"
date:   2023-12-04 11:48:00 +0900
categories: 
    - dev
    - java
tag: Java
related_posts:
  - _posts/2023/2023-12-04-java-tostring-valueof.md
---

- Table of Contents
{:toc .large-only}

### 에러메시지
java.lang.Integer cannot be cast to java.lang.String
{:.message}

### 원인
int를 String으로 강제 형변환을 하면서 발생
~~~java
String key = (String) map.get("key");

int num = 0;
String word = (String) num;
~~~

### 해결방법
캐스팅 변환을 하지 않고 String 클래스의 valueOf()를 사용

~~~java
String key = String.valueOf(map.get("key"));

String word = String.valueOf(num);
~~~
