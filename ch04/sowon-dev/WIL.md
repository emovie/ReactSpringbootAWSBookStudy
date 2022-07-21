# 목차😎
- [인증과 인가](#인증과-인가)
- [인코딩을 했는데 왜 문제가 될까?](#인코딩을-했는데-왜-문제가-될까)

<small><a href='https://magnetikonline.github.io/markdown-toc-generate/'> *Table of contents generated with markdown-toc</a></small>

***

# 인증과 인가
- 인증: 내 집에 들어올 수 있는 사용자
- 인가: 인증받고 들어온 사용자가 내 집에서 할 수 있는 것들
	- 화장실 사용, 주방사용, 거실사용 등등
	
인증에는 여러 방법이 있다.
책에서는 3가지 방법에 대해 이야기한다.
- 인증
	1. Basic 인증
	2. Bearer 인증
	3. JSON 웹 토큰

<br><br><br><br>
# 인코딩을 했는데 왜 문제가 될까?
Basic Auth에서는 아이디와 비밀번호를 인코딩한다. 이 솔루션은 아이디와 비밀번호를 노출한다.
인코딩을 했는데 왜 문제가 될까? 인코딩은 보안을 목적으로 하는 것이 아니기때문!
인간이 아이디와 비밀번호를 바로 알아내기 어렵지만 디코더만 있으면 누구나 원래의 아이디와 비번을 알아낼수 있다.
이렇게 가로채는 것을 MITM(Man in the middle attack)라고한다.