# 손익과 rebate 기여도

## 최종 원장

같은 기준통화에서, 초기와 종료의 현금·포지션·가격 및 외부 입출금을 일관되게 대사한다.

```text
순손익 = 가격 실현손익 + 잔여 inventory 평가손익
       + 실제 maker rebate - 실제 거래 수수료
       + 수취 funding - 지급 funding - 차입·헤지·운영비
```

계약별 정산 방식에 맞춘다. BTC 담보 inverse 계약이면 BTC 수량으로 먼저 계산하고 법정화폐 환산을 따로 표시한다. 주문 체결 전에는 rebate가 없다. 부분체결은 실제 체결량에 대해서만 계산하고, 열린 inventory에 가상의 종료 rebate를 주지 않는다.

## 비용 우위와 절대 수익

고정된 fills에서 `rebate 기여 = Σ(각 체결 명목 × 실제 rebate율)`이다. 동일 원장에 fee 0, 일반 fee, 개인 rebate를 대입하면 실행경로를 고정한 요율 민감도다. 실거래에서 요율에 반응한 quote와 fill이 바뀌는 효과는 다시 측정해야 한다.

Rebate가 주된 원천인 엄격한 조건은 `rebate 전 순손익 ≤ 0`이면서 `rebate 후 순손익 > 0`이다. 양수여도 한 표본의 성과다.

## 체결의 질 — markout

매수는 `s=+1`, 매도는 `s=-1`. `P`는 내 체결가, `M0`는 체결 직전 mid, `Mh`는 h 뒤 mid다. 각각 체결 당시 기준 가격으로 나눠 bp로 변환한다.

```text
즉시 가격 이점 = s × (M0 - P)
체결 후 가격 이동 = s × (Mh - M0)
h 시점 markout = s × (Mh - P)
                = 즉시 가격 이점 + 체결 후 가격 이동
fee 포함 markout = h 시점 markout + 해당 fill rebate - 해당 fill fee
```

Markout은 체결 조건부 진단값이며 최종 실현손익이 아니다. 이미 markout에 포함한 체결 후 가격 이동을 adverse selection으로 다시 빼지 않는다. 실제 최종 PnL은 모든 fills와 funding, 기말 inventory로 계산한다. 미래 mid는 청산 가능 가격을 보장하지 않는다.

가정 예시에서 즉시 이점 +0.4bp, 체결 후 이동 −0.7bp, rebate +0.2bp면 fee 포함 markout은 −0.1bp다. 실제 청산의 spread, fee 및 funding은 따로 고려한다.

## 종료 방식별 비용

- Maker 종료도 체결이 불확실하다. 시간 제한에 걸려 남은 재고를 계속 평가하거나 강제 헤지 비용을 지불한다.
- Taker 종료면 종료 수수료와 실행가격을 넣는다. 종료 명목 전체에 maker rebate를 가정하지 않는다.
- 양방향을 동시에 올려도 한쪽만 체결될 수 있다. 최소 단위·가격 단위·잔량·주문 취소 지연·margin을 반영한다.

1bp = 0.01% = 0.0001. 예를 들어 0.002%는 0.2bp이고 100만 USDT 체결의 rebate는 20 USDT다.
