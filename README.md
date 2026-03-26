# 폐렴 항균제 선택 가이드 — PWA

PCR 내성 유전자 결과 기반 항균제 선택 임상 가이드 (Progressive Web App)

---

## 파일 구성

```
pneumonia-pwa/
├── index.html       ← 앱 본체 (전체 로직 포함)
├── manifest.json    ← PWA 설정
├── sw.js            ← Service Worker (오프라인 지원)
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

---

## 안드로이드 설치 방법

### 방법 A — GitHub Pages (무료, 권장)

1. GitHub 계정 생성 (https://github.com)
2. 새 Repository 생성 (이름 예: `pneumonia-abx`)
3. 위 파일 4개를 업로드 (icons 폴더 포함)
4. Settings → Pages → Source: main branch → Save
5. 배포 완료 후 URL: `https://[계정명].github.io/pneumonia-abx/`

**안드로이드 설치:**
- Chrome에서 위 URL 접속
- 주소창 오른쪽 메뉴 → "홈 화면에 추가"
- 또는 앱 상단 설치 배너의 [설치] 버튼 클릭

### 방법 B — 로컬 테스트 (PC에서 확인)

```bash
# Python으로 로컬 서버 실행
cd pneumonia-pwa
python3 -m http.server 8080
# 브라우저에서 http://localhost:8080 접속
```

---

## 기능

- 단일균 / 다균 동시 검출 모드
- PCR 내성 유전자 기반 항균제 추천
- 다균 교집합 분석 (전 균주 커버 약제 자동 추출)
- PCR 예측력 등급 표시 (높음/중간/낮음)
- Cefepime MIC 기반 AmpC 치료 분기
- AmpC + CTX-M 동반 경고
- Acb complex 별도 항목
- 오프라인 작동 (Service Worker 캐싱)

---

## 업데이트 방법

index.html 파일만 수정하여 GitHub에 다시 업로드하면 자동 반영됩니다.
사용자는 앱 재접속 시 자동으로 최신 버전을 받게 됩니다.

---

## 주의사항

이 앱은 임상 의사결정 보조 도구입니다.
최종 항균제 선택은 반드시 표현형 배양 감수성(MIC) 결과와 임상 판단을 기반으로 하십시오.
