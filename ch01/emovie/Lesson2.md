#### 스프링
  오픈 소스의 경량 프레임워크
  오픈 ( 코드 공개 ) + 경량 ( 메모리나 CPU 자원이 적게 듦 또는 사용이 쉽고 간편 )
  프레임워크 ( 개발자들이 확장해 사용하는 코드 )
  ⇒ 프레임워크가 제공하는 클래스나 라이브러리를 사용 또는 상속 및 구현하여 프레임워크 일부로 실행
  스프링 프레임워크의 핵심 - Dependency Injection 의존성 주입
  IoC( Inversion of Control )를 구현하는 방법 중 하나

#### 의존성 주입
  클래스가 의존하는 다른 클래스들을 외부에서 주입한다는 것을 의미

  1. 생성자 주입

  ```jsx
  public class MenuService {
    private final Menu menu;

    public MenuService(Menu menu) {
      this.menu = menu;
    }

    public class order() { ... menu.order(); }
    ...
  }

  public static void main(String[] args) {
    Menu menu = new Drink();
    MenuService service = new MenuService(menu);
  }
  ```

  2. Setter 주입

  ```jsx
  public class MenuService {
   private final Menu menu;

    public void setMenuService(Menu menu) {
      this.menu = menu;
    }
  }

  public static void main(String[] args) {
    Menu menu = new Bread();
    MenuService service = new MenuService();
    service.setMenuService(menu);
  }
  ```
  의존성 주입을 해주는 것 = Dependency Inject Container 의존성 주입 컨테이너 ( 그 중 하나가 스프링 프레임워크)

#### 스프링 프레임워크
- 의존성 주입 컨테이너가 필요한 이유 (스프링 프레임워크가 필요한 이유)
    프로젝트 규모, 관리할 오브젝트가 커지고 많을 수록 오브젝트 생성에 필요한 시간 증가
- 어노테이션, XML, 자바 코드를 통해 오브젝트(**Bean** , 빈) 간의 의존성 명시 가능

#### stand-alone
애플리케이션 실행 시 다른 애플리케이션이 필요하지 않다는 의미
- stand-alone이 아닌 애플리케이션은 ? 아파치 톰캣처럼 웹 서버/서블릿 컨테이너가 필요한 경우
    stand-alone이 아닌 경우 톰캣이 이해할 수 있도록 WAR 파일로 압축하여 배포해야함

#### @SpringBootApplication
- 해당 클래스가 스프링 부트를 설정하는 클래스임을 의미
- 해당 어노테이션이 달린 클래스가 있는 패키지를 스프링은 베이스 패키지로 간주함

#### @Component
- 클래스를 빈으로 등록시키는 어노테이션
- @Service에서도 @Component를 상속받는 것을 확인할 수 있음
  💡 단 @ComponentScan이 어떤 클래스에 있어야지만 컴포넌트 스캐닝이 가능
- @Component 위치는 @SpringBootApplication이 포함하고 있다.

#### @Bean
- @Component가 아닌 직접 빈을 관리할 때 사용하는 어노테이션
