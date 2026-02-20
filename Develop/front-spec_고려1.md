# Front Spec (AstroEvent Base)

- Project: KIBEX 2026
- Updated: 2026-02-20
- Base Theme: AstroEvent Landing Page (`https://astro.build/themes/details/astroevent-landing-page/`)
- Goal: 디자인 템플릿을 KIBEX 정보구조/카피로 변형하여 즉시 개발 시작

## 1) 개발 목표
- AstroEvent 템플릿을 KIBEX용으로 리브랜딩
- 랜딩 + 내부 라우팅 구조 구현
- `final-copy/*.md` 문구를 페이지별로 반영
- 연도 정책(2026 기준, 과거 수치 `전년도 기준`) 준수

## 2) 필수 라우트
- `/` (Front Page)
- `/howtoapply`
- `/visitorguide`
- `/kibcon`
- `/notice`
- `/contactus`

## 3) 라우트별 콘텐츠 소스
- `/` -> `final-copy/front-page.md`
- `/howtoapply` -> `final-copy/how-to-apply.md`
- `/visitorguide` -> `final-copy/visitor-guide.md`
- `/kibcon` -> `final-copy/kibcon.md`
- `/notice` -> `final-copy/notice.md`
- `/contactus` -> `final-copy/contact-us.md`

## 4) 템플릿 섹션 매핑 (AstroEvent -> KIBEX)
1. Hero -> KIBEX Hero (일정/장소/핵심 CTA)
2. Features/Highlights -> Program Highlights (KIBCON/KIBA/TOUR/SHOWCASE)
3. Speakers/Team -> Audience Entry (참가사/바이어/참관객)
4. Schedule -> Program Summary + 이동 링크
5. Blog/News -> Latest Notice
6. Gallery/Sponsors -> Gallery & Partners
7. Final CTA/Footer -> 참가신청/방문안내/문의

## 5) 컴포넌트 목록 (MVP)
- `Layout/MainLayout.astro`
- `components/Hero.astro`
- `components/QuickFacts.astro`
- `components/AudienceCards.astro`
- `components/ProgramHighlights.astro`
- `components/NoticePreview.astro`
- `components/GalleryPreview.astro`
- `components/FinalCTA.astro`
- `components/PageHeader.astro`
- `components/PageSections.astro`

## 6) 콘텐츠 로딩 방식 (권장)
- 방식: 로컬 MD 파일 직접 import/parsing (CMS 미사용)
- 규칙:
  - `final-copy/`를 단일 진실 소스로 사용
  - 페이지는 메타 영역(`Title`, `H1`, `Category`)과 본문 섹션을 파싱
  - 공통 라벨(`Status`, `Updated`)은 빌드 시 표시 가능

## 7) 데이터 계약 (프론트 내부)
```ts
type PageCopy = {
  slug: string;
  category: string;
  title: string;
  h1: string;
  hero: string;
  keyPoints: string[];
  audience: {
    exhibitors: string[];
    buyers: string[];
    visitors: string[];
  };
  details: Array<{ heading: string; bullets: string[] }>;
  cta: Array<{ label: string; href: string }>;
  seo: { title: string; description: string; keywords: string[] };
};
```

## 8) 페이지 구현 우선순위
1. `/` (front-page)
2. `/howtoapply`
3. `/visitorguide`
4. `/kibcon`
5. `/notice`
6. `/contactus`

## 9) 개발 체크리스트
- [ ] 공통 레이아웃/헤더/푸터 구성
- [ ] 상단 내비게이션에 6개 라우트 연결
- [ ] `final-copy/front-page.md` 기반 홈 섹션 렌더링
- [ ] 내부 페이지 템플릿 1개로 5개 라우트 재사용
- [ ] CTA 링크 유효성 점검
- [ ] 모바일 반응형(320px+) 확인
- [ ] SEO title/description 라우트별 적용
- [ ] 2025/2024 직접 노출 문구 여부 최종 점검

## 10) QA 기준 (배포 전)
- 기능:
  - 모든 CTA 클릭 시 의도 라우트로 이동
  - 404 없는 내부 링크
- 콘텐츠:
  - `final-copy`와 렌더링 문구 일치
  - 과거 데이터는 `전년도 기준` 라벨 유지
- 접근성:
  - H1은 페이지당 1개
  - 버튼/링크 라벨 명확
  - 섹션 제목 계층 일관
- 성능:
  - 초기 랜딩 LCP 목표 2.5s 이내(이미지 최적화 전제)

## 11) 개발 시작 명령(예시)
```bash
# 1) 테마/프로젝트 준비
# Astro 프로젝트 생성 후 테마 코드 적용

# 2) 페이지/컴포넌트 스캐폴딩
mkdir -p src/components src/layouts src/pages

# 3) 콘텐츠 연결
# final-copy/*.md 파싱 유틸 작성 후 각 라우트에 바인딩
```

## 12) Done 정의 (프론트)
- 6개 필수 라우트 구현 완료
- 홈/내부 페이지 카피 반영 완료
- 주요 CTA/SEO/모바일 QA 완료
- 운영팀이 문구 수정 시 `final-copy`만 수정해 반영 가능한 구조 확보
