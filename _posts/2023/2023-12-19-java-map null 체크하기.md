---
layout: post
title:  "[Java] Map의 null 체크"
date:   2023-12-04 11:48:00 +0900
categories: 
    - dev
    - java
tag: Java
related_posts:
  - 
---

- Table of Contents
{:toc .large-only}

### Map의 null 여부 체크
NullPointerException 이 발생하지 않도록 Map의 null 여부를 체크한다.


## 방법1
<hr>
### 객체 map의 null 체크와 isEmpty 메소드를 호출하여 if문 처리
~~~java
Map<String, Object> tmpMap = new HashMap<>();

if (tmpMap != null && !tmpMap.isEmpty()) {
    log.info("map null 체크!");
}
~~~

## 방법2
<hr>
### gradle dependency를 추가하여 MapUtils.isEmpty() 사용
<br>
implementation group: 'org.apache.commons', name: 'commons-collections4', version: '4.0' 
~~~java
Map<Stirng, Object> tmpMap = new HashMap<String, Object>; 
MapUtils.isEmpty(tmpMap);
~~~
