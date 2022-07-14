#### 프론트엔드와 백엔드의 분리
    - 스프링 부트 → REST API 구현 → 프론트엔드 애플리케이션이 사용
    - 프론트엔드는 꼭 웹일까? → 모바일 앱도 위에서 구현된 REST API 사용이 가능하다
    - 결론 : REST API와 프론트엔드 분리는 마이크로서비스 아키텍처로 확장에 용이
#### HTTP
    - HyperText Transfer Protocol
        - Transfer Protocol = 통신규약
        - HyperText = 다른 문서로 향하는 링크가 있는 텍스트
        - HTML 문서에서 발전 → 그림파일, 동영상, 3D (HyperMedia)
    - 요청과 응답
        - 클라이언트인 브라우저가 URL을 통해 서버에게 HTTP Request
        - 요청을 받은 서버는 HTTP Response, 브라우저에 렌더링 됨
    - HTTP method
        - GET(리소스 조회),POST(리소스 생성, 수정),PUT(리소스 대체),DELETE(리소스 삭제)
            
            HTTP method 의미는 절대적인 규칙이 아니다.
            
    - HTTP Response
        - 응답코드 : 200(성공), 404(리소스 존재하지 않음), 403(접근 권한 없음), 500(서버 에러)
        - Content-Type : text/html, text/css, application/json, video/mpeg
        - Keep-Alive, Cache-Control, Connection … : 통신과 관련한 정보
        - Response Body : 요청 처리 결과 ( 랜딩 페이지 HTML을 담아 반환 )
#### JSON
    - JavaScript Object Notation
    - Object(메모리상에 존재하는 어떤 자료 구조)를 표현하는 문자열
    - key-value 형태로 object를 표현하는 문자열

```
{
		"string" : "emovie",
		"number" : 2022,
		"boolean": true,
		"object" : { "key" : "value" },
		"array"  : [ "arr1", "arr2" ]
}
```

#### server
	- 지정된 포트의 소켓을 열고 클라이언트가 연결할 때까지 대기한다. 클라이언트가 연결되면 클라이언트 소켓에서 요청을 받아 수행하고 응답을 전달한다.
	- Java Server Class - ServerSocket, Socket
	- FTP(File Transfer Protocol)을 사용하면 FTP 서버가 되고, HTTP를 사용하면 HTTP 서버가 된다.

#### 정적 웹 서버
	- Static Web Server
	- HTTP 서버 중에서 리소스 파일을 리턴하는 서버, html 파일에 아무 작업도 하지 않고 파일을 있는 그대로 리턴함
	- 리소스의 경로를 지정하여 사용

### 동적 웹 서버
	- Dynamic Web Server
	- 요청을 처리 → 처리한 결과 → 응답 바디 재구성 또는 HTML 템플릿 파일에 결과 대체
	- 클라이언트와 parameter에 따라 응답이 다름
	- 동적 웹 서버 구현 헬퍼 자바 프로그램 → 서블릿 엔진=아파치 톰캣

### 자바 서블릿 컨테이너/엔진
	- 서버 프로그램
	- 개발자는 서블릿 엔진에게 자신의 비즈니스 로직(클래스 파일, 클래스 파일 요청 경로)을 알려줘야함
	- HttpServlet의 상속받는 서브 클래스란? 서블릿 엔진이 이해할 수 있는 클래스를 의미
