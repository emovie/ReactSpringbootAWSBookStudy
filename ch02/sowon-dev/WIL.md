# 학습자세

```
P39
대부분의 소프트웨어 엔지니어링 도구들은 어떤 문제의 해결을 위해 창안됐다.
따라서 우리가 사용하는 도구가 어떤 문제를 해결하는지, 또 어떻게 해결하는지에 대해 dkfdkqhf dPwjddlek.
```

새로운 기술이나 도구를 접할때 그 도구가 어떤 문제를 해결하는지, 또 어떻게 해결하는지에 대해 생각하면서 학습해야겠다.

# 스프링 프레임워크와 주요 기능
프레임워크의 코드를 확장해서 사용한다는 의미는 무엇일까?
- 프레임워크가 제공하는 클래스나 라이브러리를 사용하는 것.
- 프레임워크가 제공하는 클래스나 인터페이스를 상속 및 구현해 코드를 프레임워크의 일부로 실행하는 것.

## 1 스프링 프레임워크에는 여러가지 컴포넌트가 존재한다.
- Spring ORM
- Spring Web
- Spring AOP
- Spring Messaging
- Spring Web MVC
- Springboot
![Overview of the Spring Framework](https://docs.spring.io/spring-framework/docs/4.0.x/spring-framework-reference/html/images/spring-overview.png)

여기서 컴포넌트란 구성요소의 의미로 독립적인 단위모듈이다.

## 2 스프링프레임워크의 핵심
한 단어로 표현하자면 바로 [의존성 주입(DI)](https://sowon-dev.github.io/2020/10/03/201003spring-1/#%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85-DI-Dependency-Injection)다.
의존성 주입은 [IoC(제어의 역행)](https://sowon-dev.github.io/2020/10/03/201003spring-1/#%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%ED%96%89-IoC-Inversion-of-Control)과 함께 많이 언급된다.
IoC는 제어를 역전하는 것을 설명하는 단어이고 DI는 디자인 패턴으로 IoC를 구현하는 방법 중 하나이다.
- 참고: [스프링 프레임워크에서 의존성 주입하는 3가지 방법](https://sowon-dev.github.io/2020/10/03/201003spring-1/#%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85-3%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95)

# 스프링부트부트
Stand-alone(스탠드 얼론)프로덕션급의 스프링 기반 애플리케이션을 쉽게 구동 가능.
Stand-alone(스탠드 얼론)이란? 애플리케이션 실행시 다른 애플리케이션(ex. 아파치 톰캣 등)이 필요하지 않다는 뜻.
어노테이션과 서브 클래스를 적절히 이용해 반복작업과 코드 최소화를 도와줌.

# 우리는 어느때 @Component를 사용하고 싶지 않을까?
엔터프라이즈 애플리케이션의 경우 @Autowired를 사용하지 않는 경향이 있음 why? 엔지니어가 오브젝트를 어떻게 생성하고 어느 클래스에서 사용하는지 정확히 알아야 하는 경우가 많기 때문.
