# 스프링부트 프로젝트 생성

## 1. 환경 확인
#### 프로젝트 요구환경
* java8 이상
* build tool : gradle or maven
* IDE

#### 현재 PC 환경
* java : 설치되어 있지만, 버전 확인 필요 
* gradle : 설치되어 있을 것으로 추정
* IDE : intelliJ 설치되어 있음

#### 해야 할 일
- [ ] 자바 버전 확인 및 필요한 경우 업데이트
- [ ] gradle 설치 확인

----
## 2. 환경 구축
#### java 버전 확인
```shell
$ java -version
java version "1.8.0_201"
```
- [x] 자바 버전 확인 및 필요한 경우 업데이트

#### gradle 설치 확인
저는 Android Studio를 설치할 때, gradle이 같이 설치된 것을 확인했습니다. 환경변수 등록이 되어 있지 않았기 때문에, 환경변수 등록을 했습니다. 
```shell
$ gradle -v
------------------------------------------------------------
Gradle 5.1.1
------------------------------------------------------------
...
```
- [x] gradle 설치 확인
---
## 3. 스프링부트 프로젝트 만들기
#### 프로젝트 작성
1. `create new project`에서 `gradle`선택해서 프로젝트 생성
2. `build.gradle`에 스프링부트 관련 플러그인 추가
    * 관련문서 : https://spring.io/guides/gs/spring-boot/
3. 패키지 생성 후, 해당 패키지에 java Class 작성
```java
package com.handmadecode.test;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Application {
    public static vo
    id main(String[] args) {
        SpringApplication.run(Application.class,args);
    }
}
```
> **Spring boot: Failed to read candidate component class… Caused by: java.lang.ClassNotFoundException:**</br>
> 저의 경우는 default package에 class가 작성되어 있던 것이 원인이었습니다. 패키지 생성 후 클래스를 이동했더니 문제없이 작동하는 것을 확인했습니다.</br>
> * https://better-coding.com/solved-spring-boot-failed-to-read-candidate-component-class-caused-by-java-lang-classnotfoundexception-org-springframework-dao-dataaccessexception/*


#### 실행확인
프로젝트를 실행 후 `localhost:8080`으로 접속
> 밑의 화면이 표시된다면, 프로젝트 생성 완료!

![spring-boot-pj-start](/.img/spring-boot-start.PNG)
---
> 조만간 할 일 : gradle 사용법에 대해 정리하기

