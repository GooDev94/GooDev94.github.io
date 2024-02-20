---
layout: post
title:  "[Javascript] 브라우저 종류 확인하기"
date:   2024-02-20 20:25:00 +0900
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

## 인터넷 브라우저 확인하기

~~~javascript
// 익스플로러 체크
var agent = navigator.userAgent.toLowerCase();

if ( (navigator.appName == 'Netscape' && navigator.userAgent.search('Trident') != -1) || (agent.indexOf("msie") != -1) ) {
  alert("인터넷 익스플로러 브라우저 입니다.");
}else {
  alert("인터넷 익스플로러 브라우저가 아닙니다.");
}

// 크롬 체크
var agent = navigator.userAgent.toLowerCase();
if (agent.indexOf("chrome") != -1) {
  alert("크롬 브라우저입니다.");
}

// 사파리 체크
var agent = navigator.userAgent.toLowerCase();
if (agent.indexOf("safari") != -1) {
  alert("사파리 브라우저입니다.");
}

// 파이어폭스 체크
var agent = navigator.userAgent.toLowerCase();
if (agent.indexOf("firefox") != -1) {
  alert("파이어폭스 브라우저입니다.");
}

~~~
