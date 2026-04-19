# 🤖 Claude Cowork 세션 분석 대시보드

> **229개 Claude Cowork 세션의 카테고리·자동화 태스크·반복 빈도를 분석하는 self-hosted 대시보드**
> Analytics dashboard for personal Claude Cowork productivity sessions

[![Live Dashboard](https://img.shields.io/badge/Live-Dashboard-00A67E?style=flat-square)](https://dongsoojung.github.io/cowork-dashboard/)
[![Claude](https://img.shields.io/badge/Powered%20by-Claude-D97757?style=flat-square)](https://claude.ai)
[![Chart.js](https://img.shields.io/badge/Chart.js-4.x-FF6384?style=flat-square&logo=chart.js&logoColor=white)](https://www.chartjs.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

---

## 🎯 Problem

Claude Cowork를 수개월 쓰다 보면 **세션 수가 200개를 넘어가면서 패턴 추적이 불가능**해집니다:

- 어떤 카테고리(개발/자동화/파일정리)에 시간을 가장 많이 쓰고 있는가?
- 같은 태스크를 **몇 번이나 반복**했는가? (→ 자동화 대상 식별)
- 주간·월간 생산성 추이는 어떤가?
- **스케줄링 태스크**는 어느 날짜에 몰려 있는가?

Cowork 자체는 세션 히스토리만 제공할 뿐, **메타분석 툴이 없음**.

## 💡 Solution

229개 세션 데이터를 **하드코딩된 JSON 배열**로 임베드하고, 6개 시각화 패널로 대시보드화:

```
  229 Cowork Sessions
        │
        ▼
  [ DATA Array ]  ← 세션별 {num, date, title, cat} 구조
        │
        ▼
  ┌─────────────────────────────────┐
  │  6개 분석 패널                  │
  │  1. 카테고리별 세션 수 (bar)    │
  │  2. 카테고리 비율 (doughnut)    │
  │  3. 일별 세션 추이 (line)       │
  │  4. 자동화 TOP 10 (ranked)      │
  │  5. 일자별 자동화 구성 (stacked)│
  │  6. 스케줄 최적화 인사이트      │
  └─────────────────────────────────┘
```

## 📊 Dashboard Panels

| # | 패널 | 용도 |
|---|------|------|
| 1 | **카테고리별 세션 수** | 시간 투자 분포 파악 (bar chart) |
| 2 | **카테고리 비율** | 전체 중 비중 (doughnut chart) |
| 3 | **일별 세션 추이** | 날짜 확인 세션의 시계열 (line chart) |
| 4 | **자동화 태스크 반복 TOP 10** | 중복 작업 → **자동화 우선순위** 산출 |
| 5 | **일자별 자동화 구성** | 스케줄 태스크 분포 (stacked bar) |
| 6 | **스케줄 최적화 인사이트** | 요일·시간대 추천 (text insights) |

## 🗂 Data Categories

본 대시보드의 229개 세션은 다음 카테고리로 분류:

- **개발/기술** — 코딩·리포지토리·CI/CD
- **자동화/스케줄** — cron·Notion·Slack·Gmail 자동화
- **파일/폴더 정리** — Drive·SSD·로컬 디렉토리 구조
- **Notion** — OKR/KPI·대시보드 구축
- **데이터/모니터링** — 나라장터·KOI·부동산 스캐닝
- **IT/도구** — 브라우저 자동화·기기 관리
- **기타** — OpenClaw 등 특수 툴

## 🛠 Tech Stack

- **Frontend**: Vanilla JavaScript (프레임워크 없음)
- **Charts**: Chart.js 4.x (bar, doughnut, line, stacked)
- **Data**: 하드코딩된 JSON 배열 (offline-first, 외부 API 의존 없음)
- **Hosting**: GitHub Pages (정적 배포)
- **Size**: 단일 HTML 파일 ~30KB

## 🎨 Design Philosophy

- **Offline-first**: 외부 API 호출 없음 → 프라이버시 보호, 오프라인 사용 가능
- **Single file**: 모든 코드·데이터·스타일이 `index.html` 한 파일에 내장
- **Zero deps**: Chart.js만 CDN에서 로드, 빌드 스텝 없음

## 🚀 Quick Start

```bash
git clone https://github.com/DongsooJung/cowork-dashboard.git
cd cowork-dashboard
python -m http.server 8000
# → http://localhost:8000
```

데이터를 자신의 Cowork 세션으로 교체하려면 `index.html`의 `const DATA = [...]` 배열을 수정하세요.

## 📈 Insights Derived (본 데이터 기준)

229개 세션 분석 결과:
- **자동화/스케줄**이 가장 많은 카테고리 (~40%) — Notion OKR, 데일리 브리핑, 나라장터 스캔 등
- **파일/폴더 정리**는 6개월간 지속적으로 반복 (→ 근본 해결 방법 필요)
- **2026-03-30 피크** — 주간 인프라 재구축 집중 일

## 📅 Roadmap

- [x] v1.0: 6개 패널 기본 대시보드
- [ ] v1.1: Claude API로 세션 제목 자동 분류 (현재 수동)
- [ ] v1.2: JSON 파일 분리 → 세션 추가 시 대시보드 재빌드 없이 반영
- [ ] v1.3: 카테고리 필터 + 기간 선택
- [ ] v2.0: Notion DB 연동 — 세션 추가 시 자동 동기화

## 🎓 Author

**정동수 (Dongsoo Jung)** — Stargate Corporation CEO
- AI × 생산성 분석
- SNU 스마트도시공학 박사 수료
- [GitHub](https://github.com/DongsooJung) · [Portfolio](https://dongsoojung.github.io)

## 📄 License

MIT License.

---

> *"You can't optimize what you don't measure. This dashboard measured 229 sessions so I could stop repeating myself."*
