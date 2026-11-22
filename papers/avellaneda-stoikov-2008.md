# Avellaneda & Stoikov (2008)

## 인용

Avellaneda, M., & Stoikov, S. (2008). High-frequency Trading in a Limit Order Book. *Quantitative Finance*, 8(3), 217-224.

DOI: [10.1080/14697680701381228](https://doi.org/10.1080/14697680701381228)

## 핵심 주장

**CARA utility + LOB 도착률 모형에서 마켓메이커의 최적 bid/ask에 대한 closed-form 근사를 제시했다.**

이 논문이 제시한 공식은 실무 마켓메이킹 알고리즘의 표준 출발점이 되었다.

## 모형 설정

- 미드가격 `S_t`가 Brownian motion, 변동성 `sigma`
- 도착률 `lambda(delta) = A * exp(-k * delta)`, `delta`는 미드에서의 거리
- 효용함수: CARA, 위험회피계수 `gamma`
- 유한 시간 지평 `T`

## 최적 호가 공식

```text
delta_bid* = (1/gamma) * ln(1 + gamma/k) + (1 + 2q)/2 * gamma * sigma^2 * (T-t)
delta_ask* = (1/gamma) * ln(1 + gamma/k) + (1 - 2q)/2 * gamma * sigma^2 * (T-t)
```

여기서:
- `q`는 인벤토리 (signed quantity)
- `gamma`는 위험회피계수
- `sigma^2`는 가격 변동성
- `k`는 도착률 감쇠계수
- `T-t`는 남은 시간

## 인벤토리 skew

`q > 0` (long)이면:
- `delta_bid*` 증가 → bid를 더 낮게 (덜 사려고)
- `delta_ask*` 감소 → ask를 더 낮게 (더 팔려고)

즉, 인벤토리가 쌓이면 양쪽 호가를 아래로 밀어 되파는 것을 촉진한다.

## 전략에 주는 시사점

**리베이트 전략의 인벤토리 제어는 이 공식에서 출발한다.**

다만 기존 공식에는 리베이트가 포함되어 있지 않으므로, P&L에 리베이트를 더해 확장할 필요가 있다. 리베이트가 있으면 더 좁은 스프레드를 책정해도 수익이 남으므로 최적 delta가 줄어들 것으로 예상된다.

## 한계

- 인벤토리 상한이 없음 (무한한 인벤토리 가능)
- Admissability 증명이 원문에는 없음 (Guéant et al. 2013이 지적)
- 리베이트 미포함
- 시장 impact 미포함
