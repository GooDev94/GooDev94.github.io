---
layout: post
title:  "[Java] String.valueOf()와 toString()"
date:   2023-12-04 11:32:00 +0900
categories: 
    - dev
    - java
tag: Java
---

- Table of Contents
{:toc .large-only}

String.valueOf()와 toString()은 객체를 String형으로 변환할 때 사용하는 메소드이다.

## 공통점
<hr>
값을 String 형으로 변환

## 차이점
<hr>
객체가 null인 경우에 처리하는 방식이 다름

### 1. String.valueOf()
객체가 null일 경우 문자열 "null"을 출력

### 2. toString()
null인 값을 형 변환하게 되면 NullPointerException (NPE) 발생


~~~java
   public static void main(String[] args) {
        Object obj = null;

        //1. String.valueOf()를 활용한 형변환
        System.out.println(String.valueOf(obj));
        System.out.println(valChk(obj));
        System.out.println("--------------------");

        //2. toString()을 활용한 형변환
        try{
            System.out.println(obj.toString());

        }catch (Exception e){
            //toString()으로 형변환 시, NPE 발생
            System.out.println(e.toString());
        }

    }

    //String.valueOf() 의 경우 메소드를 정의하여 null 값을 다른 문자열로 바꿀 수 있다.
    static String valChk(Object obj){
        return obj == null ? "블로그 방문환영" : String.valueOf(obj);
    }
~~~
<br>
<img width="300" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/2815cbce-d151-48f1-b9da-79c7330857e5">

### 3. 추천
toString()은 NullPointerException이 발생할 수 있다는 점에서 **String.valueOf()**를 사용하는 것이 안정적이다.