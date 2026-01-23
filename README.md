# cline_match-report

컬리/R 차량 매칭 현황 리포트를 **GitHub Pages**로 배포하는 도구입니다.

---

## 🌐 배포 주소

[https://oziing.github.io/match-report/](https://oziing.github.io/match-report/)

---

## 🚀 빠른 시작

```bash
# 오늘 데이터 추가 + HTML 생성 + 미리보기
./main.sh today

# 확인 후 배포까지 한번에
./main.sh full
```

---

## 📖 명령어

| 명령어 | 설명 |
|-------|------|
| `./main.sh today` | 오늘(어제 근태) 데이터 추가 → HTML 생성 → 브라우저 미리보기 |
| `./main.sh all` | 전체 기간 리프레시 → HTML 생성 → 미리보기 |
| `./main.sh deploy` | GitHub Pages 배포 (git push) |
| `./main.sh full` | **전체 자동화**: today → 미리보기 → 확인 → deploy |
| `./main.sh 2026-01-22` | 특정 날짜 데이터 추가 |

---

## 📁 파일 구조

```
cline_match-report/
├── main.sh            # 통합 CLI
├── generate_html.py   # HTML 생성기
├── index.html         # 배포되는 HTML (자동 생성)
├── data.txt           # 원본 데이터 (자동 생성)
└── README.md
```

---

## 🔄 일반적인 워크플로우

### 매일 업데이트

```bash
cd cline_match-report
./main.sh full
```

1. DB에서 어제 근태 데이터 조회
2. HTML 생성 및 브라우저에서 미리보기
3. "배포하시겠습니까?" 확인 후 push

### 전체 리프레시 (데이터 초기화)

```bash
./main.sh all      # 전체 재조회
./main.sh deploy   # 확인 후 배포
```

---

## ⚠️ 주의사항

* **push 시 즉시 공개됩니다** - 배포 전 미리보기 필수
* 데이터 소스: Production DB (Fleet ID: 29)
* 근태 기준: 출근자 (OFF, ANNUAL_LEAVE 제외)

---

## 🛠️ 기술 정보

* GitHub Pages: `main` 브랜치 root 배포
* 데이터: PostgreSQL 직접 쿼리
* HTML: 정적 파일 (JavaScript로 렌더링)
