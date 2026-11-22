# Foucault, Kadan & Kandel (2013)

## 인용

Foucault, T., Kadan, O., & Kandel, E. (2013). Liquidity Cycles and Make/Take Fees in Electronic Markets. *Journal of Finance*, 68(2), 579-641.

DOI: [10.1111/jofi.12021](https://doi.org/10.1111/jofi.12021)

## 핵심 주장

**최소 틱크가 가격 조정을 제한할 때, maker/take 수수료 배분이 실질적으로 중요해진다.**

거래소는 거래량을 최대화하기 위해 maker에게 보조금을 주는 것이 최적일 수 있다. Maker rebate는 taker의 monitoring intensity가 maker보다 높을 때 최적이다.

## Liquidity Cycle

```text
거래 발생 → 유동성 감소 → maker가 새 호가 공급 (make phase)
→ taker가 새 유동성 소비 (take phase) → 유동성 감소 → 반복
```

이 "liquidity cycle"의 속도가 거래량을 결정한다. Maker/take 수수료 배분은 이 cycle의 속도를 조절한다.

## 논리

1. 최소 틱크가 존재하면 스프레드가 리베이트를 완전히 흡수할 수 없다.
2. Maker rebate는 taker fee보다 커지므로 maker가 더 빨리 유동성을 재공급하게 유도한다.
3. 결과적으로 거래량이 증가한다.

## 전략에 주는 시사점

**이 논문은 리베이트 전략의 존재를 옹호하는 논문이다.**

스프레드가 1틱에 갇혀 있을 때 (틱크 제약이 binding일 때), maker rebate가 실질 이득을 만든다. 따라서 **스프레드가 1틱에 머무는 시간 비율이 높은 liquid pair**에서 이 전략이 성립한다.

## 한계

- 모형이 단순화되어 있음 (균형 분석이지 실무 전략 설계가 아님)
- 거래소 경쟁은 단일 venue 가정
- 암호화폐 시장의 다중 거래소 fragmentation 미반영
