# Wang (2017)

## 인용

Wang, X. (2017). Spoofing the Limit Order Book: An Agent-Based Model. In *Proceedings of the 18th International Conference on Autonomous Agents and MultiAgent Systems (AAMAS)*.

[PDF](https://cdn.aaai.org/ocs/ws/ws0356/15158-68369-1-PB.pdf)

## 핵심 주장

**Spoofing이 어떻게 limit order book에서 가격을 조작하는지 agent-based model로 보여줬다.**

Spoofing은:
1. 수익성이 있다
2. 시장을 불안정하게 만든다
3. 거래가 활발한 시기에 더 발생한다

## 모형

Agent들이 limit order book에서 상호작용한다. Spoofer는:
1. 실제 의도와 반대편에 대량 한정주문을 놓는다
2. 다른 참여자가 그 주문을 보고 방향을 잘못 판단하게 유도한다
3. 원하는 방향의 체결을 얻는다
4. spoofing 주문을 취소한다

## 전략에 주는 시사점

**리베이트 전략은 항상 order book에 주문을 노출하므로 spoofing의 직접적인 표적이 된다.**

1. Spoofing 주문이 보이는 방향에 maker가 체결되면 손해를 본다.
2. 큐 상태가 급변하면 체결 확률 모형이 왜곡된다.
3. 암호화폐 거래소는 규제가 약해 spoofing이 규제시장보다 빈번할 수 있다.

방어 방법은 `../risks/spoofing.md` 참조.
