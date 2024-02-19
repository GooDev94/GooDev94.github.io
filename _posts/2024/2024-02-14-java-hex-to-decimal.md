---
layout: post
title:  "[Java] 16진수를 10진수로 변환하기"
date:   2024-02-14 21:59:00 +0900
categories: 
    - dev
    - java
tag: Java
related_posts:
  - _posts/2024/2024-02-14-algorithm-baekjoon15552.md
comments: true
---

- Table of Contents
{:toc .large-only}
java.lang 패키지에 있는 Integer 클래스를 사용하여 변환이 가능하다.

## 16진수를 10진수로 변환
<hr>
### Integer.parseInt()
Integer.parseInt(16진수, 16) 를 사용하여 0x가 아닌 16진수 문자열을 변환한다.
{:.message}

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		String hex = sc.nextLine();
		int decimal = Integer.parseInt(hex, 16);
		System.out.println(decimal);

	}

}
~~~

### Integer.decode()
Integer.decode(16진수) 를 사용하여 0x00로 시작하는 16진수 문자열을 변환한다.
{:.message}

~~~java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		String hex = sc.nextLine();
		int decimal = Integer.decode(hex);
		System.out.println(decimal);

	}

}
~~~

