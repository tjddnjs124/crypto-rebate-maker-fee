# crypto-rebate-maker-fee

Maker rebate 수확 전략을 위한 문헌 조사·이론 정리·설계 원칙 저장소.

## 목적

암호화폐 거래소에서 maker 리베이트만을 수익원으로 하는 마켓메이킹 전략의 이론적 근거를 정리한다.
이 저장소는 전략 코드가 아니라 **지식 기반**이다. 무엇이 성립 조건이고 무엇이 리스크인지를 논문 단위로 추적한다.

## 구조

```
├── README.md               # 이 파일. 진입점
├── AGENTS.md               # AI 에이전트 운영 규칙
├── theory/                  # 이론 — 주제별 종합
│   ├── fee-structure.md     # make-take 수수료 경제학
│   ├── market-making.md     # 인벤토리 제어와 최적 호가
│   ├── execution-probability.md  # LOB 체결 확률 모형
│   └── crypto-microstructure.md  # 암호화폐 시장 특성
├── risks/                   # 전략 리스크
│   ├── adverse-selection.md # 정보 거래자에게 뺏기는 것
│   └── spoofing.md          # 조작·layering 방어
├── papers/                  # 논문 — 1논문 1파일
│   ├── README.md            # 주석 달린 색인
│   └── *.md                 # 개별 논문 노트
├── strategy/                # 전략 설계
│   ├── pnl-equation.md      # 핵심 순수익 식
│   ├── design-principles.md # 배포 전 확인 목록
│   └── open-questions.md    # 미해결 연구 과제
└── references/
    └── glossary.md          # 용어집
```

## 핵심 결론 (3줄)

1. **티크가 이산이고 스프레드가 1틱에 갇혀 있을 때만** maker 리베이트의 실질 이득이 존재한다. 연속 가격에서는 리베이트가 스프레드에 완전히 흡수된다.
2. **체결이 리베이트원이고 인벤토리는 리스크원이다.** Avellaneda-Stoikov류 최적 호가 식으로 인벤토리를 mean-revert 시키지 않으면 무방향 손실이 리베이트를 초과한다.
3. **Adverse selection과 spoofing이 최대 실무 리스크다.** 정보가 있는 큰 주문이 오면 maker가 먼저 체결되고 손해를 본다.

## 읽는 순서

1. `theory/fee-structure.md` — 왜 이 전략이 존재할 수 있는가
2. `theory/market-making.md` — 인벤토리를 어떻게 제어하는가
3. `strategy/pnl-equation.md` — 순수익이 어떻게 계산되는가
4. `risks/adverse-selection.md` — 언제 이 전략이 실패하는가
5. `papers/README.md` — 원문을 어디서 확인할 것인가

## 상태

- 2026-11-22: 문헌 조사 완료. 논문 16개 확인, 핵심 11개 정리.
- 다음: 거래소 수수료표 조사 → 1틱 스프레드 지속시간 측정 → 백테스트 설계.
