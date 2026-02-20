# 페이지 통합 제안서

- Project: beer_EXPO (KIBEX 2026)
- Updated: 2026-02-20
- 목적: 현대적인 사이트 구조로 페이지 통합 및 간소화

---

## 1) 현황 분석

### 현재 페이지 수
- **총 36개 페이지** (planning 폴더 기준)
- Alias 페이지: 5개
- 실제 콘텐츠 페이지: 31개

### 문제점
1. **중복 랜딩 페이지**: exhibitors-landing, visitors-landing, program-landing 등
2. **과도한 분할**: 다운로드, 홍보 키트 등이 별도 페이지로 존재
3. **비슷한 내용 분산**: whykibex, overview, show-results가 모두 "소개" 성격
4. **개별 프로그램 페이지**: 6개 프로그램이 각각 독립 페이지

### 현대적인 사이트 트렌드
- 일반적인 이벤트/전시 사이트: **6-8개 주요 페이지**
- Long-form 페이지 + 섹션/탭 구조
- 평평한 정보 구조 (깊이 최소화)
- 모바일 우선 네비게이션

---

## 2) 통합 제안: 36개 → 7개

### 최종 사이트맵

```
📍 / (홈)
📍 /about (소개)
📍 /exhibit (참가 신청)
📍 /visit (방문 안내)
📍 /programs (프로그램)
📍 /news (소식)
📍 /gallery (갤러리)
📍 /contact (문의)
```

---

## 3) 페이지별 통합 상세

### 페이지 1: 홈 (`/`)
**현재 파일**: `front-page.md` (1개)

**통합 콘텐츠** (섹션 구성):
- Hero (일정/장소/핵심 CTA)
- Why KIBEX (핵심 가치 3-4줄)
- 주요 수치 (전년도 실적 하이라이트)
- 참가 대상 카드 (참가사/바이어/일반관람객)
- 주요 프로그램 미리보기 (4-6개)
- 파트너/후원사 로고
- Latest News (최근 3개)
- Final CTA

**삭제 가능한 Alias**:
- ❌ `kibex2026.md` → `/` 리다이렉트
- ❌ `exhibitors-landing.md` → `/exhibit` 리다이렉트
- ❌ `visitors-landing.md` → `/visit` 리다이렉트
- ❌ `program-landing.md` → `/programs` 리다이렉트

**상태**: 유지 (1개)

---

### 페이지 2: 소개 (`/about`)
**통합 대상**: 5개 → 1개

#### 병합할 파일
1. `whykibex.md` - 왜 참가해야 하나
2. `overview.md` - 전시 개요
3. `show-results-2025.md` - 전년도 성과
4. `organizers.md` - 주최/주관 정보
5. `partners.md` - 파트너/후원사

#### 섹션 구조
```
/about
├─ Overview (전시 개요)
│  - 행사 소개, 역사, 비전
├─ Why KIBEX (차별점/가치 제안)
│  - 핵심 강점 3-5개
├─ 2025 Results (전년도 실적)
│  - 참가사 수, 방문객 수, 프로그램 성과
│  - 데이터 시각화 (인포그래픽)
├─ Organizers (주최/주관)
│  - 주최/주관사 로고 및 설명
└─ Partners (후원사/파트너)
   - 로고 그리드
```

**절감**: 5개 파일 → 1개 페이지

---

### 페이지 3: 참가 신청 (`/exhibit`)
**통합 대상**: 9개 → 1개

#### 병합할 파일
1. `how-to-apply.md` - 참가 안내 (메인)
2. `exhibitor-application.md` - 일반 참가 신청
3. `pairing-special.md` - 특별관 참가
4. `sponsorship-program.md` - 후원 프로그램
5. `application-download.md` - 신청서 다운로드
6. `promotional-kit.md` - 홍보 자료
7. `exhibitor-list.md` - 참가사 목록
8. `floor-plan.md` - 부스 배치도

#### 탭/섹션 구조
```
[Sticky Tab Navigation]
참가 안내 | 신청 유형 | 다운로드 | 참가사 목록 | 배치도

섹션 1: 참가 안내
- 신청 절차 (타임라인 UI)
- 참가 혜택 (아이콘 그리드)
- 요금 안내 (테이블)

섹션 2: 신청 유형 (카드 3개)
┌─────────────┐ ┌─────────────┐ ┌─────────────┐
│ 일반 부스    │ │ 특별관       │ │ 후원 프로그램 │
│ [신청하기]   │ │ [신청하기]   │ │ [문의하기]   │
└─────────────┘ └─────────────┘ └─────────────┘

섹션 3: 다운로드
- 📄 신청서 다운로드
- 📦 홍보 키트 다운로드

섹션 4: 참가사 목록
- 검색/필터 기능
- 카테고리별 분류

섹션 5: 부스 배치도
- 인터랙티브 맵 또는 확대 가능 이미지
```

**절감**: 9개 파일 → 1개 페이지

---

### 페이지 4: 방문 안내 (`/visit`)
**통합 대상**: 5개 → 1개

#### 병합할 파일
1. `visitor-guide.md` - 방문 안내 (메인)
2. `buyer-registration.md` - 바이어 등록
3. `business-matching.md` - 비즈니스 매칭
4. `amenities-transportation.md` - 편의시설/교통

#### 탭 구조
```
[Tab Navigation]
일반 관람 | 바이어 등록 | 비즈니스 매칭 | 오시는 길

탭 1: 일반 관람 안내
- 관람 시간, 입장료
- 사전 등록 방법
- 현장 등록 안내

탭 2: 바이어 등록
- 바이어 등록 자격
- 혜택 안내
- 등록 폼

탭 3: 비즈니스 매칭
- 매칭 프로그램 소개
- 신청 방법
- 신청 폼

탭 4: 오시는 길 & 편의시설
- 지도 (Google Maps 임베드)
- 대중교통 안내
- 주차 정보
- 편의시설 (식음료, 휴게실, Wi-Fi)
```

**절감**: 5개 파일 → 1개 페이지

---

### 페이지 5: 프로그램 (`/programs`)
**통합 대상**: 6개 → 1개

#### 병합할 파일
1. `kibcon.md` - KIBCON 세미나
2. `kiba.md` - KIBA 어워드
3. `open-stage.md` - 오픈 스테이지
4. `the-brew-in-tour.md` - The Brew-in Tour
5. `new-product-showcase.md` - 신제품 쇼케이스
6. `drink-seoul-2025.md` - Drink Seoul

#### 카드 그리드 + 아코디언 구조
```
[프로그램 개요 섹션]
"KIBEX 2026에서 펼쳐지는 다양한 프로그램"

[카드 그리드 - 3열]
┌────────────┐ ┌────────────┐ ┌────────────┐
│ 🎤 KIBCON  │ │ 🏆 KIBA    │ │ 🎭 Open    │
│ 세미나     │ │ 어워드     │ │ Stage      │
│ [자세히]   │ │ [자세히]   │ │ [자세히]   │
└────────────┘ └────────────┘ └────────────┘

┌────────────┐ ┌────────────┐ ┌────────────┐
│ 🍺 Tour    │ │ ✨ 신제품   │ │ 🌆 Drink   │
│ Brew-in    │ │ 쇼케이스   │ │ Seoul      │
│ [자세히]   │ │ [자세히]   │ │ [자세히]   │
└────────────┘ └────────────┘ └────────────┘

[클릭 시 아코디언 확장 또는 모달]
각 프로그램:
- 아이콘/이미지
- 제목
- 한 줄 설명
- 일정/장소
- 상세 설명
- 참가 신청 버튼 (해당 시)
```

**UI 패턴**:
- 모바일: 1열
- 태블릿: 2열
- 데스크톱: 3열

**절감**: 6개 파일 → 1개 페이지

---

### 페이지 6: 소식 (`/news`)
**통합 대상**: 2개 → 1개 (+ 동적 상세 페이지)

#### 병합할 파일
1. `notice.md` - 공지사항
2. `press-release.md` - 보도자료

#### 구조
```
/news (목록 페이지)
├─ 필터: 전체 | 공지사항 | 보도자료
├─ 검색 기능
└─ 목록 (카드 또는 리스트)

/news/[id] (동적 상세 페이지)
├─ 제목
├─ 카테고리/작성일
├─ 본문
└─ 이전글/다음글 네비게이션
```

**백엔드 필요**:
- CMS 또는 API 연동 (content-service)
- 페이지네이션

**절감**: 2개 파일 → 1개 동적 페이지

---

### 페이지 7: 갤러리 (`/gallery`)
**통합 대상**: 3개 → 1개

#### 병합할 파일
1. `gallery-landing.md` - 갤러리 메인
2. `photo-gallery.md` - 사진 갤러리
3. `sns.md` - SNS 피드

#### 탭 구조
```
[Tab Navigation]
사진 갤러리 | SNS 피드

탭 1: 사진 갤러리
- Lightbox 그리드
- 연도별/카테고리별 필터
- 클릭 시 전체 화면 보기

탭 2: SNS 피드
- Instagram/Facebook 임베드
- 또는 #KIBEX2026 해시태그 피드
```

**절감**: 3개 파일 → 1개 페이지

---

### 페이지 8: 문의 (`/contact`)
**현재 파일**: `contact-us.md` (1개)

**섹션 구성**:
- 문의 폼 (이름/이메일/연락처/문의 유형/내용)
- 오시는 길 (간단 지도)
- FAQ (아코디언)
- 연락처 정보

**상태**: 유지 (1개)

---

## 4) 통합 효과 분석

### 정량적 효과

| 구분 | 현재 | 제안 | 절감 |
|------|------|------|------|
| **총 페이지** | 36개 | 7개 | **-29개 (81%↓)** |
| 정적 페이지 | 31개 | 7개 | -24개 |
| Alias | 5개 | 0개 | -5개 |
| 네비게이션 깊이 | 2-3단계 | 1-2단계 | 개선 |
| 관리 파일 수 | 36개 | 7개 | **-29개** |

### 정성적 효과

#### 1. UX 개선
- ✅ 정보 찾기 쉬움 (7개 메뉴 vs 36개 페이지)
- ✅ 모바일 네비게이션 단순화
- ✅ 스크롤/탭으로 관련 정보 한 번에 확인
- ✅ 사용자 여정(Journey) 명확화

#### 2. 유지보수 간소화
- ✅ 29개 파일 관리 부담 제거
- ✅ 중복 콘텐츠 제거
- ✅ 연도 갱신 시 7개 페이지만 수정
- ✅ 일관성 유지 용이

#### 3. SEO 개선
- ✅ 페이지당 콘텐츠 밀도 증가
- ✅ 키워드 집중도 상승
- ✅ 내부 링크 구조 단순화
- ✅ 크롤링 효율성 향상

#### 4. 성능 향상
- ✅ 초기 라우팅 설정 간소화
- ✅ 번들 사이즈 감소
- ✅ 빌드 시간 단축
- ✅ 페이지 로딩 속도 개선

---

## 5) 구현 로드맵

### Phase 1: 콘텐츠 통합 (1주)
**목표**: 36개 파일을 7개 파일로 병합

**작업**:
1. `final-copy/` 폴더 재구성
   - 7개 새 파일 생성
   - 기존 36개 파일 내용을 섹션별로 통합
   - 마크다운 헤더로 섹션 구분

2. 콘텐츠 정리
   - 중복 내용 제거
   - 일관된 톤앤매너 적용
   - 연도 정책 준수 확인

3. 검토 및 승인
   - 통합된 콘텐츠 리뷰
   - 누락 내용 확인

**산출물**: `final-copy/` 내 7개 파일

---

### Phase 2: 라우팅 및 리다이렉트 설정 (3일)
**목표**: SEO 손실 방지 및 기존 URL 호환성 확보

**작업**:
1. `content-map.md` 업데이트
   - 새로운 7개 페이지 기준으로 갱신
   - 301 리다이렉트 규칙 정의

2. 리다이렉트 매핑 예시
```
# Alias → 홈
/kibex2026 → /

# Exhibitors 관련 → /exhibit
/exhibitors-landing → /exhibit
/how-to-apply → /exhibit
/sponsorship-program → /exhibit#sponsorship
/application-download → /exhibit#download
/promotional-kit → /exhibit#download
/exhibitor-list → /exhibit#list
/floor-plan → /exhibit#floorplan

# Visitors 관련 → /visit
/visitors-landing → /visit
/visitor-guide → /visit
/buyer-registration → /visit#buyer
/business-matching → /visit#matching
/amenities-transportation → /visit#access

# Programs 관련 → /programs
/program-landing → /programs
/kibcon → /programs#kibcon
/kiba → /programs#kiba
/open-stage → /programs#openstage
/the-brew-in-tour → /programs#tour
/new-product-showcase → /programs#showcase
/drink-seoul-2025 → /programs#drinkseoul

# News 관련 → /news
/news-landing → /news
/notice → /news?category=notice
/press-release → /news?category=press

# Gallery 관련 → /gallery
/gallery-landing → /gallery
/photo-gallery → /gallery
/sns → /gallery#sns

# About 관련 → /about
/whykibex → /about#why
/overview → /about#overview
/show-results-2025 → /about#results
/organizers → /about#organizers
/partners → /about#partners
```

3. 프론트엔드 라우팅 설정
   - Astro 또는 선택한 프레임워크에서 리다이렉트 구현
   - `astro.config.mjs` 또는 서버 설정에 301 리다이렉트 추가

**산출물**:
- 업데이트된 `content-map.md`
- 리다이렉트 설정 파일

---

### Phase 3: UI/UX 구현 (2주)
**목표**: 7개 페이지 프론트엔드 구현

**작업**:
1. 공통 컴포넌트 개발
   - Tab Navigation
   - Accordion
   - Card Grid
   - Sticky Navigation
   - Lightbox Gallery

2. 페이지별 구현
   - `/` (홈) - Hero + 섹션 구성
   - `/about` - Long-form 페이지
   - `/exhibit` - Sticky Tab + 다운로드 섹션
   - `/visit` - Tab Navigation
   - `/programs` - Card Grid + Modal/Accordion
   - `/news` - 목록 + 상세 (동적)
   - `/gallery` - Lightbox + SNS 임베드
   - `/contact` - 폼 + 지도

3. 반응형 구현
   - 모바일 (320px~)
   - 태블릿 (768px~)
   - 데스크톱 (1024px~)

**산출물**: 7개 완성 페이지

---

### Phase 4: QA 및 배포 (3일)
**목표**: 품질 검증 및 프로덕션 배포

**QA 체크리스트**:
- [ ] 모든 내부 링크 동작 확인
- [ ] 리다이렉트 규칙 테스트 (기존 URL → 새 URL)
- [ ] 모바일/태블릿/데스크톱 반응형 확인
- [ ] 섹션 앵커 링크 동작 확인
- [ ] 폼 제출 테스트
- [ ] SEO 메타태그 확인 (7개 페이지)
- [ ] 성능 테스트 (Lighthouse)
- [ ] 접근성 테스트 (WCAG AA)
- [ ] 크로스 브라우저 테스트

**배포 전 최종 확인**:
- [ ] 연도 표기 정책 준수 (`year-policy.md` 기준)
- [ ] 모든 CTA 링크 유효성
- [ ] 404 페이지 없음
- [ ] 이미지 최적화 (WebP, lazy loading)

**산출물**: 프로덕션 배포

---

## 6) 배포 전략: 즉시 통합

### 전략 개요
**새 사이트이므로** 점진적 마이그레이션 없이 **즉시 7개 페이지로 구축 및 배포**.

### 배포 방식
- **기존 36개 파일**: `planning/` 폴더에 아카이브로 보관 (참고용)
- **새로운 7개 파일**: `final-copy/`에서 즉시 구축 및 배포
- **리다이렉트**: 기존 URL 패턴 → 새 7개 페이지 (301 설정)

### 작업 순서
1. **콘텐츠 통합** (1주)
   - 36개 파일 내용을 7개 파일로 병합
   - `final-copy/` 재구성

2. **프론트엔드 구축** (2주)
   - 7개 페이지 개발
   - 리다이렉트 규칙 적용

3. **QA 및 배포** (3일)
   - 전체 테스트
   - 프로덕션 배포

### 장점
- ✅ 빠른 출시 (4주 내)
- ✅ 관리 복잡도 최소화
- ✅ 일관된 사용자 경험
- ✅ 유지보수 부담 즉시 감소

---

## 7) 리스크 및 대응 방안

### 리스크 1: SEO 순위 하락
**원인**: 기존 URL 구조 변경

**대응**:
- ✅ 301 리다이렉트 완벽 구현
- ✅ Google Search Console에 새 사이트맵 제출
- ✅ 주요 키워드 페이지 우선 모니터링
- ✅ 백링크 있는 페이지는 리다이렉트 필수

### 리스크 2: 콘텐츠 누락
**원인**: 통합 과정에서 일부 내용 누락

**대응**:
- ✅ 통합 전 콘텐츠 체크리스트 작성
- ✅ 36개 파일 전체 내용 매핑
- ✅ 2인 이상 크로스 리뷰
- ✅ 기존 파일 아카이브 보관 (삭제 금지)

### 리스크 3: 성능 저하
**원인**: Long-form 페이지로 인한 로딩 지연

**대응**:
- ✅ Lazy Loading 적용 (이미지, 섹션)
- ✅ Code Splitting (탭/아코디언 별도 로딩)
- ✅ 이미지 최적화 (WebP, 반응형 이미지)
- ✅ CDN 활용

---

## 8) 예상 비용 및 일정

### 일정 요약
| Phase | 작업 | 기간 | 담당 |
|-------|------|------|------|
| Phase 1 | 콘텐츠 통합 | 1주 | 기획/카피라이터 |
| Phase 2 | 라우팅 설정 | 3일 | 개발자 |
| Phase 3 | UI/UX 구현 | 2주 | 디자이너/개발자 |
| Phase 4 | QA 및 배포 | 3일 | QA/개발자 |
| **총계** | | **약 4주** | |

### 리소스
- 기획/카피라이터: 1명 (1주 풀타임)
- 디자이너: 1명 (1주 풀타임)
- 프론트엔드 개발자: 1명 (2주 풀타임)
- QA: 1명 (3일)

---

## 9) 성공 지표 (KPI)

### 출시 직후 (1개월)
- [ ] 페이지 로딩 속도: LCP < 2.5s
- [ ] 모바일 Lighthouse 점수: 90점 이상
- [ ] 404 에러율: 0.5% 미만
- [ ] 사용자 이탈률: 현재 대비 10% 감소

### 3개월 후
- [ ] SEO 순위: 주요 키워드 순위 유지 또는 상승
- [ ] 전환율: 참가 신청 전환율 15% 증가
- [ ] 평균 세션 시간: 20% 증가
- [ ] 모바일 트래픽 비율: 60% 이상

---

## 10) 결론 및 권장사항

### 핵심 요약
- **현재**: 36개 페이지로 분산된 정보 구조
- **제안**: 7개 페이지로 통합한 현대적 구조
- **효과**: 81% 페이지 감소, UX/SEO/유지보수 개선

### 권장 다음 단계
1. ✅ 이 제안서 검토 및 승인
2. ✅ Phase 1 시작: 콘텐츠 통합 작업
3. ✅ 디자인 목업 제작 (주요 3개 페이지)
4. ✅ 개발 착수

### 최종 의견
현대적인 이벤트 사이트는 **"적을수록 강력하다"**는 원칙을 따릅니다.
36개 페이지는 관리 부담과 사용자 혼란을 초래하며,
7개 페이지로 통합하면 **더 나은 UX, 더 쉬운 유지보수, 더 높은 전환율**을 달성할 수 있습니다.

---

## 부록

### A. 참고 사례
현대적인 이벤트 사이트 벤치마크:
- AWS re:Invent: 6개 주요 페이지
- Google I/O: 5개 주요 페이지
- Apple WWDC: 7개 주요 페이지

### B. 관련 문서
- `content-map.md`: URL 매핑 및 리다이렉트
- `year-policy.md`: 연도 표기 정책
- `backend-requirements.md`: 백엔드 요구사항
- `README.md`: 워크스페이스 가이드
