# 쿠키를 사용한 상태관리

### 쿠키란?

- 웹 사이트 접속시 접속자의 개인 장치에 다운로드 되고 브라우저에 저장되는 작은 텍스트 파일이다.
- 웹 사이트는 쿠키를 통해 접속자의 장치를 인식하고, 접속자의 설정과 과거 이용내역에 대한 일부 데이터를 저장한다.
- 쿠키에는 만료일이 있으며, 만료 기준에 따라 세션쿠키, 지속적 쿠키가 있다.
  - 세션 쿠키 : 브라우저를 닫는 경우 자동으로 삭제되는 쿠키
  - 지속적 쿠키 : 수동으로 삭제되기 전까지 남아있거나 오랫동안 컴퓨터에 저장되는 쿠키
- 데이터의 형태는 Key, Value형태로 String문이며, 4KB 이상 저장이 불가하다.

</br>

### 쿠키를 사용한 상태 관리

**쿠키를 사용하지 않으면?**

- HTTP는 스테이트리스(stateless) 프로토콜이기 때문에 과거에 교환했던 리퀘스트와 리스폰스의 상태를 관리하지 않는다.
- 이 경우, 인증을 마친 상태를 잊어버리기 때문에 새로운 페이지로 이동할 때마다 재차 로그인 정보를 보내거나, 리퀘스트마다 매개 변수나 추가 정보를 붙여서 로그인 상태를 관리해야 한다.
- 이러한 문제로 쿠키 시스템을 도입하게 된다.

<br/>

**쿠키를 사용해 상태관리 하는 프로세스**

- HTTP 리퀘스트와 리스폰스에 쿠키 정보를 추가해서 클라이언트의 상태를 파악한다.

![https://hyunjun19.github.io/2017/09/23/how-cookie-works/http-req-res.png](https://hyunjun19.github.io/2017/09/23/how-cookie-works/http-req-res.png)

1. 쿠키는 서버에서 받은 리스폰스의 Set-Cookie라는 헤더 필드에 의해 쿠키를 클라이언트에 보존한다.
2. 다음 번에 클라이언트가 같은 서버로 리퀘스트를 보낼 때, 자동으로 쿠키 값을 넣어서 송신한다.
3. 서버는 클라이언트가 보내온 쿠키를 식별하여 어느 클라이언트가 접속했는지 체크하고 서버 상의 기록을 확인하여 이전 상태를 알 수 있다.