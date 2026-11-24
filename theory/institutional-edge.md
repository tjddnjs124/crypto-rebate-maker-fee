# 동일 모델 시대의 제도적 차이

| 차이 | 작동 방식 | 검증 항목 |
|---|---|---|
| Zero fee | 명시 수수료를 줄인다 | 같은 크기의 실행 호가, spread·시장충격·수수료 합 |
| Maker rebate | 실제 maker fill마다 보상한다 | 상품·계정 등급·조건·입금·체결 품질 |
| 접속 속도 | queue 도착, 취소, 헤지 시점을 바꾼다 | 수신·송신·거래소 접수·취소 효력의 지연 분포 |
| 제도 접근성 | 프로그램, 담보, 데이터, 거래 자격이 다르다 | 가입·유지 비용과 조건 변화 |
| 자체 체결 데이터 | 내 주문별 결과를 측정할 수 있다 | fill·partial·cancel·markout·inventory 기록 |

## 수수료와 시장의 반응

2022년 Binance BTC 현물 zero fee 도입을 연구한 Galati(2024)는 연구 표본에서 spread 확대와 낮아진 depth를 보고했다. 시나리오로 계산한 fee 포함 taker 비용도 증가했다. 전체 거래비용은 실행 크기와 방향, 실제 계좌 요율로 측정해야 한다. [Galati](../papers/galati-2024.md)

## 속도와 그 가치

Brogaard 외(2015)의 스톡홀름 연구에서 co-location 속도 개선 참여자는 adverse selection 노출과 inventory 관리에서 이점을 보였다. Yao–Ye(2018)는 상대 tick이 큰 시장의 가격·시간 우선 queue에서 속도의 가치를 설명했다. Aquilina 외(2022)의 영국 주식 지연경쟁은 최빈 승패 간격이 5–10µs였다. 이 수치를 암호화폐에 대입하지 않는다. [Brogaard 외](https://doi.org/10.1093/rfs/hhv045) · [Yao–Ye](https://academic.oup.com/rfs/article-abstract/31/6/2157/4975833) · [Aquilina 외](https://academic.oup.com/qje/article/137/1/493/6368348)

차별 요율과 속도는 상호작용한다. 더 좋은 fee가 있어도 늦은 취소로 손실이 커질 수 있고, 속도를 높이려는 재호가가 queue 순위를 손상할 수 있다. 같은 신호와 위험 한도에서 각각 바꾼 2×2 비교가 필요하다. [검증 명세](../strategy/validation.md)
