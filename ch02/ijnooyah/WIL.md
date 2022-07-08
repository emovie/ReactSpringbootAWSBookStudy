









# 인텔리제이로 Spring Initializr 사용하기

![image](https://user-images.githubusercontent.com/85017704/177480488-c7a7b528-081e-44d3-bb3b-e73a9de197b6.png)

책에서 spring initializr 웹사이트를 통해 생성하는데

인텔리제이 안에서도 생성할 수 있다.



![image](https://user-images.githubusercontent.com/85017704/177480749-95cefc7b-cf10-4356-9000-9c91fa50ce06.png)

이렇게 dependncy 추가도 가능하다







# @Component

@Component는 스프링에게 이 클래스를 자바 빈으로 등록시키라고 알려주는 어노테이션.





# 백엔드 서비스 아키텍처

### 레이어드 아키텍처 패턴

![image](https://user-images.githubusercontent.com/85017704/177486047-89752b4d-22f1-4d94-b049-1dbc38bd0b6c.png)

- 스프링 프로젝트 내부에서 어떻게 코드를 적절히 분리하고 관리할 것이냐에 대한 것.
- 코드를 적절히 분리하고 관리하는 것은 코드 베이스가 커질수록 중요.
- 애플리케이션을 구성하는 요소들을 수평으로 나눠 관리하는 것.
- 레이러로 나눈다? 메서드를 클래스 또는 인터페이스로 쪼개는 것
- 레이어 사이에 계층이 있음.
  - 기본적인 레이어드 아키텍처에서는 상위레이어는 자신의 바로 하위 레이어만 사용한다.

### REST 아키텍처 스타일

- 클라이언트가 서비스를 이용하려면 어떤 형식으로 요청을 보내고 응답을 받는지에 대한 것.
- RESTful 서비스 : REST 아키텍처 스타일을 따라 설계 및 구현 된 서비스