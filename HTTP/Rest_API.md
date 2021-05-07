# Rest API

- 기계와 기계가 규격화된 방식으로 웹을 이용해 통신하도록 돕는 통신규약
- API : 컴퓨터에 기능을 실행시키는 방법
- REST API 는 HTTP를 이용한다.

### 구성

1. 자원(Resource)
2. 행위(Method)
   - Create - post
   - Read - get
   - Update - put, fetch
   - Delete - delete
3. 표현(Representations)

### Post

- POST를 통해 해당 URI를 요청하면 리소스를 생성

### GET

- 콜렉션 읽기
- Element 읽기(데이터의 식별자를 'fetch/2'와 같이 뒤에 붙여준다)

### FETCH, PUT

- 부분수정 : fetch
- 전체수정 : put 전체가 수정되므로 전송하지 않은 데이터는 모두 삭제된다.

### Delete

- 데이터 삭제(콜렉션 삭제, Element삭제가 모두 가능)
