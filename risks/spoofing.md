# Spoofing과 조작 리스크

## 정의

**Spoofing**은 실제 의도 없이 대량 한정주문을 한쪽에 놓아 시장 참여자를 속이고 반대편 체결을 유도하는 조작이다.

리베이트 전략은 항상 order book에 주문을 노출하므로 spoofing의 직접적인 표적이 된다.

## 주요 형태

| 형태 | 방법 | 탐지 신호 |
|---|---|---|
| Layering | 여러 가격 레벨에 대량 주문 | 깊은 큐에 반복 대량 등장·취소 |
| Vacuuming | 특정 레벨에 대량 주문 후 취소로 유동성 공백 생성 | 급작스러운 큐 소멸 |
| Momentum ignition | spoofing으로 방향성 움직임 유발 후 반대편 체결 | 짧은 시간 다수 취소 |

## 문헌

### Wang (2017) — Agent-based model

Spoofing이 어떻게 limit order book에서 가격을 조작하는지 agent-based model로 보여줬다.
Spoofing이 수익성이 있고 시장을 불안정하게 만들며, 거래가 활발한 시기에 더 발생한다는 것을 확인했다.

### Cartea et al. (2020, 2023)

큐 불균형(liquidity imbalance)을 spoofing 탐지에 활용하는 방법을 제시했다.

### Learning the Spoofability of LOB (2025, arXiv)

Level-3 데이터로 neural network를 학습해 spoofing 확률을 예측했다.
2024-12-04부터 12-07까지 데이터에서 31%의 대형 주문이 spoofing 가능성이 있다고 판정했다.
Spoofing 주문은 book 깊은 곳에 놓이는 경향이 있다는 것을 확인했다.

## 리베이트 전략에서의 방어

1. **큐 상태 감시** — 같은 방향에 대량 주문이 급격히 쌓이면 체결을 일시 중단.
2. **취소율 모니터링** — 취소가 급증하면 spoofing 신호일 수 있음.
3. **Posting distance** — spoofing은 주로 깊은 곳에 놓이므로, 최상단 큐의 급변만으로 판단하지 않도록 주의.
4. **체결 후 반응 지연** — spoofing 유도 체결은 보통 짧은 시간 안에 가격이 되돌아오는 패턴.

## 핵심 교훈

암호화폐 거래소는 규제시장보다 spoofing 탐지·처벌이 약하다. 따라서:

- 체결 확률 모형이 "정상적인" taker flow만 가정하면 spoofing에 취약하다.
- 큐 불균형·취소 패턴을 독립 변수로 포함해야 한다.
- 리베이트 전략의 인프라 비용에는 spoofing 탐지 layer가 포함되어야 한다.
