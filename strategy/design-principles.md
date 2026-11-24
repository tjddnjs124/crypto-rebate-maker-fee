# 설계 원칙

시장 선택의 기준은 체결 후 순손익과 필요한 자본이다. 1틱 비중, 변동성, 데이터 지연, 거래량, rebate tier는 측정 변수이며 이 저장소에서 정한 보편적 숫자 기준은 없다.

- 계정·상품별 실제 적용 fee와 rebate 입금, tier 산정과 유지비 확인.
- 실제 queue, partial fill, post-only 처리와 cancel 효력 확인.
- inventory 상한, funding·margin, 종료 방법 및 잔여 inventory 평가 명세.
- 체결 이후 markout과 위험 시점의 꼬리 손실 측정.
- 요율별 고정경로 대조, 시간순 독립 기간, 시장 변화와 지연의 민감도 비교.

10ms, 1틱 50% 같은 숫자는 특정 시장에서 측정·설계할 가정으로 사용하며 전략의 일반 필요조건으로 두지 않는다. 대상 BTC에 대한 구체적인 예시는 [전략 명세](rebate-only-design.md)와 [검증 명세](validation.md)를 따른다.
