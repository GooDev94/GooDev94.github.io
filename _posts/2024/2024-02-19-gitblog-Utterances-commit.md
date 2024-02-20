---
layout: post
title:  "[GitBlog] Gitblog에 댓글 기능 추가하기 (Utterances)"
date:   2024-02-14 21:59:00 +0900
categories: 
    - study
    - blog
tag: Blog
related_posts:
  - 
comments: true
---

- Table of Contents
{:toc .large-only}
아무래도 배우고 있는 것들에 대한 기록을 하다보니 분명 틀린 정보가 있을 수 있다고 생각하여 다른 능력자분들의 의견을 받아야겠다는 생각이 들었다.
<br>
기존에 사용하던 티스토리 블로그의 경우 자체 댓글 기능이 있었으나 gitblog는 직접 넣어줘야 했고 Github Issues를 활용하여 댓글을 다는 Utterances를 적용하기로 하였다.

# Utterances 적용하기
<hr>

### 1. [Utterances](https://github.com/apps/utterances) 에 접속한 후 Install을 클릭한다.
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/30600145-bb93-4587-8ce2-8b634a047c25">

### 2. 댓글 Issues가 올라올 저장소를 정한다.
-	모든 저장소에 업로드를 할지, 정해진 저장소의 Issues에만 업로드가 되게 할지를 선택한다.
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/e8a79695-f9d4-4ea3-bf8b-8c5fb04e4efd">
<br>


### 3. 댓글 Issues가 올라올 곳으로 저장소의 permalink를 적는다 
-	해당 gitblog의 repo로 할 생각이었기 때문에 **github아이디/저장소이름** 으로 진행
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/5280c69c-2cde-4af5-b394-1dd443bdd7c3">

<br>

> ※ 주의 ※
<br>
아래 이미지처럼 **github아이디 / 저장소이름** 와 같이 띄어쓰기가 중간에 들어가지 않도록 주의 할 것
<br>
repository 를 잘못 정의했을 경우 오류가 발생한다.
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/3ee6bdeb-822d-49cb-8b51-47a42280398a">


### 4. Theme 에서 블로그 색과 맞는 utterances의 색을 선택할 수 있다.
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/3b94a447-d35a-4844-ad1d-3eb94c6cc6be">
<br>


### 5. Enable utterances의 코드를 복사하여 댓글 구현을 담당하는 레이아웃 파일에 해당 코드를 추가한다.
- 아래의 코드에서 repo가 띄어쓰기가 들어가지 않았는지 확인한다. 첨부 이미지의 경우 오류가 났던 상태에서 캡쳐하여 띄어쓰기가 들어가서 오류 발생(ㅠㅠ)
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/bc78e7d2-68a3-4930-9b38-9e7f19cd3f5e">
<br>

- 해당 블로그의 경우 post.html 에서 comments.html 를 구현하고 있었기 때문에 comments.html에 복사한 코드를 추가하였다.
- 해당 블로그의 레이아웃은 comments라는 속성이 있어야 적용 때문에 글 작성 시 **comments: true** 로 속성을 부여한다. (댓글을 사용하지 않을 경우 false)
<br>
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/66db048d-fee7-4961-89b2-977253ea922e"><br><br>
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/c59bd835-3310-41d8-87e1-0da3c97077cd">
<br>

### 6. 댓글 테스트
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/4ddee02a-104e-40a9-8ca0-7cbbb52a064d">

<br>

### 7. 댓글이 잘 작성되면 정의했던 repository의 Issues에서 확인이 가능하다.
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/d6fac260-ce94-4f88-b126-ecb27831028b">