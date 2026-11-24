# 체결 확률과 queue

실제 fill은 주문 접수 시 가격과 수량, 같은 가격 앞쪽 잔량, 이후 taker 주문·취소, partial fill, 경과 시간과 latency에 의존한다. 앞쪽 잔량이 많을수록 내 차례까지 남은 물량은 늘지만 감소 형태가 일반적으로 지수 함수라는 근거는 없다.

체결확률이 높아도 체결 후 불리한 가격 변화가 커질 수 있다. `P(fill)`과 `E[손익 | fill]`을 함께 추정한다. 부분체결은 queue 앞쪽에서도 발생한다. L2에서 취소가 내 앞에서 일어났는지 확인할 수 없다면 여러 가정을 비교한다.

호가 가격, 도착률 및 수수료와 실행의 상호작용에 대한 이론은 [Cont & Kukanov](https://arxiv.org/abs/1210.1625), 가격 변동의 order-flow imbalance 연구는 [Cont, Kukanov & Stoikov](../papers/cont-kukanov-stoikov-2014.md)를 참고한다. 후자를 개별 계좌 fill probability의 직접 검증으로 취급하지 않는다. 자료·지연·검증 조건은 [검증 명세](../strategy/validation.md)를 따른다.
