# beerexpo.kr 콘텐츠 맵 (7개 통합 페이지 구조)

- 기준일: 2026-02-20
- 업데이트: 36개 → 7개 페이지 통합 완료
- 목적: 통합된 사이트 구조 및 301 리다이렉트 매핑

---

## 1) 신규 사이트 구조 (7개 페이지)

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

## 2) 페이지별 콘텐츠 파일 매핑

### 페이지 1: 홈 (`/`)
- **파일**: `final-copy/home.md`
- **원본**: `front-page.md`
- **콘텐츠**:
  - Hero (일정/장소/핵심 CTA)
  - Why KIBEX 요약
  - 주요 수치
  - 참가 대상 카드
  - 프로그램 미리보기
  - 파트너 로고
  - Latest News
  - Final CTA

---

### 페이지 2: 소개 (`/about`)
- **파일**: `final-copy/about.md`
- **통합된 원본**: 5개
  1. whykibex.md
  2. overview.md
  3. show-results-2025.md
  4. organizers.md
  5. partners.md

- **섹션 구조**:
  ```
  ## Why KIBEX
  ## 전시 개요 (Overview)
  ## 2025년 성과 (Show Results)
  ## 주최/주관 (Organizers)
  ## 파트너 (Partners)
  ```

---

### 페이지 3: 참가 신청 (`/exhibit`)
- **파일**: `final-copy/exhibit.md`
- **통합된 원본**: 9개
  1. how-to-apply.md
  2. exhibitor-application.md
  3. pairing-special.md
  4. sponsorship-program.md
  5. application-download.md
  6. promotional-kit.md
  7. exhibitor-list.md
  8. floor-plan.md

- **섹션 구조** (Sticky Tab Navigation 권장):
  ```
  ## 참가 안내 (How to Apply)
  ## 참가 신청 (Exhibitor Application)
  ## 페어링 특별관 (Pairing Special)
  ## 스폰서십 프로그램 (Sponsorship Program)
  ## 신청서 다운로드 (Application Download)
  ## 홍보 키트 (Promotional Kit)
  ## 참가 업체 목록 (Exhibitor List)
  ## 부스 배치도 (Floor Plan)
  ```

- **앵커 링크**:
  - `/exhibit#how-to-apply`
  - `/exhibit#application`
  - `/exhibit#pairing-special`
  - `/exhibit#sponsorship`
  - `/exhibit#download`
  - `/exhibit#promotional-kit`
  - `/exhibit#exhibitor-list`
  - `/exhibit#floor-plan`

---

### 페이지 4: 방문 안내 (`/visit`)
- **파일**: `final-copy/visit.md`
- **통합된 원본**: 4개
  1. visitor-guide.md
  2. buyer-registration.md
  3. business-matching.md
  4. amenities-transportation.md

- **섹션 구조** (Tab Navigation 권장):
  ```
  ## 관람 안내 (Visitor Guide)
  ## 바이어 등록 (Buyer Registration)
  ## 비즈니스 매칭 (Business Matching)
  ## 교통 및 편의시설 (Amenities & Transportation)
  ```

- **앵커 링크**:
  - `/visit#guide`
  - `/visit#buyer`
  - `/visit#matching`
  - `/visit#access`

---

### 페이지 5: 프로그램 (`/programs`)
- **파일**: `final-copy/programs.md`
- **통합된 원본**: 6개
  1. kibcon.md
  2. kiba.md
  3. open-stage.md
  4. the-brew-in-tour.md
  5. new-product-showcase.md
  6. drink-seoul-2025.md

- **섹션 구조** (Card Grid + Modal/Accordion 권장):
  ```
  ## KIBCON 세미나
  ## KIBA 어워드
  ## OPEN STAGE
  ## THE BREW-IN TOUR
  ## 신제품 쇼케이스
  ## DRINK SEOUL 2025
  ```

- **앵커 링크**:
  - `/programs#kibcon`
  - `/programs#kiba`
  - `/programs#open-stage`
  - `/programs#tour`
  - `/programs#showcase`
  - `/programs#drink-seoul`

---

### 페이지 6: 소식 (`/news`)
- **파일**: `final-copy/news.md`
- **통합된 원본**: 2개
  1. notice.md
  2. press-release.md

- **섹션 구조** (필터/카테고리 권장):
  ```
  ## 공지사항 (Notice)
  ## 보도자료 (Press Release)
  ```

- **동적 라우팅**:
  - `/news` - 목록 페이지
  - `/news/{id}` - 상세 페이지
  - `/news?category=notice` - 공지사항 필터
  - `/news?category=press` - 보도자료 필터

---

### 페이지 7: 갤러리 (`/gallery`)
- **파일**: `final-copy/gallery.md`
- **통합된 원본**: 3개
  1. gallery-landing.md
  2. photo-gallery.md
  3. sns.md

- **섹션 구조** (Tab 권장):
  ```
  ## 포토 갤러리 (Photo Gallery)
  ## 현장 사진 (Event Photos)
  ## SNS 피드
  ```

- **앵커 링크**:
  - `/gallery#photos`
  - `/gallery#sns`

---

### 페이지 8: 문의 (`/contact`)
- **파일**: `final-copy/contact.md`
- **원본**: `contact-us.md`
- **콘텐츠**:
  - 문의 폼
  - 오시는 길
  - FAQ
  - 연락처 정보

---

## 3) 301 리다이렉트 규칙 (기존 URL → 새 URL)

### 3-1. Alias 리다이렉트

```
# 기존 Alias URL → 새 Canonical URL
/KIBEX2026              → /about
/EXHIBITORS             → /exhibit
/VISITORS               → /visit
/PROGRAM                → /programs
/NEWS                   → /news
```

---

### 3-2. 소개 페이지 리다이렉트 → `/about`

```
/whykibex               → /about#why-kibex
/overview               → /about#overview
/show-results-2025      → /about#results
/organizers             → /about#organizers
/partners               → /about#partners
```

---

### 3-3. 참가 신청 페이지 리다이렉트 → `/exhibit`

```
/exhibitors-landing     → /exhibit
/how-to-apply           → /exhibit#how-to-apply
/exhibitor-application  → /exhibit#application
/pairing-special        → /exhibit#pairing-special
/sponsorship-program    → /exhibit#sponsorship
/application-download   → /exhibit#download
/promotional-kit        → /exhibit#promotional-kit
/exhibitor-list         → /exhibit#exhibitor-list
/floor-plan             → /exhibit#floor-plan
```

---

### 3-4. 방문 안내 페이지 리다이렉트 → `/visit`

```
/visitors-landing       → /visit
/visitor-guide          → /visit#guide
/buyer-registration     → /visit#buyer
/business-matching      → /visit#matching
/amenities-transportation → /visit#access
```

---

### 3-5. 프로그램 페이지 리다이렉트 → `/programs`

```
/program-landing        → /programs
/kibcon                 → /programs#kibcon
/kiba                   → /programs#kiba
/open-stage             → /programs#open-stage
/the-brew-in-tour       → /programs#tour
/new-product-showcase   → /programs#showcase
/drink-seoul-2025       → /programs#drink-seoul
```

---

### 3-6. 소식 페이지 리다이렉트 → `/news`

```
/news-landing           → /news
/notice                 → /news?category=notice
/press-release          → /news?category=press
```

---

### 3-7. 갤러리 페이지 리다이렉트 → `/gallery`

```
/gallery-landing        → /gallery
/photo-gallery          → /gallery#photos
/sns                    → /gallery#sns
```

---

### 3-8. 기타 페이지

```
/contact-us             → /contact
```

---

## 4) 네비게이션 메뉴 구조

### 메인 메뉴 (Desktop)
```
┌─────────────────────────────────────────────────────────┐
│ KIBEX 2026 | About | Exhibit | Visit | Programs | News  │
│                                          | Gallery | Contact │
└─────────────────────────────────────────────────────────┘
```

### 모바일 메뉴 (햄버거)
```
☰ 메뉴
├─ 홈 (/)
├─ 소개 (/about)
├─ 참가 신청 (/exhibit)
├─ 방문 안내 (/visit)
├─ 프로그램 (/programs)
├─ 소식 (/news)
├─ 갤러리 (/gallery)
└─ 문의 (/contact)
```

---

## 5) 구현 참고사항

### 5-1. Astro 라우팅 예시

```javascript
// src/pages/index.astro → /
// src/pages/about.astro → /about
// src/pages/exhibit.astro → /exhibit
// src/pages/visit.astro → /visit
// src/pages/programs.astro → /programs
// src/pages/news/index.astro → /news
// src/pages/news/[id].astro → /news/{id}
// src/pages/gallery.astro → /gallery
// src/pages/contact.astro → /contact
```

### 5-2. 리다이렉트 설정 (astro.config.mjs)

```javascript
export default defineConfig({
  redirects: {
    // Alias
    '/KIBEX2026': '/about',
    '/EXHIBITORS': '/exhibit',
    '/VISITORS': '/visit',
    '/PROGRAM': '/programs',
    '/NEWS': '/news',

    // About
    '/whykibex': '/about#why-kibex',
    '/overview': '/about#overview',
    '/show-results-2025': '/about#results',
    '/organizers': '/about#organizers',
    '/partners': '/about#partners',

    // Exhibit
    '/exhibitors-landing': '/exhibit',
    '/how-to-apply': '/exhibit#how-to-apply',
    '/exhibitor-application': '/exhibit#application',
    '/pairing-special': '/exhibit#pairing-special',
    '/sponsorship-program': '/exhibit#sponsorship',
    '/application-download': '/exhibit#download',
    '/promotional-kit': '/exhibit#promotional-kit',
    '/exhibitor-list': '/exhibit#exhibitor-list',
    '/floor-plan': '/exhibit#floor-plan',

    // Visit
    '/visitors-landing': '/visit',
    '/visitor-guide': '/visit#guide',
    '/buyer-registration': '/visit#buyer',
    '/business-matching': '/visit#matching',
    '/amenities-transportation': '/visit#access',

    // Programs
    '/program-landing': '/programs',
    '/kibcon': '/programs#kibcon',
    '/kiba': '/programs#kiba',
    '/open-stage': '/programs#open-stage',
    '/the-brew-in-tour': '/programs#tour',
    '/new-product-showcase': '/programs#showcase',
    '/drink-seoul-2025': '/programs#drink-seoul',

    // News
    '/news-landing': '/news',
    '/notice': '/news?category=notice',
    '/press-release': '/news?category=press',

    // Gallery
    '/gallery-landing': '/gallery',
    '/photo-gallery': '/gallery#photos',
    '/sns': '/gallery#sns',

    // Contact
    '/contact-us': '/contact',
  }
});
```

---

## 6) SEO 최적화

### 6-1. Canonical URL 설정
각 페이지의 `<head>`에 canonical URL 명시:
```html
<link rel="canonical" href="https://beerexpo.kr/about" />
```

### 6-2. 메타 태그
7개 페이지별로 고유한 title, description, keywords 설정

### 6-3. Sitemap.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url><loc>https://beerexpo.kr/</loc><priority>1.0</priority></url>
  <url><loc>https://beerexpo.kr/about</loc><priority>0.9</priority></url>
  <url><loc>https://beerexpo.kr/exhibit</loc><priority>0.9</priority></url>
  <url><loc>https://beerexpo.kr/visit</loc><priority>0.9</priority></url>
  <url><loc>https://beerexpo.kr/programs</loc><priority>0.8</priority></url>
  <url><loc>https://beerexpo.kr/news</loc><priority>0.7</priority></url>
  <url><loc>https://beerexpo.kr/gallery</loc><priority>0.6</priority></url>
  <url><loc>https://beerexpo.kr/contact</loc><priority>0.8</priority></url>
</urlset>
```

---

## 7) QA 체크리스트

### 배포 전 필수 확인

- [ ] **라우팅**
  - [ ] 7개 메인 페이지 모두 접근 가능
  - [ ] 앵커 링크(#) 정상 동작
  - [ ] 301 리다이렉트 정상 동작 (36개 기존 URL)

- [ ] **콘텐츠**
  - [ ] 각 페이지의 섹션 구분 명확
  - [ ] 통합 전 콘텐츠 누락 없음
  - [ ] 연도 정책 준수 (2026/2025 표기)

- [ ] **네비게이션**
  - [ ] 메인 메뉴가 7개 페이지로 연결
  - [ ] 모바일 햄버거 메뉴 동작
  - [ ] 현재 페이지 하이라이트

- [ ] **SEO**
  - [ ] 각 페이지 canonical URL 설정
  - [ ] title/description 고유화
  - [ ] sitemap.xml 생성 및 제출
  - [ ] robots.txt 설정

- [ ] **성능**
  - [ ] LCP < 2.5s
  - [ ] Lighthouse 점수 90점 이상
  - [ ] 이미지 lazy loading 적용

- [ ] **접근성**
  - [ ] H1 페이지당 1개
  - [ ] 앵커 링크 포커스 가능
  - [ ] 키보드 네비게이션 지원

---

## 8) 운영 체크리스트

### 정기 점검 (월 1회)
- [ ] 404 에러 발생 여부 (Google Search Console)
- [ ] 리다이렉트 정상 동작 확인
- [ ] 검색 유입 키워드 분석
- [ ] 페이지 로딩 속도 모니터링

### 콘텐츠 업데이트 시
- [ ] `final-copy/` 폴더의 7개 파일만 수정
- [ ] 연도 정책 준수 (`Develop/year-policy.md` 참고)
- [ ] 수정 후 preview 환경 확인
- [ ] 프로덕션 배포 전 QA

### 연도 전환 시 (2026 → 2027)
- [ ] `Develop/year-policy.md` 참고하여 일괄 갱신
- [ ] 7개 파일만 수정하면 됨 (vs 기존 36개)
- [ ] 푸터 저작권 연도 업데이트
- [ ] SEO 메타 태그 연도 확인

---

## 9) 참고 문서

- `Develop/page-consolidation-proposal.md` - 통합 제안서 (상세)
- `Develop/year-policy.md` - 연도 표기 정책
- `Develop/backend-requirements.md` - 백엔드 요구사항
- `final-copy/README.md` - 콘텐츠 파일 포맷
- `README.md` - 워크스페이스 가이드

---

## 10) 요약

| 항목 | 기존 | 신규 | 개선 |
|------|------|------|------|
| **페이지 수** | 36개 | 7개 | **-29개 (81%↓)** |
| **관리 파일** | 36개 | 7개 | **-29개** |
| **메뉴 깊이** | 2-3단계 | 1-2단계 | 단순화 |
| **콘텐츠 파일** | `final-copy/*.md` (36개) | `final-copy/*.md` (7개) | 통합 완료 |
| **리다이렉트** | 없음 | 301 (36개 → 7개) | SEO 손실 방지 |

**통합 완료일**: 2026-02-20
**구조**: 7개 통합 페이지 + 301 리다이렉트
**상태**: 프론트엔드 구현 준비 완료 ✅
