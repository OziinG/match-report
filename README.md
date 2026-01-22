# match-report

정적 HTML 리포트를 **GitHub Pages**로 배포하는 저장소입니다.
서버 없이 HTML만 서빙하며, 사용자는 **열람만 가능**합니다.

---

## 🌐 배포 주소

[https://oziing.github.io/match-report/](https://oziing.github.io/match-report/)

---

## 📁 저장소 구조

```text
/
├── index.html   # GitHub Pages 진입 파일 (배포 대상)
├── README.md
└── .gitignore
```

* GitHub Pages는 `index.html`만 자동 인식합니다.
* DB, 스크립트 등 민감한 파일은 `.gitignore`로 관리합니다.

---

## 🔄 운영 방식

### 관리자

1. 로컬에서 리포트 HTML 생성
2. 결과물을 `index.html`로 갱신
3. `git commit && git push`

→ push 후 수 분 내 GitHub Pages에 자동 반영됩니다.

### 사용자

* 위 배포 주소로 접속
* **보기만 가능 (읽기 전용)**

---

## ⚠️ 중요 안내 (가시성)

* **Cline이 이 저장소를 직접 갱신(push)하면, 변경 내용은 즉시 모든 사용자에게 공개됩니다.**
* 배포 대상은 `main` 브랜치의 `/ (root)`에 있는 `index.html`입니다.

---

## 🛠️ 기술 메모

* GitHub Pages: `Deploy from a branch`
* Branch: `main`
* Folder: `/ (root)`
* 별도의 Actions / Jekyll 설정 없음
