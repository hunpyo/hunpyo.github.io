# 2025-12-17: UI 개선 (Hero 배경, Cover 이미지, 폰트 크기)

## 요구사항
1. Hero 섹션에 배경 이미지 적용 (투명하게)
2. Publications 페이지 Journal Cover Images 세로 높이 통일
3. 페이지 제목 폰트 크기 조정 (줄바꿈 방지)

## 구현 내용

### 1. Hero 섹션 배경 이미지
- `assets/images/hero/Background.jpg` 이미지를 Hero 섹션 배경에 적용
- `::before` pseudo-element로 구현 (콘텐츠에 영향 없음)
- `opacity: 0.7` (70% 투명도)
- 텍스트 가독성 향상을 위한 글로우 효과 추가:
  - `.hero-title`: `text-shadow: 0 0 12px rgba(255,255,255,0.8), 0 0 25px rgba(255,255,255,0.5)`
  - `.hero-subtitle`, `.hero-description`: `text-shadow: 0 0 15px rgba(255,255,255,0.8)`
  - 색상 변경: `color-text-secondary` → `color-text` (더 진한 검정)

### 2. Cover Images 높이 통일
- `.cover-item img` 스타일 변경:
  - 기존: `max-width: 280px; max-height: 380px; width: auto; height: auto;`
  - 변경: `height: 380px; width: auto;`
- 세로 높이 고정, 가로는 비율 유지하여 자동 조정
- `.cover-gallery`에 `align-items: flex-start` 추가 (상단 정렬)

### 3. 폰트 크기 조정
- Publications 페이지 h1에 `page-title` 클래스 추가
- `.page-title` 스타일: `font-size: clamp(2.25rem, 4.5vw, 3.25rem)`
- 일반 h1보다 작게 설정하여 줄바꿈 방지
- h2 크기 조정: `clamp(2rem, 4vw, 2.5rem)` → `clamp(1.75rem, 3.5vw, 2.25rem)`

### 4. About 페이지 프로필 이미지
- 프로필 이미지 원본 비율 유지 (1:1 강제 해제)
- `.profile-image` 높이를 텍스트 영역에 맞춤 (`height: 210px`)
- `.profile-card` grid-template-columns 변경: `250px 1fr` → `auto 1fr`

## 수정 파일
- `css/style.css` (+30줄)
  - Hero 섹션 배경 이미지 스타일
  - 텍스트 글로우 효과
  - Cover Gallery 높이 통일
  - page-title 클래스 추가
  - h2 폰트 크기 조정
  - 프로필 이미지 비율 및 높이 조정
- `publications.html` (+1줄)
  - h1에 `page-title` 클래스 추가

## 테스트 결과
- ✅ Hero 배경 이미지 정상 표시
- ✅ 텍스트 가독성 양호 (글로우 효과)
- ✅ Cover Images 세로 높이 통일
- ✅ Publications 제목 줄바꿈 없음
- ✅ 프로필 이미지 원본 비율 유지 및 텍스트 영역 높이 정렬

## 다음 작업 시 참고사항
- Hero 배경 투명도는 `opacity: 0.7`로 설정됨 (조정 가능)
- 텍스트 글로우 강도: title(12px/25px), subtitle/description(15px)
