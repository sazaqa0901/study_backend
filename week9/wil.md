#기초 백엔드 스터디 9주차 과제

**브라우저 캐싱**
client와 server 간 응답속도를 높이기 위해 웹 페이지의 구성요소들을 사용자의 pc에 저장할 수 있다.

**HTTP Method**
해당 요청이 어떤 행동을 수행하는 메세지인지 전달하는 상태코드(http request의 맨 앞)
캐싱 가능한 요청 
    -단순 조회 요청
    -여러번 요청해도 결과 동일
    -url에 정보를 넣어 전달해도 됨
 => GET method 
    1. 웹 브라우저의 기본 HTTP Method
    2. 캐싱 기능 지원
    3. 정보 읽기, 검색 요청에 주로 사용
    4. url 정보를 넣어 전달

캐싱 불가능한 요청 
    -새로운 리소스 생성 요청
    -요청마다 결과 변경 가능
    -민감한 정보를 다룸
=> POST method
    1. 멱등성X(캐싱 기능 지원X)
    2. 새로운 요소 생성, 로그인 등에 사용
    3. Request Body에 정보 들어감

**Form 태그**
action 속성의 url로 데이터를 전송할 수 있다. method 속성에 지정한 http method를 이용하여 전송할 수 있다.
**Input 태그**
데이터를 입력 받을 수 있다.
-사용법 : 
<form action="localhost:8000/create" method="post">
    <input type="text"/>
    <input type="submit"/>
</form>

**redirect(PRG 패턴)**
사용자가 처음 요청한 url이 아닌 다른 url을 보낸다.
