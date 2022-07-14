# 목차😎
- [학습자세](#학습자세)
- [2-1. 백엔드개발 환경설정](#2-1-백엔드개발-환경설정)
	- [스프링 프레임워크와 주요 기능](#스프링-프레임워크와-주요-기능)
		- [1 스프링 프레임워크에는 여러가지 컴포넌트가 존재한다.](#1-스프링-프레임워크에는-여러가지-컴포넌트가-존재한다)
		- [2 스프링프레임워크의 핵심](#2-스프링프레임워크의-핵심)
	- [스프링부트부트](#스프링부트부트)
	- [@Component vs @Bean](#component-vs-bean)
		- [1 근데 실무에선 어떤 경우에 자동으로 찾아 생성하게 하고싶지 않을까?](#1-근데-실무에선-어떤-경우에-자동으로-찾아-생성하게-하고싶지-않을까)
		- [2 @Bean 이란?](#2-bean-이란)
	- [Gradle은 빌드 자동화 툴, 근데 빌드자동화 툴을 왜 사용할까?](#gradle은-빌드-자동화-툴-근데-빌드자동화-툴을-왜-사용할까)
	- [롬복라이브러리를 install한 후 디펜던시에 추가하고도 이클립스에 또 추가해야하는 이유?(어노테이션 프로세싱 설정)](#롬복라이브러리를-install한-후-디펜던시에-추가하고도-이클립스에-또-추가해야하는-이유어노테이션-프로세싱-설정)
- [2-2 백엔드서비스 아키텍처](#2-2-백엔드서비스-아키텍처)
	- [DTO를 사용하는 이유?](#dto를-사용하는-이유)
	- [RESTfulAPI](#restfulapi)
	- [관계형데이터베이스?](#관계형데이터베이스)
	- [JpaRepository는 인터페이스인데 어떻게 구현하는 클래스가 없어도 작동할까?](#jparepository는-인터페이스인데-어떻게-구현하는-클래스가-없어도-작동할까)
- [2-3 백엔드서비스 실습](#2-3-백엔드서비스-실습)
	- [Optional 리턴타입을 사용하는 이유?](#optional-리턴타입을-사용하는-이유)
	- [Service에서 delete메서드 구현시 내부 로직 캡슐화를 위해 e를 리턴하지 않는다는 건 무슨 의미일까?](#service에서-delete메서드-구현시-내부-로직-캡슐화를-위해-e를-리턴하지-않는다는-건-무슨-의미일까)
		- [배운점](#배운점)


<small><a href='https://magnetikonline.github.io/markdown-toc-generate/'> *Table of contents generated with markdown-toc</a></small>


***

# 학습자세

```
P39
대부분의 소프트웨어 엔지니어링 도구들은 어떤 문제의 해결을 위해 창안됐다.
따라서 우리가 사용하는 도구가 어떤 문제를 해결하는지, 또 어떻게 해결하는지에 대해 dkfdkqhf dPwjddlek.
```

새로운 기술이나 도구를 접할때 그 도구가 어떤 문제를 해결하는지, 또 어떻게 해결하는지에 대해 생각하면서 학습해야겠다.

# 2-1. 백엔드개발 환경설정
## 스프링 프레임워크와 주요 기능
프레임워크의 코드를 확장해서 사용한다는 의미는 무엇일까?
- 프레임워크가 제공하는 클래스나 라이브러리를 사용하는 것.
- 프레임워크가 제공하는 클래스나 인터페이스를 상속 및 구현해 코드를 프레임워크의 일부로 실행하는 것.

### 1 스프링 프레임워크에는 여러가지 컴포넌트가 존재한다.
- Spring ORM
- Spring Web
- Spring AOP
- Spring Messaging
- Spring Web MVC
- Springboot
![Overview of the Spring Framework](https://docs.spring.io/spring-framework/docs/4.0.x/spring-framework-reference/html/images/spring-overview.png)

여기서 컴포넌트란 구성요소의 의미로 독립적인 단위모듈이다.

### 2 스프링프레임워크의 핵심
한 단어로 표현하자면 바로 [의존성 주입(DI)](https://sowon-dev.github.io/2020/10/03/201003spring-1/#%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85-DI-Dependency-Injection)다.
의존성 주입은 [IoC(제어의 역행)](https://sowon-dev.github.io/2020/10/03/201003spring-1/#%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%ED%96%89-IoC-Inversion-of-Control)과 함께 많이 언급된다.
IoC는 제어를 역전하는 것을 설명하는 단어이고 DI는 디자인 패턴으로 IoC를 구현하는 방법 중 하나이다.
- 참고: [스프링 프레임워크에서 의존성 주입하는 3가지 방법](https://sowon-dev.github.io/2020/10/03/201003spring-1/#%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85-3%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95)

<br><br><br>
## 스프링부트부트
Stand-alone(스탠드 얼론)프로덕션급의 스프링 기반 애플리케이션을 쉽게 구동 가능.
Stand-alone(스탠드 얼론)이란? 애플리케이션 실행시 다른 애플리케이션(ex. 아파치 톰캣 등)이 필요하지 않다는 뜻.
어노테이션과 서브 클래스를 적절히 이용해 반복작업과 코드 최소화를 도와줌.

<br><br><br>
## @Component vs @Bean
@Component를 클래스에 달기만하면 무조건 스프링이 검색해주지 않는다! @ComponentScan이 있어야만 스프링이 컴포넌트를 스캔할 수 있다.
근데 기입하지 않아도 잘 찾는다. 그 이유는? @SpringBootApplication 안에 이미 @ComponentScan을 포함하고 있어서!
여기서 문제가 생김 -> if 스프링이 자동으로 오브젝트를 찾아 생성하게 하고 싶지 않을때는?
이때 사용하는 것이 @Bean이다. 

### 1 근데 실무에선 어떤 경우에 자동으로 찾아 생성하게 하고싶지 않을까?
1. 엔터프라이즈 애플리케이션의 경우 @Autowired를 사용하지 않는 경향이 있음 why? 엔지니어가 오브젝트를 어떻게 생성하고 어느 클래스에서 사용하는지 정확히 알아야 하는 경우가 많기 때문.
2. 사용할 라이브러리 클래스가 스프링 기반이 아니라서 @Component를 추가 못하는 경우

### 2 @Bean 이란?
@Bean을 이용해 스프링에게 오브젝트의 생성과 매개변수 등을 정확히 알려줄 수 있음.

프로젝트를 진행하면서 @Controller, @Service, @Repository 등 다양한 스트레오타입 어노테이션을 사용할텐데 이 어노테이션들은 내부에 전부 @Component가 달려있음!
> 그래서 내가 플젝할때 @Component를 쓴적이 없구나 깨달았다.

<br><br><br>
## Gradle은 빌드 자동화 툴, 근데 빌드자동화 툴을 왜 사용할까?
모든 자동화의 시작은 반복 작업때문! -> 웹 애플리케이션을 만들려면 여러 가지 라이브러리가 필요함 -> 빌드 자동화 툴이 없다면 라이브러리 사용을 위해 라이브러리 사이트(예를 들어 [메이븐 리포지토리](https://mvnrepository.com/))에서 jar 파일을 다운로드 받아서 이클립스의 Project Build Path에 해당 라이브러리 추가해야함. 매번 반복해야함
빌드자동화툴을 사용하면 `라이브러리를 다운받는 대신 원하는 라이브러리와 버전을 코드로 작성`하면 빌드자동화 툴이 해석해서 프로젝트 빌드에 필요한 작업을 해준다!

> 아하! build 설정파일에 있는 artifact은 애플리케이션이란 뜻임.

<br><br><br>
## 롬복라이브러리를 install한 후 디펜던시에 추가하고도 이클립스에 또 추가해야하는 이유?(어노테이션 프로세싱 설정)
그래들 디펜턴시에 라이브러리를 추가했지만 이건 그래들이 인식하는 라이브러리지 이클립스는 인식하지 못함. => 어노테이션 프로세싱을 설정해줘야함

***

<br><br><br><br>
# 2-2 백엔드서비스 아키텍처

## DTO를 사용하는 이유?

![DTO와 Domain클래스 쓰임차이](https://gmlwjd9405.github.io/images/spring-framework/spring-package-flow.png)

서비스가 요청을 처리하고 클라이언트로 반환할때 모델model 자체를 그대로 리턴하는 겨우는 별로 없다. DTO로 변환한다.
why?
1. 비즈니스 로직 캡슐화를 위해: 보통 모델은 DB테이블구조와 비슷해서 외부인에게 노출되길 원치않음
1. 쿨라이언트에게 필요한 정보를 모델이 다 가지고 있지 않음 ex)에러메시지

<br><br><br>
## RESTfulAPI
REST 조건
1. Client - Server: 리소스(html, json등)를 관리하는 서버가 존재하고 다수의 클라이언트가 리소스를 소비하려고 네트워크를 통해 서버에 접근하는 구조
1. Stageless(상태없음): 클라이언트가 서버에 요청을 보낼 때 서버는 이전 요청의 영향을 받지 않음을 의미, 서버는 이전 정보를 모른다.-> 그럼 로그인 상태유지는 how? 클라이언트가 정보를 가지고 요청해야함.
	- HTTP는 기본적으로 상태가 없는 프로토콜임. 따라서 HTTP를 사용하는 웹 애플리케이션은 기본적으로 상태가 없는 구조를 따른다.
1. Casheable 데이터: 서버에서 리소스를 리턴할 때 캐시가 가능한지 아닌지 명시할 수 있어야 함
1. Uniform interface: 리소스 접근할때 인터페이스가 일관적 + URI의 일관성
1. Layered system: 클라이언트는 서버 레이어 존재 유무를 알지 못함
1. Code-on-demand: 선택사항으로 클라이언트는 서버에 코드를 요청할 수 있고 서버가 리턴한 코드를 실행할 수 있음.

<br><br><br>
## 관계형데이터베이스?
[관계형DMBS란 클라이언트가 원하는 것을 요청할때 요청사항에 위치(where)이 포함되는게 아니라 그냥 what을 요청한다. 그러면 RDMBS는 어느 위치에 있는지 스스로 찾아 데이터를 가져온다.](https://sowon-dev.github.io/2020/05/28/200529dbi/)
보통 DB테이블마다 그에 상응하는 엔티티 클래스가 존재함.
> 아는 ORM이 jpa같은 기술을 지칭하는 용어인 줄만 알고 있었는데 dbconnection하고 prepareStatemnet하고 resultset하는 과정등을 ORM(Object-Relation Mapping)이라고 하는구나
- H2: In-Memory 데이터베이스로 로컬 환경에서 메모리상에 데이터베이스를 구축해줌

<br><br><br>
## JpaRepository는 인터페이스인데 어떻게 구현하는 클래스가 없어도 작동할까?
추상클래스나 인터페이스는 반드시 구현하는 클래스가 있어야 사용할 수 았다. 하지만 JpaRepository는 이 법칙을 무시하는 것 같다.
스프링은 MethodInterceptor라는 AOP를 사용함 -> JpaRepository 메서드 호출시 MethodInterceptor가 메서드 콜을 가로채서 메서드명 확인 후 일치하는 쿼리를 실행함.
저자는 AOP는 책 범위 밖이라 스스로 공부하길 추천했는데 기존에 공부한 자료가 있어 한 번 더 읽어보았다.
- [관점 지향(AOP, Aspect-Oriented Programming) 총정리](https://sowon-dev.github.io/2020/10/06/201007spring/)


<br><br><br><br>
# 2-3 백엔드서비스 실습

## Optional 리턴타입을 사용하는 이유?
[리턴타입에 굳이 옵셔널(Optional)인 이유?](https://sowon-dev.github.io/2022/07/10/220711JPA-optional/)

<br><br><br>
## Service에서 delete메서드 구현시 내부 로직 캡슐화를 위해 e를 리턴하지 않는다는 건 무슨 의미일까?

TodoService클래스에서 delete메서드 구현시 예외처리 하는 부분이 있다.

- TodoService.java
```java
public List<TodoEntity> delete(final TodoEntity entity) {
		// (1) 저장 할 엔티티가 유효한지 확인한다.
		validate(entity);

		try {
			// (2) 엔티티를 삭제한다.
			repository.delete(entity);
		} catch(Exception e) {
			// (3) exception 발생시 id와 exception을 로깅한다.
			log.error("error deleting entity ", entity.getId(), e);

			// (4) 컨트롤러로 exception을 날린다. 데이터베이스 내부 로직을 캡슐화 하기 위해 e를 리턴하지 않고 새 exception 오브젝트를 리턴한다.
			throw new RuntimeException("error deleting entity " + entity.getId());
		}
		// (5) 새 Todo리스트를 가져와 리턴한다.
		return retrieve(entity.getUserId());
	}
```

이때 `데이터베이스 내부 로직을 캡슐화 하기 위해 e를 리턴하지 않고 새 exception 오브젝트를 리턴한다.` 라는 설명이 있는데 추가 설명이 없어서 직접 고민해보았다.

1. `데이터베이스 내부 로직`은 보안이 중요하다.그 누구도 밖으로 유출하고 싶어하지않는다. 유출되는경우 해킹의 대상이 될 수 있다. 따라서 캡슐화([💊여기서 캡슐화란?](https://sowon-dev.github.io/2020/07/08/200709javai/#%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9D%80%EB%8B%89%EA%B3%BC-%EB%B3%B4%ED%98%B8-Encapsulation))가 필요하다.
2. Exception 인수를 노출하는 경우 안에 데이터베이스 내부 로직이 노출 될 수 있다. 따라서 새로운 new RuntimeException을 만들어 리턴한다.

### 배운점(BM)
앞으로 catch로 예외 잡을때 Exception인수는 로깅만 해놓고 절대 던지지(throw) 말아야겠다.