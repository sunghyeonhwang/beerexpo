# beer_EXPO Workspace Guide

- Path: `/Users/griff_hq/Library/Mobile Documents/com~apple~CloudDocs/Reseach/Web/beer_EXPO`
- Updated: 2026-02-20
- 목적: 현재 폴더 구조와 문서 산출물 위치를 한 번에 확인

## 1) 루트 주요 파일
- `README.md`: 현재 문서(워크스페이스 안내)
- `content-map.md`: URL alias/canonical 매핑 및 운영 체크리스트

## 2) 폴더 구조 요약
- `Develop/`
- `content/`
- `final-copy/`
- `planning/`
- `skills/`

## 3) 폴더별 상세

## `Develop/`
- `Develop/backend-requiremnets.md`
  - 서버 스펙 미정 상태를 전제로 한 백엔드 요구사항 문서
  - 페이지별 백엔드 필요도, 데이터 모델, API 계약, 단계별 구현안 포함
- `Develop/front-spec.md`
  - AstroEvent 기반 프론트 구현 명세
  - 라우트/컴포넌트/콘텐츠 매핑/QA/DoD 포함

## `content/`
- 성격: 수집/분류/감사 자료(중간 산출물 + 수동 정리 파일 포함)
- 주요 파일:
  - `content/beerexpo_plan_collect.md` (수동/기존 계획 파일)
  - `content/content-freshness-audit.md` (연도/최신성 점검 리포트)
  - `content/sitemap.md` (사이트맵)
- 하위 폴더:
  - `content/clipping/`: 페이지별 원문 클리핑
  - `content/collected/`: 수집/정제 원문 (`INDEX.md`, `README.md` 포함)
  - `content/functional/`: `Title/H1/Body` 기능 분해본 (`README.md` 포함)

## `planning/`
- 성격: 기획 문서(디자인 제외)
- 주요 파일:
  - `planning/front-page.md` (메인 페이지 기획/카피 초안)
  - 페이지별 계획서 32개 (`how-to-apply.md`, `kibex2026.md` 등)
  - `planning/README.md` (포맷 설명)

## `final-copy/`
- 성격: 배포용 카피 초안(페이지별 `Status: Final`)
- 구성:
  - 페이지별 파일 32개
  - `final-copy/README.md` (패키지 설명)
- 특징:
  - `Category` 메타 포함
  - Hero/핵심요약/참석자별 안내/상세/CTA/SEO/검수메모 구조

## `skills/`
- `skills/web-site-copywriter/SKILL.md`
  - 웹사이트 카피 정리용 커스텀 스킬
  - 요약+상세 2단 구조, 최신성 규칙, 최종 체크리스트 정의

## 4) 현재 작업 기준 추천 사용 순서
1. 기획 확인: `planning/front-page.md` + `planning/*.md`
2. 카피 사용: `final-copy/*.md`
3. 백엔드 정의: `Develop/backend-requiremnets.md`
4. 원문 근거 확인: `content/collected/*.md` 및 `content/clipping/*.md`

## 5) 공통 운영 원칙
- 역할 분리:
  - `planning/`은 전략/구조/요구사항만 관리
  - `final-copy/`는 배포 문구만 관리
- 최신성 정책:
  - 과거 수치/성과는 `전년도 기준` 또는 `아카이브`로 표기
  - 일정/요금/마감/장소는 운영 최신 공지 기준으로 확정
- 변경 절차:
  1. 기획 변경은 `planning/` 반영
  2. 문구 변경은 `final-copy/` 반영
  3. 링크/상태 최종 점검 후 배포

## 6) 참고
- `.DS_Store` 파일은 macOS 생성 파일로, 문서 작업과 무관
- 파일명 `backend-requiremnets.md`는 요청 명칭 그대로 생성됨
