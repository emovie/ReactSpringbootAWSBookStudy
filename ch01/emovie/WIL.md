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
