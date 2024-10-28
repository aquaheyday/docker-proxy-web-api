## 개요
도커 컴포즈를 이용한 개발환경 세팅 내용입니다.

## 실행되는 컨테이너 정보
버전 컨트롤의 용의성을 위해 각각 컨테이너를 별도로 실행하였습니다.

![docker구성](https://github.com/user-attachments/assets/49bfcbbd-3f31-4c77-b410-1764ecb5c861)

## 서버 구성
#### 프론트 접근시
1. / 루트 도메인으로 접근시 WEB 서버의 80포트로 포워딩되어 WEB 서버에 Flutter로 빌드된 프로젝트가 실행됩니다.
   
#### 백엔드 접근시
1. /api 도메인으로 접근시 API 서버의 80 포트로 포워딩되어 API 서버에서 PHP-FPM 서버의 9000 포트로 포워딩 되며, Laravel 프로젝트가 실행됩니다.
2. MySQL 컨테이너와 3306 포트를 이용해 통신하게 됩니다.

![도커순서 drawio](https://github.com/user-attachments/assets/72b75ad6-52f6-4e6e-9bdb-831f11d76c65)

#### 디렉터리 구조

![도커파일구성 drawio](https://github.com/user-attachments/assets/486e29e7-f7c0-4eaa-b76a-1413d2515045)

## 버전 정보
|server|type|version
|:--:|:--:|:--:
|proxy|nginx|1.25.1
|web|nginx|1.25.1
|api|nginx|1.25.1
|api|php|8.1-fpm
|api|mysql|8.0

## docker .env 설정 정보
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
