# 순수익 모형

## 핵심 식

```text
E[PnL] = Σ ( rebate × fill_probability × order_size )
       − Σ ( inventory_cost × sigma^2 × holding_time )
       − Σ ( adverse_selection_cost × informed_trade_probability )
       − Σ ( spoofing_loss × spoof_encounter_rate )
```

각 항의 의미와 측정 방법을 아래에 정리한다.

## 1. 리베이트 수익

```text
rebate × fill_probability × order_size
```

| 변수 | 측정 | 비고 |
|---|---|---|
| rebate | 거래소 수수료표 (VIP 등급별) | Binance VIP9 -0.003% 등 |
| fill_probability | 체결률 (1틱 내측 vs 외측) | Cont-Kukanov-Stoikov류 분석 필요 |
| order_size | 주문 크기 | 클수록 큐우선도 영향 |

**주의:** fill_probability가 높다고 항상 좋은 것은 아니다. Adverse selection 참조.

## 2. 인벤토리 비용

```text
inventory_cost × sigma^2 × holding_time
```

| 변수 | 측정 | 비고 |
|---|---|---|
| inventory_cost | 인벤토리 크기 × 가격 변동 | Avellaneda-Stoikov의 q·sigma² 항 |
| sigma^2 | 실현 변동성 | 1분 봉 등 고빈도 추정 |
| holding_time | 인벤토리 유지 시간 | 반대편 체결까지의 대기 |

**제어:** 인벤토리 상한 Q를 두고, 초과 시 해당 방향 호가 중단 (Guéant-Lehalle-Tapia).

## 3. Adverse Selection 비용

```text
adverse_selection_cost × informed_trade_probability
```

| 변수 | 측정 | 비고 |
|---|---|---|
| adverse_selection_cost | realized spread (체결가 - N초 후 미드) | 음수면 손실 |
| informed_trade_probability | 정보 거래 비율 | 선물-현물 lead, 대형 주문 신호 |

**방어:** `../risks/adverse-selection.md` 참조.

## 4. Spoofing 손실

```text
spoofing_loss × spoof_encounter_rate
```

암호화폐 거래소에서 규제가 약하므로 무시할 수 없다.

**방어:** `../risks/spoofing.md` 참조.

## 전략이 성립하는 조건

```text
rebate × fill_probability > inventory_cost + adverse_selection + spoofing_loss
```

즉, **리베이트당 체결이 만드는 총비용을 초과해야 한다.**

이 조건이 만족되기 쉬운 경우:
- 스프레드가 1틱에 갇혀 있고 (틱크 제약)
- 변동성이 낮고 (인벤토리 비용 작음)
- 정보 비대칭이 적고 (adverse selection 작음)
- 조작이 드물 때 (spoofing 빈도 낮음)
