# 🪙 원화 스테이블코인 발행사 거래 모의 시스템

> **KOSCOM AI Agent Challenge 2025**
> 원화 스테이블코인 발행·소각·준비금 흐름을 검증하기 위한 **발행사 거래 시뮬레이션 시스템**

본 시스템은 원화 스테이블코인 발행사가 
**발행–유통–소각–준비금 관리 전 과정을 안전하게 검증**하기 위해 구축된 **모의 운영(Scenario-based Simulation) 시스템**입니다.

---

## 🧑‍💻 Team DANCOM
|  권민석  |  김도연  |  양서윤  |  이도원  | 
| :-----: | :-----: | :-----: | :-----: | 
| <img src="https://avatars.githubusercontent.com/u/155413606?v=4" width=150px alt="권민석"> | <img src="https://avatars.githubusercontent.com/u/186993697?v=4" width=150px alt="김도연"> | <img src="https://avatars.githubusercontent.com/u/138513591?v=4" width=150px alt="양서윤"> | <img src="https://avatars.githubusercontent.com/u/204447212?v=4" width=150px alt="이도원"> | 
| [@kwonminseok242](https://github.com/kwonminseok242) | [@kxmdoyn](https://github.com/kxmdoyn) | [@seoyun0311](https://github.com/seoyun0311) | [@leedw21](https://github.com/leedw21) |

---

## 🎯 구축 목적

원화 스테이블코인 리스크 관리 AI Agent를 설계함에 있어,
단순 이론 설계가 아닌 **실제 발행사 운영 흐름을 전제로 한 데이터 생성 환경**이 필요했습니다.

이에 따라 본 시스템은:

* 발행량 변화
* 유통량 증감
* 은행 예치금 변동
* 담보 비율 변화

를 **의도적으로 발생시키는 발행사 시뮬레이션 환경**을 제공합니다.

👉 AI Agent는 이 데이터를 기반으로 **리스크 분석·감사·보고 기능을 실증**합니다.

---

## 🧩 시스템 역할 (Positioning)

```text
[ Issuer Simulation System ]
        ↓ (API / Event)
[ Cloud Database ]
        ↓
[ MCP Risk Management AI Agent ]
```

* 실제 발행 시스템을 **대체하지 않음**
* 리스크 관리 AI Agent 검증을 위한 **데이터 소스 역할**
* 로컬·클라우드 어디서든 실행 가능한 경량 구조

---

## 🔄 핵심 시뮬레이션 시나리오

### 1️⃣ 토큰 발행 (Mint)

* 발행사가 K-WON 토큰 신규 발행
* On-chain 발행량 증가
* Off-chain 준비금 증가 시뮬레이션

### 2️⃣ 토큰 유통 (Circulation)

* 사용자 지갑으로 토큰 이동
* 순유통량(Net Circulation) 변화

### 3️⃣ 토큰 소각 (Burn)

* 토큰 환매·소각 시나리오
* 발행량 및 준비금 동시 감소

### 4️⃣ 담보 비율 변동

* 은행 예치금 증감 시나리오
* 담보 비율 정상 / 경고 / 위험 구간 유도

---

## 🏗 아키텍처 개요

```text
[ Web / Dashboard ]
        ↓ HTTP / JSON-RPC
[ Issuer Operation Server ]
        ↓
[ Blockchain Node (Local / Testnet) ]
        ↓
[ Cloud DB (PostgreSQL) ]
```

* 발행·소각 요청은 API 기반 처리
* 블록체인 이벤트는 DB에 기록
* AI Agent 및 MCP 서버가 동일 DB 참조

---

## 🖥 주요 기능

* 발행량 / 유통량 / 소각량 제어
* 은행별 예치금 수동·자동 조정
* 실시간 담보 비율 시각화
* 리스크 상황 재현용 테스트 버튼

---

## 🔗 AI Agent 연계 포인트

본 시뮬레이션 시스템은 다음 MCP 서버의 입력 데이터로 활용됩니다.

* **MCP SERVER ①**: 1:1 완전 담보 실시간 검증
* **MCP SERVER ②**: 예치은행 신용위험 & 분산도 분석
* **MCP SERVER ③**: 감사 추적 및 불변 증빙 생성
* **MCP SERVER ④**: 규제 준수 보고 자동 생성

---

## 🧪 활용 예시

* 담보 비율 103% 이하 상황 재현 → 위험 알림 테스트
* 특정 은행 예치 비중 과다 → 재배치 정책 검증
* 특정 거래 단건 감사 → 증빙팩 생성 검증

---

## ⚠️ 참고 사항

* 본 시스템은 **실제 금융 서비스용이 아닌 시뮬레이션 목적**입니다.
* 실제 발행 시스템 적용 시 보안·인증·권한 관리 강화 필요

---

