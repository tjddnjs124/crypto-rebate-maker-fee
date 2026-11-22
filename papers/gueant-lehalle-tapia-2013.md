# Guéant, Lehalle & Fernandez-Tapia (2013)

## 인용

Guéant, O., Lehalle, C.-A., & Fernandez-Tapia, J. (2013). Dealing with the Inventory Risk: A Solution to the Market Making Problem. *Mathematics and Financial Economics*, 7(4), 477-507.

DOI: [10.1007/s11579-012-0087-0](https://doi.org/10.1007/s11579-012-0087-0)

arXiv: [1105.3115](https://arxiv.org/abs/1105.3115)

## 핵심 주장

**Avellaneda-Stoikov 모형에 인벤토리 상한 Q를 도입하고, HJB를 선형 ODE로 변환해 완전한 해를 제시했다.**

인벤토리 한도가 있는 실무 제약을 반영한 최적 호가 공식을 유도했다.

## 기여

1. 인벤토리 상한 `Q` 도입 — 실무에서 반드시 존재하는 포지션 한도 반영
2. HJB를 선형 ODE로 변환하는 change of variables 제시
3. Asymptotic behavior 분석
4. Closed-form 근사 제시

## 최적 호가 (asymptotic)

```text
delta_bid*(q) ≈ (1/gamma) * ln(1 + gamma/k) + (2q+1)/2 * sqrt(sigma^2 * gamma / (2*k*A)) * (1 + gamma/k)^(1+k/gamma)
delta_ask*(q) ≈ (1/gamma) * ln(1 + gamma/k) - (2q-1)/2 * sqrt(sigma^2 * gamma / (2*k*A)) * (1 + gamma/k)^(1+k/gamma)
```

인벤토리 `q`가 상한 `Q`에 도달하면 해당 방향의 호가를 중단한다.

## 전략에 주는 시사점

**리베이트 전략에 가장 직접 적용 가능한 논문이다.**

1. 인벤토리 상한 `Q`를 정의한다.
2. `Q`에 도달하면 해당 방향 호가를 중단한다.
3. `Q` 이내에서는 인벤토리에 따라 skew를 준다.

리베이트를 P&L에 포함하도록 확장하면, 최적 delta가 줄어들 것으로 예상된다.

## 한계

- 리베이트 미포함 (기존 P&L은 스프레드 수익만)
- 단일 자산 가정
- 도착률이 시장 상태 무관이라는 가정이 강함
