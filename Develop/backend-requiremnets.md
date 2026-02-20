# Backend Requirements (Stack-Agnostic)

- Project: beer_EXPO (KIBEX 2026)
- Updated: 2026-02-20
- Scope: 서버 스펙 미정 상태에서 바로 의사결정 가능한 백엔드 요구사항 정의

## 1) 전제
- 현재 콘텐츠는 `final-copy/*.md` 기준으로 정리됨
- 백엔드 기술 스택(Node, Python, Go, SaaS CMS 등)은 아직 미정
- 따라서 본 문서는 `기능/데이터/API 계약` 중심으로 작성

## 2) 페이지별 백엔드 필요도

## A. 백엔드 필수
1. `NOTICE` / `PRESSRELEASE`
- 필요 기능: 게시글 CRUD, 고정공지, 공개/비공개, 날짜/카테고리 관리
- 공개 API: 목록 조회, 상세 조회

2. `BUYERREGISTRATION`
- 필요 기능: 등록 폼 저장, 상태 관리(접수/검토/확정/반려), 알림(메일)
- 공개 API: 등록 제출, 제출 결과 조회
- 관리자 API: 상태 변경, 메모/태그 관리

3. `BUSINESSMATCHING`
- 필요 기능: 참가사-바이어 매칭 신청, 매칭 상태 추적, 관리자 배정
- 공개 API: 신청 제출/수정/취소, 상태 조회
- 관리자 API: 매칭 확정/변경

4. `HOWTOAPPLY` (온라인 신청 사용 시)
- 필요 기능: 참가 신청 접수, 파일 업로드, 접수 상태 관리
- 공개 API: 신청 제출, 접수 확인
- 관리자 API: 신청 검토/상태 변경

5. `EXHIBITORAPPLICATION` / `PAIRINGSPECIAL`
- 필요 기능: 일반 참가신청/특별관 참가신청 접수, 할인 조건 검증, 납부 상태 관리
- 공개 API: 신청 제출, 접수 확인
- 관리자 API: 신청 검토/상태 변경, 특별관 구분 처리

6. `CONTACTUS`
- 필요 기능: 문의 접수, 유형 분류, 담당자 할당, 응답 이력
- 공개 API: 문의 제출
- 관리자 API: 상태/담당자/응답 기록

## B. 조건부
1. `APPLICATIONDOWNLOAD` / `PROMOTIONALKIT` / `SPONSORSHIPPROGRAM`
- 단순 정적 링크면 불필요
- 문서/패키지 버전관리, 권한, 다운로드 로그, 스폰서십 문의 리드 관리 필요 시 백엔드 필요

2. `PROGRAM` 하위
- 소개 전용 정적 페이지면 불필요
- 참가 신청/정원/대기열 운영 시 백엔드 필요

3. `EXHIBITORLIST` / `FLOORPLAN`
- 고정 목록/이미지면 불필요
- 필터 검색/부스 실시간 상태 제공 시 백엔드 필요

## C. 정적 우선 (백엔드 불필요)
- `WHYKIBEX`, `OVERVIEW`, `ORGANIZERS`, `PARTNERS`
- `GALLERY`, `PHOTOGALLERY`, `SNS_` (임베드/링크 중심일 때)

## 3) MVP 백엔드 모듈 (권장)
1. `content-service`
- 공지/보도자료 조회

2. `lead-service`
- 참가신청/바이어등록/문의 접수

3. `matching-service`
- 비즈니스 매칭 신청/상태

4. `admin-service`
- 운영자 인증, 승인/반려, 게시 관리

## 4) 공통 데이터 모델 (초안)
1. `posts`
- id, type(notice|press), title, body, status, is_pinned, published_at

2. `applications`
- id, type(exhibitor|buyer), company_name, contact_name, email, phone, payload_json, status, created_at

3. `inquiries`
- id, category, name, email, phone, message, status, assignee, created_at

4. `matchings`
- id, applicant_id, preferred_categories, target_companies, status, admin_note

5. `files` (조건부)
- id, file_name, version, url, visibility, download_count

## 5) API 최소 계약 (예시)

## Public
- `GET /api/notices?limit=5`
- `GET /api/notices/{id}`
- `GET /api/press-releases?limit=10`
- `POST /api/applications/exhibitor`
- `POST /api/applications/buyer`
- `POST /api/inquiries`
- `POST /api/matchings`

## Admin
- `POST /api/admin/login`
- `PATCH /api/admin/applications/{id}/status`
- `PATCH /api/admin/matchings/{id}/status`
- `POST /api/admin/notices`
- `PATCH /api/admin/notices/{id}`

## 6) 스택 미정 상태에서 먼저 확정할 항목
1. 인증 방식
- 관리자만 필요한지, 외부 사용자 계정도 필요한지

2. 파일 업로드 정책
- 신청서 첨부 허용 여부, 최대 용량, 저장소(S3류/로컬)

3. 운영 정책
- 상태값 정의(접수/검토/확정/반려), SLA, 알림 채널(메일/메신저)

4. 데이터 보관/삭제
- 개인정보 보관기간, 마스킹, 삭제 프로세스

## 7) 보안/운영 최소 요구
- 전송 구간 HTTPS
- 관리자 접근 제어(역할 기반)
- PII 필드 암호화/마스킹
- 감사 로그(상태 변경 이력)
- 백업/복구 정책

## 8) 단계별 구현 제안
1. Phase 1 (필수)
- Notice/Press API
- Exhibitor/Buyer/Contact 접수 API
- Admin 기본 상태 변경

2. Phase 2 (운영 고도화)
- Business Matching 워크플로우
- 파일 버전관리/다운로드 로그
- 운영 대시보드

3. Phase 3 (확장)
- CRM/메일 자동화 연동
- 통계 대시보드(전환/문의/신청)

## 9) Definition of Done (백엔드)
- 필수 폼 3종(참가/바이어/문의) 저장 및 관리자 조회 가능
- 공지/보도 목록 및 상세 API 동작
- 상태 변경 이력 추적 가능
- 운영팀이 테스트 데이터로 E2E 검증 완료
