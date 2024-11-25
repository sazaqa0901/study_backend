#기초 백엔드 11주차 과제

**일대일 관계**
: FK(외래키)를 이용하여 두 테이블을 각각 하나씩 연결함.

**일대다 관계**
: FK(외래키)를 이용하여 두 테이블을 하나씩 연결함. "다"쪽의 테이블이 FK를 가짐. ex. 한 글에 여러개의 댓글이 달림

**다대다 관계**
: FK(외래키)를 이용하여 두 테이블 간 여러 연결이 가능함. ex. 한 학생이 여러 강의를 신청함, 한 강의를 여러 학생이 신청함

Models.py 클래스 생성 -> DB 테이블 생성

- 클래스 멤버변수에 models.ForeignKey()를 생성하여 FK(외래키) 추가
 - FK 선언 시 to, on_delete parameter를 필수로 넣어야 함 class ForeignKEy(to, on_delete, **options)
- on : 해당 외래키가 연결될 (pk 값을 저장할) 테이블을 구현한 Model 클래스
- on_delete : 연결된 항목이 삭제되었을 떄 -> 해당 테이블의 FK column을 어떻게 할 것인가 설정하는 항목(여러 속성 지정 가능)
    - CASCADE로 설정 시 외래키로 연결된 항목이 삭제되면 해당 항목도 같이 삭제(주로 종속관계일 떄 사용)
    - PROTECT : FK(외래키)로 연결된 항목은 삭제할 수 없도록 삭제 시도 시오류를 띄움
    - SET_NULL, SET_DEFAULT : FK column을 각각 NULL과 default 값으로 변경
    - DO_NOTHING : 아무런 행동을 취하지 않음