#### 개요
사내 문화 개선 프로젝트
막내의 커피 심부름 문화를 개선하여 여러 팀원들이 소통할 수 있는 장을 마련하여 보다 돈독한 팀관계 형성을 목적으로 한 프로젝트

#### 사용방법
1. 메뉴 접수를 위한 방을 생성한다.
2. 방 비밀번호 또는 초대 링크를 통해 접속하여 각자 메뉴를 접수한다.
3. 접수가 끝난 후 방을 마감하면 랜덤으로 배달원이 배정된다.

#### 구축정보
AWS EC2  인스턴스 생성 및 Load Balancers를 이용한 ssl 인증서 적용, Route 53 가비아 구매 도메인 연동
Docker 를 이용하여 proxy, api, web, db서버 구축 (nginx, mysql)
Laravel + MySql 을 이용해 RESTful API를 구축하기 위해 노력하였습니다.
ios, aos, web 을 구축하기 위해 flutter 를 사용하였습니다.

## docker-compose 를 이용한 proxy, web, api 세팅

#### 버전 정보
|server|type|version
|:--:|:--:|:--:
|proxy|nginx|1.25.1
|web|nginx|1.25.1
|api|nginx|1.25.1
|api|php|8.1-fpm
|api|mysql|8.0

#### .env 설정
|type|info|description
|:--:|:--:|:--:
|PORT|80|로컬 서버에서 접근할 포트 번호
|WEB_DIR|./../soruce/flutter|WEB 서버 소스 로컬 경로
|API_DIR|./../soruce/laravel|API 서버 소스 로컬 경로
|MYSQL_DIR|./../data/mysql|DB 정보 저장 로컬 경로
|MYSQL_ROOT_USER|root|MYSQL 루트 사용자 ID
|MYSQL_ROOT_PASSWORD|root|MYSQL 루트 사용자 PW
|MYSQL_API_DATABASE|laravel|API 서버에서 사용할 데이터베이스명
|MYSQL_API_USER|laravel|API 서버에서 사용할 사용자 ID
|MYSQL_API_PASSWORD|laravel|API 서버에서 사용할 사용자 PW
