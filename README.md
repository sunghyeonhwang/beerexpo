# beer_EXPO Workspace Guide

- Path: `/Users/griff_hq/Library/Mobile Documents/com~apple~CloudDocs/Reseach/Web/beer_EXPO`
- Updated: 2026-02-20
- 목적: 현재 폴더 구조와 문서 산출물 위치를 한 번에 확인

---

## 1) 루트 주요 파일

- `README.md`: 현재 문서(워크스페이스 안내)
- `content-map.md`: 7개 통합 페이지 구조 및 301 리다이렉트 매핑

---

## 2) 폴더 구조 요약

```
beer_EXPO/
├── Develop/          # 개발 명세 및 제안서
├── content/          # 수집/감사 자료 (중간 산출물)
├── final-copy/       # 배포용 콘텐츠 (7개 통합 파일) ⭐
├── planning/         # 기획 문서 (아카이브)
└── skills/           # 커스텀 스킬
```

---

## 3) 폴더별 상세

### `Develop/` - 개발 명세 및 제안서

#### 핵심 문서
- **`Develop/page-consolidation-proposal.md`** ⭐
  - 36개 → 7개 페이지 통합 제안서 (상세 버전)
  - 통합 효과, 구현 로드맵, 리스크 관리, 성공 지표 포함
  - 파워포인트 버전: `page-consolidation-proposal.pptx`

- **`Develop/backend-requirements.md`**
  - 서버 스펙 미정 상태를 전제로 한 백엔드 요구사항 문서
  - 페이지별 백엔드 필요도, 데이터 모델, API 계약, 단계별 구현안 포함
  - Phase별 모듈 매핑, PII 보안 정책, 조건부 기능 판단 기준 포함

- **`Develop/year-policy.md`**
  - 연도 표기 및 과거 데이터 처리 규칙
  - 2026/2025/2024 표기 원칙, 연도 전환 프로세스, QA 체크리스트

#### 참고 문서
- `Develop/front-spec_고려1.md`
  - 프론트엔드 구현 명세 (검토 중 - Tailwind 기반 예정)

---

### `final-copy/` - 배포용 콘텐츠 (7개 통합 파일) ⭐

#### 상태
- **통합 완료**: 36개 파일 → 7개 파일 (2026-02-20)
- **백업**: 기존 36개 파일은 `final-copy/archive/` 폴더에 보관

#### 7개 통합 파일

| 파일명 | 통합된 파일 수 | 라인 수 | 라우트 | 설명 |
|--------|--------------|---------|--------|------|
| `home.md` | 1개 | 62줄 | `/` | 메인 페이지 |
| `about.md` | 5개 | 169줄 | `/about` | 소개 (whykibex, overview, results, organizers, partners) |
| `exhibit.md` | 9개 | 290줄 | `/exhibit` | 참가 신청 (how-to-apply, 신청서, 스폰서십 등) |
| `visit.md` | 4개 | 152줄 | `/visit` | 방문 안내 (visitor-guide, 바이어 등록, 매칭, 교통) |
| `programs.md` | 6개 | 228줄 | `/programs` | 프로그램 (KIBCON, KIBA, Open Stage 등) |
| `news.md` | 2개 | 84줄 | `/news` | 소식 (공지사항, 보도자료) |
| `gallery.md` | 3개 | 111줄 | `/gallery` | 갤러리 (포토, 현장사진, SNS) |
| `contact.md` | 1개 | 51줄 | `/contact` | 문의 |

**총 라인 수**: 1,147줄

#### 특징
- 각 파일은 H2 (##) 헤더로 섹션 구분
- 원본 콘텐츠 그대로 보존 (통합만 수행)
- `Category`, `Title`, `H1`, `Status`, `Updated` 메타데이터 포함
- Hero/핵심요약/참석자별 안내/상세/CTA/SEO/검수메모 구조 유지

#### 구조 예시 (exhibit.md)
```markdown
---
Category: Exhibitors
Title: 참가 신청 | KIBEX 2026
H1: 참가하세요
Status: Final
Updated: 2026-02-20
---

## 참가 안내 (How to Apply)
[콘텐츠]

---

## 참가 신청 (Exhibitor Application)
[콘텐츠]

---

## 페어링 특별관 (Pairing Special)
[콘텐츠]

...
```

---

### `content/` - 수집/감사 자료

- 성격: 수집/분류/감사 자료 (중간 산출물 + 수동 정리 파일 포함)
- 주요 파일:
  - `content/beerexpo_plan_collect.md` (수동/기존 계획 파일)
  - `content/content-freshness-audit.md` (연도/최신성 점검 리포트)
  - `content/sitemap.md` (사이트맵)
- 하위 폴더:
  - `content/clipping/`: 페이지별 원문 클리핑
  - `content/collected/`: 수집/정제 원문 (`INDEX.md`, `README.md` 포함)
  - `content/functional/`: `Title/H1/Body` 기능 분해본 (`README.md` 포함)

---

### `planning/` - 기획 문서 (아카이브)

- 성격: 기획 문서 (디자인 제외)
- 상태: **아카이브** (통합 완료 후 참고용)
- 구성:
  - `planning/front-page.md` (메인 페이지 기획/카피 초안)
  - 페이지별 계획서 36개 (`how-to-apply.md`, `kibex2026.md`, `pairing-special.md` 등)
  - `planning/README.md` (포맷 설명)
- 용도:
  - 통합 전 원본 기획 참고
  - 섹션별 상세 요구사항 확인
  - 콘텐츠 누락 여부 검증

---

### `skills/` - 커스텀 스킬

- `skills/web-site-copywriter/SKILL.md`
  - 웹사이트 카피 정리용 커스텀 스킬
  - 요약+상세 2단 구조, 최신성 규칙, 최종 체크리스트 정의

---

## 4) 현재 작업 기준 추천 사용 순서

### 프론트엔드 개발 시
1. **사이트 구조 확인**: `content-map.md`
   - 7개 페이지 구조 및 라우팅
   - 301 리다이렉트 규칙
   - 앵커 링크 (#) 매핑

2. **콘텐츠 사용**: `final-copy/*.md` (7개 파일)
   - home.md, about.md, exhibit.md, visit.md
   - programs.md, news.md, gallery.md, contact.md

3. **백엔드 정의**: `Develop/backend-requirements.md`
   - API 계약 확인
   - Phase별 구현 우선순위

4. **연도 정책**: `Develop/year-policy.md`
   - 2026/2025 표기 규칙
   - 푸터 저작권 연도

### 기획 검토 시
1. **통합 제안서**: `Develop/page-consolidation-proposal.md`
   - 통합 효과 및 근거
   - 구현 로드맵

2. **원본 기획**: `planning/*.md` (아카이브)
   - 통합 전 상세 기획 참고

3. **원문 근거**: `content/collected/*.md` 및 `content/clipping/*.md`

---

## 5) 공통 운영 원칙

### 역할 분리
- **`final-copy/`**: 배포용 콘텐츠 (7개 통합 파일)
  - 프론트엔드 구현 시 직접 사용
  - 콘텐츠 업데이트는 이 폴더만 수정

- **`planning/`**: 기획 문서 (아카이브)
  - 통합 전 원본 기획 참고용
  - 더 이상 직접 수정하지 않음

- **`Develop/`**: 개발 명세 및 제안서
  - 백엔드/프론트엔드 구현 가이드
  - 통합 제안서 및 정책 문서

### 최신성 정책
- 연도 표기: `Develop/year-policy.md` 참고
  - 현재 행사: 2026년 명시
  - 실적 데이터: `전년도 기준` 또는 `2025년 기준` 라벨 병기
  - 푸터 저작권: `© 2026` 또는 `© 2024-2026`

- 일정/요금/마감/장소: 운영 최신 공지 기준으로 확정

### 변경 절차

#### 콘텐츠 업데이트 시
1. `final-copy/` 폴더의 7개 파일 수정
2. 연도 정책 준수 확인
3. Preview 환경에서 확인
4. 프로덕션 배포

#### 사이트 구조 변경 시
1. `content-map.md` 업데이트
2. 리다이렉트 규칙 반영
3. `Develop/page-consolidation-proposal.md` 참고

#### 백엔드 API 변경 시
1. `Develop/backend-requirements.md` 업데이트
2. Phase별 우선순위 확인
3. 프론트엔드와 계약 동기화

---

## 6) 빠른 참조

### 사이트 구조
```
📍 / (home.md)
📍 /about (about.md)
📍 /exhibit (exhibit.md)
📍 /visit (visit.md)
📍 /programs (programs.md)
📍 /news (news.md)
📍 /gallery (gallery.md)
📍 /contact (contact.md)
```

### 주요 문서
| 문서 | 경로 | 용도 |
|------|------|------|
| 사이트맵 & 리다이렉트 | `content-map.md` | 7개 페이지 구조 및 301 매핑 |
| 통합 제안서 | `Develop/page-consolidation-proposal.md` | 통합 근거 및 로드맵 |
| 백엔드 요구사항 | `Develop/backend-requirements.md` | API 계약 및 Phase |
| 연도 정책 | `Develop/year-policy.md` | 2026/2025 표기 규칙 |
| 배포 콘텐츠 | `final-copy/*.md` (7개) | 프론트엔드 구현용 |

### 통합 효과
| 항목 | 기존 | 신규 | 개선 |
|------|------|------|------|
| 페이지 수 | 36개 | 7개 | **-29개 (81%↓)** |
| 관리 파일 | 36개 | 7개 | **-29개** |
| 메뉴 깊이 | 2-3단계 | 1-2단계 | 단순화 |
| 연도 갱신 시 | 36개 수정 | 7개 수정 | **5배 효율** |

---

## 7) 다음 단계

### 프론트엔드 구현 준비 완료 ✅

1. **콘텐츠 준비** ✅
   - `final-copy/` 7개 파일 통합 완료
   - 원본 백업 (`final-copy/archive/`)

2. **라우팅 설계** ✅
   - `content-map.md` 7개 페이지 구조 정의
   - 301 리다이렉트 규칙 작성
   - Astro 예시 코드 제공

3. **개발 가이드** ✅
   - 백엔드 API 계약 정의
   - 연도 정책 수립
   - QA 체크리스트 작성

### 권장 구현 순서
1. **Week 1**: 7개 페이지 프론트엔드 스캐폴딩
2. **Week 2**: 콘텐츠 연동 (final-copy/*.md 파싱)
3. **Week 3**: UI/UX 구현 (Tab, Accordion, Card Grid)
4. **Week 4**: QA 및 배포

---

## 8) 참고

- `.DS_Store` 파일은 macOS 생성 파일로, 문서 작업과 무관
- `final-copy/archive/` 폴더는 원본 36개 파일 백업 (삭제 금지)
- 통합 완료일: 2026-02-20

---

## 9) 문의 및 지원

### 문서 관련
- 통합 제안서: `Develop/page-consolidation-proposal.md` 참고
- 파워포인트: `Develop/page-consolidation-proposal.pptx`

### 구현 관련
- 백엔드: `Develop/backend-requirements.md`
- 프론트엔드: `content-map.md` 섹션 5 "구현 참고사항"
- 연도 정책: `Develop/year-policy.md`

---

**상태**: 프론트엔드 구현 준비 완료 (2026-02-20) ✅
