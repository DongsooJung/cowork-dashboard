# 📊 Claude Cowork 세션 분석 대시보드

> **135+ Claude Cowork 세션의 메타데이터를 분석하여 워크플로우 효율을 시각화**
>
> 세션 수, 사용 모델별 분포, 평균 응답 시간, 작업 유형 분류를 한눈에 확인할 수 있는 단일 페이지 대시보드.

[![Deploy](https://img.shields.io/badge/Deploy-GitHub%20Pages-181717?style=flat-square&logo=github&logoColor=white)](https://dongsoojung.github.io/cowork-dashboard/)
[![Model](https://img.shields.io/badge/Analyzed-Claude%20Opus%204.6%20%2B%20Sonnet%204.6-C2956F?style=flat-square)](https://www.anthropic.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

---

## 🎯 Problem

Claude Cowork로 수행한 작업이 누적될수록, **어떤 세션이 실제로 산출물을 만들었는지 · 어떤 작업이 반복·낭비되었는지**를 파악하기 어렵습니다. 텍스트 로그만으로는 **세션 간 패턴**을 볼 수 없습니다.

## ✨ Solution

수집된 Cowork 세션 메타데이터를 5-phase 감축 플랜과 연결하여, **"135 세션 → 30 active 세션" 78% 감축** 진행도를 추적하는 대시보드입니다.

## 📊 Dashboard Contents

- 📈 **세션 수 추이** — 일자별·주차별 신규 세션 카운트
- 🏷 **작업 유형 분류** — Kmong 제작 / Notion 관리 / Drive 정리 / 연구 / 기타
- 🤖 **모델별 사용 분포** — Opus 4.6 / Sonnet 4.6 / Haiku 4.5 비율
- ⏱ **평균 세션 소요 시간** — 작업 유형별 heat map
- 🎯 **감축 플랜 진행도** — 5-phase 계획 기준 % 달성

## 🛠 Tech Stack

- **Vanilla HTML + CSS + JS** — 단일 파일, 빌드 도구 없음
- **Chart.js** (권장 CDN 통합) — 시각화
- **GitHub Pages** — 정적 호스팅

## 🚀 Live Demo

**▶ https://dongsoojung.github.io/cowork-dashboard/**

## 📂 Structure

```
cowork-dashboard/
└── index.html    # 단일 페이지 대시보드 (28KB)
```

## 🔗 Related

- [Notion 229-conversation archive](https://www.notion.so/) — v2.0 스코어링 데이터 소스
- [GitHub 잔재 리포 정리 프로젝트](https://github.com/DongsooJung) — 동일한 "감축 플랜" 철학 적용

## 📄 License

MIT © 2026 Dongsoo Jung / Stargate Corporation

---

<p align="center">
  <sub>Built to make AI workflows measurable · <a href="https://stargate11.com">Stargate Corp</a></sub>
</p>
