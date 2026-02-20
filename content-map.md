# beerexpo.kr 콘텐츠 맵 (신규 사이트 이전용)

- 기준일: 2026-02-20
- 목적: 기존 URL/메뉴를 신규 사이트 콘텐츠 파일과 1:1 또는 alias로 매핑

## 1) 사용 규칙
- `canonical`: 신규 사이트에서 실제로 유지/노출할 대표 페이지
- `alias`: 기존 상위 메뉴 URL이 리다이렉트되는 별칭 URL
- 원칙:
  - alias 페이지는 별도 본문을 만들지 않고 canonical 페이지로 통합 관리
  - 메뉴에는 canonical만 노출
  - SEO/라우팅에서는 alias를 301로 canonical에 연결

## 2) Alias 매핑 (리다이렉트 확인)
1. `/KIBEX2026` -> `/WHYKIBEX`
  - canonical 파일: `content/whykibex.md`
  - alias 파일: `content/kibex2026.md`

2. `/EXHIBITORS` -> `/HOWTOAPPLY`
  - canonical 파일: `content/how-to-apply.md`
  - alias 파일: `content/exhibitors-landing.md`

3. `/VISITORS` -> `/VISITORGUIDE`
  - canonical 파일: `content/visitor-guide.md`
  - alias 파일: `content/visitors-landing.md`

4. `/PROGRAM` -> `/KIBCON`
  - canonical 파일: `content/kibcon.md`
  - alias 파일: `content/program-landing.md`

5. `/NEWS` -> `/NOTICE`
  - canonical 파일: `content/notice.md`
  - alias 파일: `content/news-landing.md`

## 3) 직접 운영 페이지 (200 응답)
- `/AMENITIESTRANSPORTATION`
  - 파일: `content/amenities-transportation.md`
  - 상태: 직접 운영

- `/GALLERY`
  - 파일: `content/gallery-landing.md`
  - 상태: 직접 운영

## 4) 신규 사이트 권장 메뉴 (canonical 기준)
1. Expo 소개
  - `content/whykibex.md`
  - `content/overview.md`
  - `content/show-results-2025.md`

2. 참가사
  - `content/how-to-apply.md`
  - `content/sponsorship-program.md`
  - `content/application-download.md`
  - `content/promotional-kit.md`

3. 방문객
  - `content/visitor-guide.md`
  - `content/buyer-registration.md`
  - `content/business-matching.md`
  - `content/amenities-transportation.md`

4. 프로그램
  - `content/kibcon.md`
  - `content/kiba.md`
  - `content/open-stage.md`
  - `content/the-brew-in-tour.md`
  - `content/new-product-showcase.md`
  - `content/drink-seoul-2025.md`

5. 소식
  - `content/notice.md`
  - `content/press-release.md`

6. 갤러리
  - `content/gallery-landing.md`
  - `content/photo-gallery.md`
  - `content/sns.md`

## 5) 운영 체크리스트
- 라우팅:
  - alias URL은 301으로 canonical URL에 연결
- 콘텐츠:
  - canonical 파일만 수정/리뷰 대상에 포함
  - alias 파일은 리다이렉트 정보만 유지
- QA:
  - 메뉴 링크가 alias가 아닌 canonical을 가리키는지 점검
  - 검색엔진 색인 대상이 canonical로 통일되는지 점검
  - 공통 푸터 연도 표기(`2024`)를 `2026` 또는 범위 표기로 일괄 갱신
