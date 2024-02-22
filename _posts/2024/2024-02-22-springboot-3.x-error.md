---
layout: post
title:  "[SpringBoot_Error] SpringBoot 3.x 빌드 오류"
date:   2024-02-22 23:16:00 +0900
categories: 
    - dev
    - java
tag: [java, springboot]
related_posts:
  - 
comments: true
---

- Table of Contents
{:toc .large-only}


스프링부트 3.x은 Java 17 이상을 지원하기 때문에 새로 생성한 스프링부트 3.2.2 버전의 프로젝트를 지금까지 사용하던 Java 11 버전으로 빌드하려고 하자 오류가 발생하였다.

## 수정 전 프로젝트 환경
<hr>
- java 환경변수 설정 : 기존 Java 11버전
<br><br>
<img width="800" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/e9961f25-3652-490a-af98-0d65e6d2648c">
<br><br>
- IntelliJ 프로젝트를 생성할 때 자바를 설치할 수 있다고 해서 따로 환경변수 설정을 하지 않고 프로젝트 import 후 `Project Structure > Project Settings > Project` 의 SDK 를 No SDK 에서 17 버전 이상을 선택하여 설치하고 `Language level` 은 `SDK default` 로 설정
<br><br>
<img width="800" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/700717d2-5fe8-4f29-b2ce-b526921362b9">
<br>
<img width="800" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/53e6d166-69cd-451b-9d04-d17b1e2a129a">
<br><br>
- `Project Structure > Platform Settings > SDKs` 에 Java 17 버전 지정
<br><br>
<img width="800" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/581c5519-2836-4b7b-bc58-b516f43affbd">
<br><br>
이후 빌드를 진행했는데 아래 같은 오류 발생ㅠㅠ

## 오류 메시지
<hr>
긴 에러가 발생하면서 마지막에 BUILD FAILED 메시지가 나타났다.
~~~js
A problem occurred configuring root project 'hello-spring'.
> Could not resolve all files for configuration ':classpath'.
   > Could not resolve org.springframework.boot:spring-boot-gradle-plugin:3.2.2.
     Required by:
         project : > org.springframework.boot:org.springframework.boot.gradle.plugin:3.2.2
      > No matching variant of org.springframework.boot:spring-boot-gradle-plugin:3.2.2 was found. The consumer was configured to find a library for use during runtime, compatible with Java 11, packaged as a jar, and its dependencies declared externally, as well as attribute 'org.gradle.plugin.api-version' with value '8.5' but:
          - Variant 'apiElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.2.2 declares a library, packaged as a jar, and its dependencies declared externally:
              - Incompatible because this component declares a component for use during compile-time, compatible with Java 17 and the consumer needed a component for use during runtime, compatible with Java 11
              - Other compatible attribute:
                  - Doesn't say anything about org.gradle.plugin.api-version (required '8.5')
          - Variant 'javadocElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.2.2 declares a component for use during runtime, and its dependencies declared externally:
              - Incompatible because this component declares documentation and the consumer needed a library
              - Other compatible attributes:
                  - Doesn't say anything about its target Java version (required compatibility with Java 11)
                  - Doesn't say anything about its elements (required them packaged as a jar)
                  - Doesn't say anything about org.gradle.plugin.api-version (required '8.5')
          - Variant 'mavenOptionalApiElements' capability org.springframework.boot:spring-boot-gradle-plugin-maven-optional:3.2.2 declares a library, packaged as a jar, and its dependencies declared externally:
              - Incompatible because this component declares a component for use during compile-time, compatible with Java 17 and the consumer needed a component for use during runtime, compatible with Java 11
              - Other compatible attribute:
                  - Doesn't say anything about org.gradle.plugin.api-version (required '8.5')
          - Variant 'mavenOptionalRuntimeElements' capability org.springframework.boot:spring-boot-gradle-plugin-maven-optional:3.2.2 declares a library for use during runtime, packaged as a jar, and its dependencies declared externally:
              - Incompatible because this component declares a component, compatible with Java 17 and the consumer needed a component, compatible with Java 11
              - Other compatible attribute:
                  - Doesn't say anything about org.gradle.plugin.api-version (required '8.5')
          - Variant 'runtimeElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.2.2 declares a library for use during runtime, packaged as a jar, and its dependencies declared externally:
              - Incompatible because this component declares a component, compatible with Java 17 and the consumer needed a component, compatible with Java 11
              - Other compatible attribute:
                  - Doesn't say anything about org.gradle.plugin.api-version (required '8.5')
          - Variant 'sourcesElements' capability org.springframework.boot:spring-boot-gradle-plugin:3.2.2 declares a component for use during runtime, and its dependencies declared externally:
              - Incompatible because this component declares documentation and the consumer needed a library
              - Other compatible attributes:
                  - Doesn't say anything about its target Java version (required compatibility with Java 11)
                  - Doesn't say anything about its elements (required them packaged as a jar)
                  - Doesn't say anything about org.gradle.plugin.api-version (required '8.5')

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
> Get more help at https://help.gradle.org.
BUILD FAILED in 114ms

~~~


## 해결 방법
<hr>
아래 블로그를 참고하여 수정을 진행했다. <br>
[참고 블로그](https://jojoldu.tistory.com/698)

1) `Settings > Build, Execution, Deployment > Build Tooks > Gradle` 메뉴의 Gradle JVM 설정이 11로 되어 있는 것을 확인!
<br>
<img width="800" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/8cfd0e68-5db5-4adf-a6bd-f36a7029ac87">

<br>
2) Gradle JVM을 Java 17버전으로 수정한 후 빌드진행
<img width="800" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/87cf2b08-41eb-4128-a5d1-9854c8d55a35">

<br>
3) **BUILD SUCCESSFUL** 확인
<br>
<img width="800" alt="image" src="https://github.com/GooDev94/GooDev94.github.io/assets/54229410/f1ef6109-0b4b-4384-a67d-e4958a4c201c">