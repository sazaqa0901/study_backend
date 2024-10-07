#기초 백엔드 스터디 4주차 과제

데이터베이스(DB)란?
데이터들을 저장하고 필요할 때 쓸 수 있도록 분류하고 관리해둠

정보를 저장하고 양식에 맞지 않는 정보는 받아들이지 않음
이러한 작업을 하는 소프트웨어를 데이터베이스 관리 시스템이라고 함
"데이터 관리 시스템 => dbms"
ex. mysql, redis, mongodb
dbms 종류에 따라 메모리 저장 위치 또는 형식이 달라짐(디스크vs메모리, key-value vs 문자열)

“관계형 데이터베이스(RDBMS)”
엑셀처럼 표에 데이터를 저장함 -> 테이블이라고 부름
1. 데이터 구조화
2. 중복 데이터 최소화
3. 유행을 따라갈 수 있음

명령어를 SQL이라고 부르고 영어 문법 구조와 유사함
장고를 사용하면 models.py에서 데이터 저장, 검색, 관리를 대신하주기 때문에 SQL를 잘 몰라도 됨
-model
1. 데이터베이스 생성
2. 데이터 입출력, 양식 변환
3. DBMS에 비종속적임 -> 코드 하나만 짜도 됨

PK(primary key)
1. 고유한 키(중복되지 않아야 함)
2. 잘 변경되지 않는 값
3. 모든 low가 가지는 값
db에는 반드시 pk가 하나씩 있음

정규화 => 테이블 나눠서 저장함
한 테이블에서 다른 테이블로 연결 시켜줌

다른 테이블의 pk를 가지고 있는 칼럼을 FK(foregin key)라고 함

실습내용
views 파일에 동적 html 생성
-name 변수 만들고 context라는 딕셔너리 만들기
-템플릿에 전달할 때 받은 요청 + 가공한 정보
따라서 html파일에서 넘겨준 정보 사용 가능

models.py에 클래스 만들기
-Question클래스는 장고 모델에서 models.Model에서 상속받음거임
python manage.py runserver(런 서버)
python manage.py makemigrations(장고는 models.py를 읽어서 바뀐 점을 확인하고 바뀐 내용을 migrations라는 폴더 안에 저장함 -> 0001_initial.py)
python manage.py migrate 명령어들 실행됨-> 데이터베이스 만들어줌(db.sqlite3)

어드민 기능
python manage.py createsuperuser(계정 등록)
admin.py에서 어드민 등록
python manage.py runserver

어드민 페이지 확인
127.0.0.1:8000/admin/