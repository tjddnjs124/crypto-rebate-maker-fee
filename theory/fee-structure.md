# Make-take 수수료와 가격 경쟁

Maker fee는 체결한 유동성 공급자에게 적용되고, 음수인 경우 rebate가 입금된다. Taker fee는 유동성을 즉시 소비한 주문에 적용된다. 실제 적용은 상품, 계정, 프로그램 및 시점에 따라 다르다.

마찰이 없고 경쟁적인 Colliard–Foucault 모형에서는 전체 수수료를 고정한 채 maker/taker 사이의 분할만 바꾸면 quote가 조정되어 그 효과가 중립적일 수 있다. 이는 모형의 조건부 결과다. [Colliard–Foucault](../papers/colliard-foucault-2012.md)

Foucault–Kadan–Kandel은 양쪽 참여자의 감시와 반응이 서로 영향을 주는 liquidity cycle 모형으로 비대칭 fee를 설명했다. Lin–Swan–Harris는 거래·라우팅이 명목 가격에 의존하는 제약을 포함하고 NASDAQ fee 변경을 검토해 fee 분할이 tick과 무관하게 영향을 미칠 수 있다고 주장한다. 두 결과는 시장 설계와 가정에 의존한다. [Foucault 외](../papers/foucault-kadan-kandel-2013.md) · [Lin 외](../papers/lin-swan-harris-2025.md)

TSX fee 변경을 연구한 Malinova–Park는 quote가 조정된 뒤 taker의 fee 포함 거래비용이 변하지 않았다고 보고했다. 모든 시장질 지표가 변화하지 않았다는 뜻으로 확대하지 않는다. [Malinova–Park](../papers/malinova-park-2015.md)

따라서 **1틱은 검토할 시장 상태이지 rebate 수익의 필수·충분 조건이 아니다.** 적용 요율, 실제 fill, quote와 종료 비용을 함께 검증한다. [심층 논증](rebate-only-edge.md)
