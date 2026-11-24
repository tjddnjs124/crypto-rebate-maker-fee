# Adverse selection과 체결의 질

Maker는 상대방이 거래를 선택하는 시점에 체결된다. 시장 흐름이 거래자에게 유리하게 움직일 때 대기 주문이 체결되는 경향이 있으면 maker의 체결 이후 가격 변화는 불리할 수 있다. 그 원인이 항상 정보 보유자 때문이라고 단정할 수는 없다.

매수 fill의 경우 `(미래 mid - 체결가) / 체결 당시 mid`, 매도 fill은 반대 부호로 markout을 계산한다. 이를 시점별, 시장 상황별, queue와 inventory별로 보고한다. 체결 가격에서 계산한 markout에는 즉시 체결 가격의 유불리와 이후 가격 변화가 모두 포함된다. 측정·부호는 [손익식](../strategy/pnl-equation.md)을 따른다.

[Albers 외](../papers/albers-et-al-2022.md)는 과거 Bybit BTC perpetual에서 maker 전략과 단순 기준을 실제 주문으로 비교했다. 학습된 조건으로 quote를 관리한 전략에서 약 5일의 순손익이 양수였고 기준 대비 약 1bp 개선을 보고했다. 시기·상품·당시 요율과 표본 기간에 한정된 결과다.

더 먼 quote, 빠른 취소, inventory skew는 위험과 함께 체결 수량·queue 위치도 바꾼다. 따라서 완화 효과는 동일 기간 대조군과 최종 순손익으로 평가한다.
