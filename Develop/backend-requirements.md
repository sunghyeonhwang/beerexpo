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

### 판단 기준
| 기능 | 정적 구현 조건 | 백엔드 필요 조건 |
|------|---------------|-----------------|
| 다운로드 (APPLICATIONDOWNLOAD/PROMOTIONALKIT) | 1~3개 고정 파일, 직접 링크 | 버전 관리/권한 제어/다운로드 로그 필요 시 |
| 스폰서십 (SPONSORSHIPPROGRAM) | PDF 안내서만 제공 | 문의 리드 수집/단계별 관리 필요 시 |
| 참가신청 (HOWTOAPPLY) | 외부 폼(구글 폼/타입폼) 사용 | 자체 CRM 연동/커스텀 워크플로우 필요 시 |
| 프로그램 (PROGRAM 하위) | 소개 전용 정적 페이지 | 참가 신청/정원 관리/대기열 운영 시 |
| 참가사 목록 (EXHIBITORLIST/FLOORPLAN) | 고정 목록/이미지 | 필터 검색/부스 실시간 상태/예약 기능 필요 시 |

### 1차 출시 권장사항
- **모두 정적 우선 구현**
- 운영 피드백 수집 후 2단계에서 백엔드 전환 여부 결정
- 정적 → 백엔드 전환 시 URL 구조 유지 (SEO 손실 방지)

## C. 정적 우선 (백엔드 불필요)
- `WHYKIBEX`, `OVERVIEW`, `ORGANIZERS`, `PARTNERS`
- `GALLERY`, `PHOTOGALLERY`, `SNS_` (임베드/링크 중심일 때)

## 3) MVP 백엔드 모듈 및 Phase 매핑

### Phase 1 (필수 - MVP)
**목표**: 핵심 콘텐츠 조회 + 신청 접수 기능

1. `content-service`
   - 공지/보도자료 목록 및 상세 조회
   - 고정공지 지원

2. `lead-service`
   - 참가신청/바이어등록/문의 접수
   - 기본 유효성 검증
   - 접수 확인 응답

3. `admin-service`
   - 운영자 인증 (로그인/로그아웃)
   - 신청 목록 조회
   - 기본 상태 변경 (접수/검토/확정/반려)
   - 게시글 CRUD

### Phase 2 (운영 고도화)
**목표**: 고급 워크플로우 + 파일 관리

4. `matching-service` 추가
   - 비즈니스 매칭 신청/상태 관리
   - 참가사-바이어 매칭 로직

5. `lead-service` 고도화
   - 파일 업로드 (신청서 첨부)
   - 다운로드 로그 추적
   - 버전 관리

6. `admin-service` 고도화
   - 운영 대시보드 (통계)
   - 담당자 배정 기능
   - 이력 조회 UI

### Phase 3 (확장)
**목표**: 외부 연동 + 자동화

7. 외부 연동
   - CRM 연동 (신청 데이터 동기화)
   - 메일 자동화 (접수/승인 알림)
   - 통계 대시보드 (전환율/문의 분석)

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

### 전송 보안
- 전송 구간 HTTPS 필수
- API 토큰/세션 쿠키 Secure/HttpOnly 플래그 설정

### 접근 제어
- 관리자 역할 기반 접근 제어 (RBAC)
- 최소 권한 원칙 적용
- 세션 타임아웃 설정 (30분 권장)

### PII(개인식별정보) 보안 정책

**민감 필드 정의 및 처리**
| 필드 | 저장 방식 | 관리자 조회 | 로그 기록 |
|------|----------|-----------|----------|
| email | 암호화 저장 | 복호화 표시 | 해시 처리 |
| phone | 암호화 저장 | 마스킹 (010-****-1234) | 해시 처리 |
| company_name | 평문 저장 | 평문 표시 | 평문 |
| contact_name | 암호화 저장 | 복호화 표시 | 해시 처리 |
| payload_json | 암호화 저장 | 복호화 표시 | 기록 안 함 |

**준수 규정**
- 개인정보보호법 (국내)
- 보관 기간: 행사 종료 후 1년 (법정 보관 의무)
- 삭제 요청: 접수 후 30일 내 처리
- 외부 제공: 본인 동의 없이 금지

**기술 요구사항**
- 암호화 알고리즘: AES-256-GCM 이상
- 키 관리: 환경 변수/KMS 사용 (코드 내 하드코딩 금지)
- 마스킹 함수 예시:
  - 이메일: `user@example.com` → `us**@ex******.com`
  - 전화: `010-1234-5678` → `010-****-5678`

### 감사 로그
- 상태 변경 이력 필수 기록
  - 변경 시각, 변경자, 이전 상태, 새 상태, 사유
- 보관 기간: 최소 3년
- 위변조 방지 (해시 체인 또는 불변 로그)

### 백업/복구
- 일일 자동 백업 (최소 7일 보관)
- 주간 전체 백업 (최소 4주 보관)
- RTO(복구 목표 시간): 4시간 이내
- RPO(복구 목표 시점): 24시간 이내

## 8) 단계별 구현 세부사항

### Phase 1 (필수 - MVP)
**구현 모듈**: content-service, lead-service, admin-service 기본

- Notice/Press API (content-service)
  - `GET /api/notices`, `GET /api/notices/{id}`
  - `GET /api/press-releases`

- 신청 접수 API (lead-service)
  - `POST /api/applications/exhibitor`
  - `POST /api/applications/buyer`
  - `POST /api/inquiries`

- 관리자 기본 기능 (admin-service)
  - `POST /api/admin/login`
  - `GET /api/admin/applications`
  - `PATCH /api/admin/applications/{id}/status`
  - `POST /api/admin/notices`, `PATCH /api/admin/notices/{id}`

**DoD**:
- 3종 폼(참가/바이어/문의) 저장 및 조회 가능
- 공지/보도 목록 동작
- 관리자 로그인 및 상태 변경 가능

### Phase 2 (운영 고도화)
**구현 모듈**: matching-service 추가, 기존 모듈 고도화

- Business Matching (matching-service)
  - `POST /api/matchings`
  - `GET /api/matchings/{id}/status`
  - `PATCH /api/admin/matchings/{id}/status`

- 파일 관리 (lead-service 확장)
  - 파일 업로드 엔드포인트 추가
  - 버전 관리 및 다운로드 로그

- 운영 대시보드 (admin-service 확장)
  - 통계 조회 API
  - 담당자 배정 기능

**DoD**:
- 매칭 신청 및 관리자 확정 워크플로우 동작
- 파일 첨부 및 이력 추적 가능

### Phase 3 (확장)
**구현 모듈**: 외부 연동 계층

- CRM/메일 자동화
  - 신청 시 자동 메일 발송
  - CRM 데이터 동기화 배치

- 고급 통계 대시보드
  - 전환율 분석 (페이지 → 신청)
  - 문의 유형별 분석
  - 월별 신청 추이

**DoD**:
- 메일 자동 발송 확인
- 통계 데이터 실시간 조회 가능

## 9) Definition of Done (백엔드)
- 필수 폼 3종(참가/바이어/문의) 저장 및 관리자 조회 가능
- 공지/보도 목록 및 상세 API 동작
- 상태 변경 이력 추적 가능
- 운영팀이 테스트 데이터로 E2E 검증 완료
