<p align="center">
  <img src="https://raw.githubusercontent.com/yongyong-18team/.github/main/profile/logo.png" alt="돌봄바통 로고" width="140">
</p>

# 돌봄바통 (Dolbom Baton)

> **오늘의 돌봄을 기록하고, 다음 돌봄으로 이어주는 AI 기반 발달장애인 돌봄 지원 서비스**
>
> 반복되는 설명의 부담은 줄이고, 돌봄 정보는 끊김 없이 이어갑니다.

**돌봄바통**은 발달장애인 보호자가 매일 쓰는 돌봄 일기를 AI가 정리하고, 보호자가 승인한 정보만 모아 "이 사람을 돌보는 법" 설명서로 만들어 다른 돌봄 제공자에게 링크 하나로 넘겨주는 서비스입니다. 2026 용용톤 복지 트랙 출품작입니다.

| 바로가기 | |
| --- | --- |
| 서비스 (모바일 웹) | https://yongyong-18team-frontend.vercel.app |
| 백엔드 | [yongyong-18team/backend](https://github.com/yongyong-18team/backend) · Spring Boot 3.5, PostgreSQL 16 |
| 프론트엔드 | [yongyong-18team/frontend](https://github.com/yongyong-18team/frontend) · Next.js 16, React 19 |

## 왜 만들었나

**돌봄 서류는 전달되지만, 일상의 돌봄 경험은 이어지기 어렵습니다.** 긴급돌봄이나 활동지원을 신청하면 신청서와 체크리스트는 기관에 전달되지만, 대상자가 무엇에 불안해하고 무엇으로 진정하는지는 주 보호자의 머릿속에만 남습니다. 보호자가 입원하거나 활동지원사가 바뀌면 이 정보가 끊기고, 그 공백이 곧 돌봄 공백이 됩니다.

발달장애인 보호자 45명에게 설문한 결과(10.31~11.8)입니다.

<img src="https://raw.githubusercontent.com/yongyong-18team/backend/main/docs/assets/deck_survey.jpg" alt="보호자 설문 결과 슬라이드" width="720">

| 질문 | 응답 |
| --- | --- |
| 돌봄서비스 이용 시 대상자의 특성이나 주의사항을 전달하기 어려웠나요? | **80.0%** 자주 있었다 |
| 돌보는 방법이나 주의사항 중 보호자님만 자세히 알고 있는 정보가 있나요? | **62.2%** 많이 있었다 |

## 핵심 기능

<img src="https://raw.githubusercontent.com/yongyong-18team/backend/main/docs/assets/deck_features.jpg" alt="핵심 기능 슬라이드" width="720">

1. **기록과 AI 분석**: 음성이나 텍스트로 남긴 일기에서 AI가 행동 특성, 발생 상황, 대처 방법을 뽑아 제안합니다. 보호자가 승인한 항목만 돌봄 설명서에 쌓이고, 위기 표현이 감지되면 긴급 안전 안내로 바뀝니다.
2. **기록 공유**: 보호자가 공유할 정보와 공개 범위를 직접 골라 기간 제한 링크를 만듭니다. 받는 사람은 앱 설치나 로그인 없이 엽니다. 링크는 7일 뒤 만료되고, 보호자가 언제든 막을 수 있습니다.
3. **돌봄 탐색**: 돌봄 기간, 대상자 나이, 지역 조건으로 용인시 돌봄시설과 공공 지원제도를 찾고 신청 정보까지 안내합니다.

## 용인시 공공데이터

<img src="https://raw.githubusercontent.com/yongyong-18team/backend/main/docs/assets/deck_publicdata.jpg" alt="공공데이터 활용 구조 슬라이드" width="720">

| 수집 | 정제·검증 | 돌봄 자원 DB | 확장 범위 |
| :---: | :---: | :---: | :---: |
| **252건** | **6곳** | **53곳 · 5개** | **31개 시·군** |
| 용인시 복지시설 정보 API | 명칭·주소 불일치 관리 | 장애인복지시설 · 지원제도 | 경기도 공공데이터 연계 목표 |

공공데이터포털 「경기도 용인시_복지시설 정보 조회 서비스」에는 시설 유형이 없어서, 용인시청 장애인복지시설현황과 이름·주소로 맞춰 유형을 붙였습니다. 두 자료가 서로 다른 6곳은 따로 표시해 관리하고, 지원제도 5개를 시설 유형과 연결해 조건에 맞는 제도와 가까운 시설부터 안내합니다.

## 핵심 가치

- **보호자가 정합니다**: 설명서와 공유 문서에는 보호자가 승인했거나 직접 입력한 정보만 들어갑니다. AI는 제안만 합니다.
- **AI를 그대로 믿지 않습니다**: AI가 뽑은 항목은 일기 원문에 근거 문장이 있어야만 남고, 위기 표현은 서버가 따로 한 번 더 검사합니다.
- **필요한 만큼만 공유합니다**: 공개할 섹션을 보호자가 고르고, 공유 링크는 승인 시점의 내용으로 고정됩니다.
- **보호자도 돌봅니다**: 소진 신호가 쌓이면 휴식·상담 제도를 안내하고, 위기 표현이 있으면 안전 안내를 먼저 보여줍니다.

## 비전

용인 시범 운영에서 시작해 경기도 31개 시·군, 그리고 전국으로 넓힙니다. 지역 공공데이터만 바꾸면 같은 구조로 확장할 수 있습니다. 사업 모델은 보호자에게는 무료, 지자체·돌봄기관에는 연간 구독(B2G·B2B)입니다.

| 시장 | 규모 | 구성 |
| --- | --- | --- |
| TAM | 4,229개 기관 | 전국 기초지자체 226개 + 장애인복지시설 4,003개 |
| SAM | 828개 기관 | 경기도 31개 시·군 + 장애인복지시설 797개 |
| SOM | 2개 기관 | 용인시 1개 + 지역 돌봄기관 1개 |

## 팀 · 육룡이 나르샤

2주 동안 기획 1명, 프론트엔드 2명, 백엔드 3명이 함께 만들었습니다.

| | 역할 | GitHub | 맡은 일 |
| --- | --- | --- | --- |
| <img src="https://github.com/xofkd009.png?size=64" width="48" height="48" alt="xofkd009"> | 기획 | [xofkd009](https://github.com/xofkd009) | 서비스 기획, 문구, AI 평가 데이터, 시연·발표 |
| <img src="https://github.com/Sehoon-Jeong.png?size=64" width="48" height="48" alt="Sehoon-Jeong"> | 프론트엔드 | [Sehoon-Jeong](https://github.com/Sehoon-Jeong) | 가입·온보딩·홈·기록 흐름, 위기 안내 |
| <img src="https://github.com/imly-dia.png?size=64" width="48" height="48" alt="imly-dia"> | 프론트엔드 | [imly-dia](https://github.com/imly-dia) | 설명서, 공유, 수신자 페이지, 돌봄 지원, 공동 관리자 |
| <img src="https://github.com/parkc31.png?size=64" width="48" height="48" alt="parkc31"> | 백엔드 | [parkc31](https://github.com/parkc31) | 인증, 설명서, 공유, 공동 관리자, 배포 |
| <img src="https://github.com/Hyunsuk305.png?size=64" width="48" height="48" alt="Hyunsuk305"> | 백엔드 | [Hyunsuk305](https://github.com/Hyunsuk305) | 온보딩, 일기, 음성 인식, AI 분석 |
| <img src="https://github.com/wonnbu.png?size=64" width="48" height="48" alt="wonnbu"> | 백엔드 | [wonnbu](https://github.com/wonnbu) | 리포트, 돌봄 지원, 소진 신호, 공공데이터 |

<sub>시장 규모 참고: 행정안전부 「지방자치단체 행정구역 현황」(2026), 보건복지부 「2025년 장애인복지시설 일람표」(2024.12월말 기준). 공공데이터는 2026.11.08 수집 기준입니다.</sub>
