---
layout: post
title:  "[Javascript] undefined와 null의 차이"
date:   2024-02-20 20:32:00 +0900
categories: 
    - dev
    - javascript
tag: Javascript
related_posts:
  - 
comments: true
---

- Table of Contents
{:toc .large-only}

## undefined
- 단어 그대로 아무것도 존재하지 않는 값
- 변수를 선언하고 값을 할당하지 않은 상태에서 변수를 사용하려고 할 때 개발자가 아닌 <span style="color:#3d8cd1;font-weight: bold;" >브라우저 엔진에서 자동할당</span>하고 리턴해주는 값

## null
- undefined와 같이 아무것도 존재하지 않는 값
- undefined와 다르게 개발자가 명시하여 사용하는 것으로 어떤 데이터 타입이 할당될지 모를 경우, <span style="color:#3d8cd1;font-weight: bold;" >개발자가 명시적으로</span> null을 부여하여 의도적으로 사용하는 존재하지 않는 값
- null은 참조할 필요가 없는 값에 할당하게 되면 <span style="color:#3d8cd1;font-weight: bold;" >특정 위치에 대한 참조가 제거 되기 때문에</span> 메모리 공간을 확보하는 데에 사용하여 메모리를 효율적으로 관리하고 싶을 때 사용할 수 있음