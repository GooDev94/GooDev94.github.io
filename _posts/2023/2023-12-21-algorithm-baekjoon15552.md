---
layout: post
title:  "[BaekJoon-Java] 15552 빠른 A+B"
date:   2023-12-21 13:23:00 +0900
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
[백준 15552번](https://www.acmicpc.net/problem/15552)

<br><br>
<img width="884" alt="image" src="https://github.com/GooDev94/study_algorithm/assets/54229410/14f3115d-a57c-4778-b717-bb1cfa7e28b6">


## 주의할 점
- 주로 사용하던 **Scanner 클래스** 를 사용해서 하게 되면 **시간초과** 가 발생하게 된다. 
<br>에러는 아니지만 시간 제한 조건에 의해 사용할 수 없는 입력 방법이다.
<br><br>
<img width="274" alt="image" src="https://github.com/GooDev94/study_algorithm/assets/54229410/6bf62df8-aec9-44dd-891e-c7824d7f8ad1">


## 풀이
import java.io.BufferedReader;
<br>
import java.io.BufferedWriter;
{:.message}
- BufferedReader 를 통해 데이터를 입력 받고 BufferedWriter를 사용해서 출력 한다.
- BufferedReader 클래스는 String 으로 리턴하기 때문에 데이터를 가공하는 작업을 진행해야 한다는 단점이 있으나 속도가 더 빠르다.
- 출력 또한 System.out.println 를 사용할 수 있으나 이는 한 번에 한 번 찍기 때문에 시간이 더 걸려서 BufferedWriter 의 write()를 사용하여 한 번에 출력하여 속도를 단축할 수 있다.

~~~java

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.util.StringTokenizer;

public class Day2_15552 {

	public static void main(String[] args) throws IOException {
		//1. Scanner 사용
		/* 시간초과 발생
		Scanner sc = new Scanner(System.in);
		
		int T = sc.nextInt();
		for(int i=0; i<T; i++) {
			System.out.println(sc.nextInt() + sc.nextInt());
		}
		*/
		
		//2. BufferedReader 사용
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
		
		int T = Integer.parseInt(br.readLine());
		
		for(int i=0; i<T; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			int a = Integer.parseInt(st.nextToken());
			int b = Integer.parseInt(st.nextToken());
			
			bw.write(a+b + "\n");
			
		}
		
		bw.flush();
		bw.close();
		
	}

}


~~~
