---
layout: post
title:  "[BaekJoon-Java] 1271 엄청난 부자2"
date:   2023-12-20 13:09:00 +0900
categories: 
    - study
    - algorithm
tag:
    - algorithm
    - baekjoon
    - java
related_posts:
  - 

---

- Table of Contents
{:toc .large-only}

## 문제
[백준 1271번](https://www.acmicpc.net/problem/1271)

<br><br>
<img width="800" alt="image" src="https://github.com/GooDev94/study_algorithm/assets/54229410/8407ecb2-26c2-4656-a45e-02c2dca5db6e">

## 주의할 점
- 괄호에 있는 **(1 ≤ m ≤ n ≤ 10^1000, m과 n은 10진수 정수)** 라는 조건이다. int와 long 형으로 진행하기에는 10의 1000승은 숫자가 크다.
- 범위가 크기 때문에 주로 사용하던 int와 long의 사용은 [**런타임 에러 (InputMismatch)**](https://help.acmicpc.net/judge/rte) 를 발생시킨다.
<br><br>
<img width="500" alt="image" src="https://github.com/GooDev94/study_algorithm/assets/54229410/d20faff7-fc4a-4680-9fd3-62d4995d0163">


## 풀이
java.math.BigInteger
{:.message}
- BigInteger는 문자열 형태로 이루어져 있어 사실상 무한대의 정수형을 입력할 수 있기 때문에 int와 long 보다 큰 정수값을 연산할 때 활용할 수 있다.
- BigInteger는 계산을 위한 메서드들이 정의 되어 있어서 이번 문제는 BigInteger의 연산 메서드를 활용 한다.

~~~java
import java.math.BigInteger;
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		BigInteger n = sc.nextBigInteger();
		BigInteger m = sc.nextBigInteger();
		
		System.out.println(n.divide(m));
		System.out.println(n.mod(m));

	}

}

~~~
