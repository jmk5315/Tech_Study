# 세션
  - 일정시간동안 같은 사용자(브라우저)로부터 오는 일련의 요청을 하나의 상태로 보고, 그상태를 일정하게 유지하는 기술.
  - 여기서 일정시간은 사용자가 웹 브라우저를 통해 웹 서버에 접속한 시점으로부터 웹 브라우저를 종료함으로써 연결을 끝내는 시점.
  - 즉, 방문자가 웹서버에 접속해 있는 상태를 하나의 단위로 보고 세션이라 함.

## 세션의 특징
  - 클라이언트 별로 각각의 상태 정보를 서버에서 저장함
  - 브라우저 종료시 삭제됨

## 세션의 동작 순서
  1. 클라이언트가 서버에 요청(사용자가 웹사이트 접근)
  2. 서버는 접근한 클라이언트의 Request-Header필드의 cookie를 확인하여 클라이언트가 세션 ID를 보냈는지 확인
  3. 세션 ID가 존재하지 않는다면, 서버는 세션 ID를 생성하여 클라이언트에게 전송
  4. 클라이언트는 해당 세션 ID를 쿠키에 저장하여 매 요청마다 세션 ID가 담긴 쿠키를 서버로 보냄
  5. 서버는 해당 세션 ID가 존재하는지 확인만 하면됨.

## 쿠키와 세션의 차이

  ||쿠키 cookie|세션 session|
  |----|---|---|
  |저장위치|클라이언트(로컬)|서버|
  |만료시점|쿠키 저장시 설정|브라우저 종료시 삭제|
  |보안|로컬에 저장되어 유실,변조,도난에 비교적 취약|서버에 저장되므로 비교적 안전|
  |속도|빠름|세션 ID를 이용하여 서버에서 존재하는지 확인하기 위해 데이터를 참조해야 하므로 비교적 느림|