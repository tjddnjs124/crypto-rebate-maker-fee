# 용어집

| 용어 | 뜻 |
|---|---|
| Maker | 한정주문으로 유동성을 제공하는 쪽. 거래소에서 리베이트를 받는다 |
| Taker | 시장주문으로 유동성을 소비하는 쪽. 거래소에 수수료를 낸다 |
| Rebate | Maker가 체결 시 거래소로부터 받는 보너스. 보통 음수 maker fee로 표현 |
| Spread | 최우선 bid와 ask의 차이. 1틱 스프레드면 전략 존재 근거가 있음 |
| Tick | 최소 가격 변동 단위. BTCUSDT에서 보통 0.1 USDT |
| Inventory | 마켓메이커가 보유한 부호 있는 포지션. 양수면 long, 음수면 short |
| Skew | 인벤토리에 따라 bid/ask를 비대칭으로 조정하는 것 |
| Adverse selection | 정보가 있는 taker가 maker 주문을 체결시켜 maker가 손해 보는 현상 |
| Realized spread | 체결가 - N초 후 미드가격. 음수면 adverse selection 손실 |
| Queue priority | 동일 가격에서 먼저 놓인 주문이 먼저 체결되는 규칙 |
| Spoofing | 실제 의도 없이 대량 주문을 보여 반대편 체결을 유도하는 조작 |
| Layering | 여러 가격 레벨에 spoofing 주문을 겹겹이 쌓는 것 |
| Liquidity cycle | 거래 → 유동성 감소 → 새 호가 공급 → 다음 거래의 반복 (Foucault et al.) |
| LOB | Limit Order Book. 호가창 |
| Fill probability | 한정주문이 일정 시간 내 체결될 확률 |
| CARA utility | Constant Absolute Risk Aversion. Avellaneda-Stoikov가 쓰는 효용 함수 |
| HJB | Hamilton-Jacobi-Bellman. 확률적 최적제어의 해를 구하는 편미분방정식 |
| Locked market | bid = ask인 상태 |
| Crossed market | bid > ask인 상태 (음수 스프레드) |
