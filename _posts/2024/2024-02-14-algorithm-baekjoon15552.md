---
layout: post
title:  "[BaekJoon-Java] 1550 16진수"
date:   2024-02-14 21:57:00 +0900
categories: 
    - study
    - algorithm
tag:
    - algorithm
    - baekjoon
    - java
related_posts:
  - _posts/2024/2024-02-14-java-hex-to-decimal.md

---

- Table of Contents
{:toc .large-only}

## 문제
[백준 1550번](https://www.acmicpc.net/problem/1550)

<br><br>
<img width="884" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/06eeb052-c9ce-4a3c-8fc0-1da095c22851">


## 풀이
- Integer.parseInt를 사용하여 풀면 수월하게 해결 할 수 있음

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
