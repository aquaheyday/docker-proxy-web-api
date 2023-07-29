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
