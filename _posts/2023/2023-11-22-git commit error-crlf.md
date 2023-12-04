---
layout: post
title:  "[Git_Error] LF will be replaced by CRLF  the neect time Git touches it"
date:   2023-11-22 21:15:18 +0900
categories: 
    - dev
    - git
tag: Git
related_posts:
    - 
---

- Table of Contents
{:toc .large-only}

React 실습하는 도중에 package-lock.json과 package.json 파일을 add 하는데 에러메시지가 발생했다.

### 약간의 사전지식
- CR(Carriage-Return) : 현재 커서를 줄 올림 없이 가장 앞으로 옮기는 동작
- LF (Line-Feed) :  커서는 그 자리에 둔 상황에서 종이만 한 줄 올려 줄을 바꾸는 동작
- CRLF (Carriage-Return+Line-Feed) : 줄바꿈

### 에러메시지
warning: in the working copy of ‘package-lock.json’, LF will be replaced by CRLF  the neect time Git touches it
warning: in the working copy of ‘package.json’, LF will be replaced by CRLF  the neect time Git touches it
{:.message}

### 원인
OS마다 줄바꿈에 대한 문자열이 다르기 때문에 git에서 어떤 방식으로 해야하는지에 대한 경고문을 띄워주는 것.

### 해결방법
- 운영체제에 맞춰 core.autocrl 기능 켜주기

~~~js
// Windows, DOS
git config --global core.autocrlf true

// Linux, MAC
git config --global core.autocrlf input
~~~

