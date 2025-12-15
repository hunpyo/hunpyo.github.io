# Plan: v2.0 Personal Homepage

## 개요
5개 페이지로 구성된 개인 연구 웹사이트 구현
- 라이트 모드, Apple 스타일 스크롤 애니메이션
- GSAP ScrollTrigger 활용
- 콘텐츠 보호 (드래그/우클릭 방지)

---

## 파일 구조

```
WebPage_v2.0/
├── index.html          ← HOME
├── research.html       ← RESEARCH
├── publications.html   ← PUBLICATIONS
├── people.html         ← PEOPLE
├── contact.html        ← CONTACT
├── css/
│   └── style.css       ← 공통 스타일
├── js/
│   └── main.js         ← 공통 JS (애니메이션, 보호)
└── assets/images/      ← 이미지 (준비 완료)
```

---

## 구현 순서

### Phase 1: 공통 요소 + HOME
1. `css/style.css` - 공통 스타일 (컬러, 폰트, 레이아웃)
2. `js/main.js` - 공통 JS (네비게이션, 콘텐츠 보호, GSAP 초기화)
3. `index.html` - HOME 페이지
   - 네비게이션 바 (공통)
   - Hero 섹션 (타이틀 + 소개)
   - Research Highlights (대표 연구 3개)
   - Stats 섹션 (논문 수, 프로젝트 수)
   - Footer (공통)

### Phase 2: RESEARCH
4. `research.html`
   - 4개 연구 프로젝트 상세
   - 각 프로젝트: 이미지/비디오 + 설명 + 출판 정보
   - research_03: Virtual/Real 가로 배치

### Phase 3: PUBLICATIONS
5. `publications.html`
   - 11개 논문 목록 (연도별 역순)
   - Cover Image 강조 표시
   - TOC 이미지 표시 (없으면 placeholder)

### Phase 4: PEOPLE + CONTACT
6. `people.html`
   - 프로필 카드 (사진 + 소속)
   - 학력/경력 타임라인
   - Google Scholar 링크
7. `contact.html`
   - 연락처 정보 카드
   - 이메일 복사 기능
   - Google Scholar 링크

---

## 사용할 이미지 매핑

### Research
| 연구 | PNG (대표) | MP4 (데모) |
|------|-----------|------------|
| 01 Self-bendable Film | research_01-1.png | research_01-2~5.mp4 |
| 02 Multi-channel Film | research_02-1.png | research_02-2~7.mp4 |
| 03 Soft Robotic Flatworm | research_03-1.png | research_03-2_virtual.mp4, research_03-3_real.mp4 |
| 04 Morphing Sheet | research_04.png | - |

### Publications
| 논문 # | Cover | ToC |
|--------|-------|-----|
| 1 | #1_Cover.jpg | #1_ToC.png |
| 2~8 | - | #2~8_ToC.png/jpg |
| 9 | #9_Cover.jpg | #9_ToC.png |

### Profile
- profile/Profile.jpg
- profile/Affiliation.png

### Hero
- hero/Image_1.png (배경 또는 장식)

---

## 기술 상세

### 콘텐츠 보호
```javascript
// 드래그 방지
document.addEventListener('selectstart', e => e.preventDefault());
// 우클릭 방지
document.addEventListener('contextmenu', e => e.preventDefault());
// 키보드 단축키 차단 (Ctrl+C, Ctrl+S 등)
document.addEventListener('keydown', e => {
  if (e.ctrlKey && ['c','s','u'].includes(e.key.toLowerCase())) {
    e.preventDefault();
  }
});
```

### 애니메이션 (GSAP)
- Fade Up: 섹션 진입 시
- 비디오: 스크롤 시 자동 재생/정지
- 카운트업: Stats 숫자 애니메이션

---

## 예상 코드량
- style.css: ~500줄
- main.js: ~200줄
- index.html: ~400줄
- research.html: ~500줄
- publications.html: ~400줄
- people.html: ~300줄
- contact.html: ~200줄

---

## 기존 기능 영향
- 없음 (신규 프로젝트)

---

**작성일**: 2025-12-15
