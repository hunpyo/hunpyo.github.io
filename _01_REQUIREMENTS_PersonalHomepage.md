# Requirements: v2.0

## 원본 요청
기존 Google Sites 개인 홈페이지(https://sites.google.com/view/hunpyohome)를
트렌디하고 인터랙티브한 연구실 웹사이트로 리뉴얼.
Apple iPhone 페이지 스타일의 스크롤 애니메이션 적용.

---

## 현재 사이트 구조 분석

### 메뉴 구성 (5개)
| 메뉴 | 내용 |
|------|------|
| HOME | 메인 소개 + 연구 이미지 6개 |
| RESEARCH | 4개 연구 프로젝트 상세 |
| PUBLICATIONS | 11편 논문 목록 |
| PEOPLE | 프로필, 학력, 경력 |
| CONTACT | 연락처, 주소, 지도 |

### 기존 콘텐츠 상세

**HOME**
- 헤드라인: "Innovative Soft Systems for Active Deformation"
- 설명: soft actuators와 structures를 활용한 지능형 능동 변형 연구
- 연구 이미지 6개 (Google Drive 호스팅)

**RESEARCH (4개 프로젝트)**
1. Self-bendable Film - Soft Robotics (2018)
2. Multi-channel Bendable Film - Soft Robotics (2021)
3. Soft Robotic Flatworm - Advanced Functional Materials (2023)
4. Multi-channel Morphing Sheet - 준비 중

**PUBLICATIONS (11편)**
- Cover Image 선정: 3편
- 주요 저널: Soft Robotics, PNAS, Advanced Materials, npj Flexible Electronics

**PEOPLE**
- Hunpyo Ju, Ph.D.
- Senior Researcher @ ETRI
- GIST 박사 (2022), 경북대 학사 (2015)

**CONTACT**
- ETRI, 3번 건물 401호
- 218 Gajeong-ro, Yuseong-gu, Daejeon
- hunpyo@etri.re.kr
- +82-42-860-6424

---

## 데이터 이전 가능 여부

### 가져올 수 있는 것
| 항목 | 가능 여부 | 비고 |
|------|----------|------|
| 텍스트 콘텐츠 | ✅ | 모든 텍스트 복사 가능 |
| 논문 목록 | ✅ | 제목, 저널, 연도 |
| 프로필 정보 | ✅ | 학력, 경력 |
| 연락처 | ✅ | 이메일, 전화, 주소 |

### 별도 준비 필요
| 항목 | 상태 | 해결 방법 |
|------|------|----------|
| 연구 이미지 | ⚠️ | Google Drive 이미지는 직접 다운로드 후 제공 필요 |
| 프로필 사진 | ⚠️ | 별도 파일 제공 필요 |
| 논문 썸네일 | ⚠️ | 저널 커버/Figure 이미지 별도 준비 |

---

## 명확화된 요구사항

### 1. 디자인 컨셉
**테마**: Academic Premium + Modern Interactive
- 학술적 신뢰감 + 프리미엄 느낌
- Apple 스타일 스크롤 기반 스토리텔링
- **라이트 모드** 기반 (깔끔하고 학술적인 느낌)

**참고 스타일**
- Apple iPhone 17 Pro 페이지 (스크롤 애니메이션)
- MIT Media Lab (학술 + 모던)
- Stanford HAI (깔끔한 연구 소개)

### 2. 컬러 팔레트 (라이트 모드)
| 용도 | 컬러 | HEX |
|------|------|-----|
| 배경 (메인) | Off White | #f5f5f7 |
| 배경 (섹션) | Pure White | #FFFFFF |
| 포인트 | Electric Blue | #007AFF |
| 포인트 보조 | Soft Cyan | #5AC8FA |
| 텍스트 (기본) | Charcoal | #1d1d1f |
| 텍스트 (보조) | Gray | #6e6e73 |
| 구분선/보더 | Light Gray | #d2d2d7 |

### 3. 페이지별 구현 방향

**① HOME (메인)**
- 풀스크린 히어로: 타이틀 + 키워드 애니메이션
- 연구 하이라이트: 스크롤 시 이미지 전환 (Apple 스타일)
- 숫자 통계: 논문 수, 인용 수, 프로젝트 수 카운트업
- Featured Research: 대표 연구 3개 프리뷰

**② RESEARCH**
- 프로젝트별 풀스크린 섹션
- 스크롤 시 이미지 확대/축소 효과
- 각 연구 클릭 시 상세 모달 또는 섹션 확장

**③ PUBLICATIONS**
- 타임라인 형식 (연도별 그룹핑)
- Cover Image 논문 강조 표시
- 호버 시 논문 정보 확장
- 필터: 연도, 저널, 유형

**④ PEOPLE (About)**
- 프로필 카드 + 스크롤 애니메이션
- 학력/경력 타임라인
- 연구 관심사 태그 클라우드
- **Google Scholar 링크** 추가

**⑤ CONTACT**
- 깔끔한 연락처 카드
- 인터랙티브 지도 (선택)
- 이메일 복사 버튼
- **Google Scholar 링크** 추가

### 4. 인터랙션 & 애니메이션

**스크롤 기반 (GSAP ScrollTrigger)**
- 섹션 진입 시 Fade Up
- 이미지 패럴랙스
- 텍스트 순차 등장
- 스크롤 진행률 표시 (선택)

**마이크로 인터랙션**
- 버튼 호버: Glow 효과
- 카드 호버: 살짝 떠오름
- 네비게이션: 현재 섹션 하이라이트

### 5. 콘텐츠 보호 기능 ⭐
- **드래그 방지**: 텍스트/이미지 선택 불가
- **우클릭 방지**: 컨텍스트 메뉴 차단
- **이미지 저장 방지**: 드래그 앤 드롭 차단
- **키보드 단축키 차단**: Ctrl+C, Ctrl+S 등

### 6. 기술 스택
- HTML5 / CSS3 / JavaScript
- GSAP 3.x + ScrollTrigger
- Google Fonts (학술적 세리프 + 모던 산세리프)
- 반응형 디자인 (PC/Tablet/Mobile)

---

## 파일 구조 ⭐

### HTML 파일 (5개 페이지)
```
WebPage_v2.0/
├── index.html          ← HOME
├── research.html       ← RESEARCH
├── publications.html   ← PUBLICATIONS
├── people.html         ← PEOPLE (About)
├── contact.html        ← CONTACT
├── assets/
│   ├── images/
│   │   ├── hero/
│   │   │   └── hero-bg.jpg (1920x1080 권장)
│   │   ├── research/
│   │   │   ├── research-01-bendable-film.jpg
│   │   │   ├── research-02-multichannel.jpg
│   │   │   ├── research-03-flatworm.jpg
│   │   │   └── research-04-morphing.jpg
│   │   ├── publications/
│   │   │   ├── cover-soft-robotics-2023.jpg
│   │   │   ├── cover-afm-2023.jpg
│   │   │   └── cover-adv-healthcare-2020.jpg
│   │   └── profile/
│   │       └── profile-hunpyo.jpg (정사각형 권장)
│   └── files/
│       └── CV_HunpyoJu.pdf (선택)
```

### 이미지 사양 권장
| 용도 | 파일명 패턴 | 권장 크기 | 형식 |
|------|------------|----------|------|
| 히어로 배경 | hero-bg.jpg | 1920×1080 | JPG/WebP |
| 연구 이미지 | research-NN-name.jpg | 1200×800 | JPG/WebP |
| 논문 커버 | cover-journal-year.jpg | 600×800 | JPG/WebP |
| 프로필 | profile-name.jpg | 500×500 | JPG/PNG |

### 제공 방법
1. 위 폴더 구조대로 `assets` 폴더 생성
2. 이미지 파일을 해당 위치에 배치
3. 파일명 규칙 준수 (영문, 소문자, 하이픈 구분)

---

## 제약사항
- 이미지 파일은 사용자가 별도 제공해야 함
- 단일 HTML 파일 또는 최소한의 파일 구조
- 외부 의존성 최소화 (CDN 사용)

---

## 구현 우선순위

### Phase 1 (MVP)
1. HOME 페이지 (히어로 + 연구 하이라이트)
2. 기본 네비게이션
3. 스크롤 애니메이션 기본 적용
4. 콘텐츠 보호 기능 (드래그/우클릭 방지)

### Phase 2
5. RESEARCH 페이지
6. PUBLICATIONS 페이지

### Phase 3
7. PEOPLE 페이지
8. CONTACT 페이지
9. 반응형 최적화

---

## 기대 결과
- 학술적 신뢰감과 현대적 디자인이 조화된 개인 연구 웹사이트
- Apple 스타일의 몰입감 있는 스크롤 경험
- 연구 성과를 효과적으로 어필할 수 있는 인터랙티브 프레젠테이션
- 콘텐츠 무단 복제 방지

---

## 확인 완료 사항

1. **컬러 테마**: ✅ 라이트 모드
2. **페이지 구조**: ✅ 멀티 페이지 (5개 HTML 파일)
3. **추가 콘텐츠**: ✅ Google Scholar 링크 추가

## 추가 확인 필요

1. **Google Scholar URL**: 본인 프로필 URL 제공 필요
2. **이미지 파일**: 연구 이미지, 프로필 사진 제공 가능 여부?

---

**작성일**: 2025-12-15
