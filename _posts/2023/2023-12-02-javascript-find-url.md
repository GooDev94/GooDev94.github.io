---
layout: post
title:  "[Javascript] 현재 페이지 URL 찾기"
date:   2023-12-02 13:58:00 +0900
categories: 
    - dev
    - javascript
tag: Javascript
related_posts:
    - 
---

- Table of Contents
{:toc .large-only}

javascript를 사용하여 현재 페이지 URL을 비롯하여 정보를 가져오는 방법을 알아보자

## <a href="https://developer.mozilla.org/en-US/docs/Web/API/Location">Location </a>
Location 인터페이스는 연결된 개체의 위치 URL을 나타낸다. 
<br>
Document 인터페이스와 Window 인터페이스는 **Document.location** 과 <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/location">**Window.location**</a>을 통해서 연결 위치를 가지게 된다.

1. window.location.href
: URL의 전체 문자열을 가져온다.

2. window.location.protocol
: 웹 프로토콜을 알려준다.

3. window.location.host
: URL의 호스트 정보를 가져온다.

4. window.location.hostname
: URL과 호스트명을 가져온다.

5. window.location.port
: URL의 포트번호를 가져온다.

6. window.location.pathname
: 호스트명 뒤의 경로를 가져온다.

7. window.location.search
: URL의 ? 뒤의 쿼리스트링을 가져온다.

## 테스트 해보기
- test url : http://localhost:4000/dev/db/mysql-alias-where/

<br>
<img width="500" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/49dcbfc8-fd6a-4796-8086-4c6d6ea61bb6">
