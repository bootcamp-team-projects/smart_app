# Smart App — 농가·수확 관리 서비스

Flutter 앱과 Python 기반 API 백엔드 코드가 함께 포함된 팀 프로젝트 저장소입니다. 모델 및 데이터베이스 관련 모듈과 여러 업무 도메인의 API 라우터가 구성되어 있습니다.

## 프로젝트 개요

농가, 상품, 수확 일정, 예약, 주문, 배송 및 품질 검사 등 농산물 유통 업무를 지원하는 서비스의 앱·백엔드 구성 요소를 개발하기 위한 프로젝트입니다. 개별 기능의 완성 여부는 실제 구현과 실행 환경을 기준으로 확인해야 합니다.

## 주요 구성

- `lib/` — Flutter 앱 코드
- `backend/app/main.py` — FastAPI 애플리케이션 진입점
- `backend/app/routers/` — 인증, 상품, 주문, 수확 일정, 품질 분석 등 API 라우터
- `backend/app/models/` — 계정, 농가, 상품, 주문, 예약 및 관련 데이터 모델
- `backend/app/repositories/` — 데이터 접근 계층
- `backend/app/core/` — 설정, DB 연결, 보안 및 공통 로직

## 기술 스택

- Flutter / Dart
- Python / FastAPI
- SQLAlchemy 계열 데이터 접근 구조(실제 의존성 확인 필요)
- 관계형 데이터 모델 및 REST API 구조

데이터베이스 종류, 인증 방식, 필수 패키지와 환경변수는 백엔드 설정 파일 및 의존성 목록을 확인해 확정하세요.

## 실행 방법

### Flutter 앱

```bash
flutter pub get
flutter run
```

웹 실행을 지원하는 설정이라면 다음 명령도 사용할 수 있습니다.

```bash
flutter run -d chrome
```

### FastAPI 백엔드

프로젝트의 백엔드 의존성 파일과 설정을 확인한 뒤 가상환경에서 필요한 패키지를 설치하고 실행하세요. 현재 README에서는 검증되지 않은 requirements 경로나 환경변수를 단정하지 않습니다. 실행 진입점은 `backend/app/main.py`입니다.

## 보안 및 운영 유의사항

DB 접속 정보, JWT 비밀키, API 키 등은 환경변수로 관리하고 공개 저장소에 실제 값을 커밋하지 마세요. 결제·주문·품질 검사 기능의 운영 준비 상태는 별도 검증이 필요합니다.