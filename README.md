# Crypto maker rebate 연구

**판정 — 조건부로 가능한 연구 가설.** 실제 maker 체결에서 받은 rebate가 가격·재고·헤지·운영의 전체 손실을 초과하면, 방향 예측 없이도 양의 순수익이 가능하다. 우대 요율은 경쟁자 대비 명확한 비용 우위다. 체결 가능성과 위험을 포함한 실전 수익성은 아직 검증되지 않았다.

이 저장소는 전략 코드가 아닌 문헌과 설계의 지식 기반이다. 수수료, 상대 속도, 거래소 조건의 차이가 어떻게 전략의 차별화로 이어지는지 함께 다룬다.

## 먼저 읽기

1. [결론과 논증](theory/rebate-only-edge.md) — 왜 우위가 가능하고, 왜 자동 수익은 아닌가
2. [수익 회계](strategy/pnl-equation.md) — 가격손익·rebate·위험 비용의 단위와 기준
3. [전략 명세](strategy/rebate-only-design.md) — 양방향 post-only, 재고 관리와 종료 규칙
4. [검증 명세](strategy/validation.md) — 대조군, 실제 체결, 조건 변경과 판정
5. [제도적 차별화](theory/institutional-edge.md) — zero fee, maker rebate, 속도와 데이터
6. [논문 색인](papers/README.md) · [거래소 조건](references/exchange-programs.md)

## 디렉터리

- `theory/` — 시장 구조와 제도 경제학
- `strategy/` — 수익 회계, 연구 설계와 검증
- `risks/` — 체결 및 inventory 위험
- `papers/` — 논문별 출처와 적용 범위
- `references/` — 거래소 문서와 용어

## 연구 상태

- 2026-11-22 초기 문헌 조사.
- 2026-11-24 rebate-only 가설을 심층 정리하고 과도한 1틱 필수 주장 및 논문 서지 오류를 수정. 실제 계좌 요율·queue·체결 및 수익은 미검증.
