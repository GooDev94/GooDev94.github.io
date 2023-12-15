---
layout: post
title:  "[Postman] Postman 에서 POST 메서드 날리기"
date:   2023-12-15 17:01:00 +0900
categories: 
    - study
    - tip
tag: postman
related_posts:
  - 
---

- Table of Contents
{:toc .large-only}

Postman을 사용에 미숙할 때 POST 메서드를 GET 방식처럼 Params에 파라미터값을 정의하여 날렸더니 500 Internal Server Error 가 발생했다.
<br>
<img width="827" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/82bd5af2-382b-41ab-b036-6a360594d2e4">

<br>
<br>
확인 해보니 파라미터가 제대로 전달 되지 않았고 Params에 정의하는 방식이 아님을 알게 되었다.


## Headers > key, value 세팅
- key : Content-Type
- value : application/json
<br>
<img width="609" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/efa07410-a29d-4053-b02b-54ea492256df">

## Body 설정
- raw 선택 & JSON 선택
- json 방식으로 파라미터 입력
<br>
<br>
<img width="464" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/6e21f009-de74-4cee-a892-5a97145a4474">

<br><br>
위처럼 설정하고 진행한다면 POST 메서드 방식으로 데이터를 확인 할 수 있다.
