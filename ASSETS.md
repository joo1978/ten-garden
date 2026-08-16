# TEN GARDEN — 외부 자산 및 라이선스 현황

이번 난이도/사운드 업데이트(rulesetVersion 2) 기준으로 프로젝트가 사용하는 모든 외부 자산을 기록합니다.
Google Play 공개 출시를 검토할 경우 이 문서를 기준으로 재검토하세요.

## 효과음

**외부 음원 파일을 전혀 사용하지 않습니다.**
모든 효과음(연결음, 성공음, 큰 꽃/긴 연결음, 콤보 단계 상승음, 왕관 획득음, 게임오버음)은
`index.html`의 `SoundEngine` 모듈에서 Web Audio API(`OscillatorNode`/`GainNode`)로 런타임에
직접 생성합니다. 파일명, 출처, 라이선스 표기가 필요한 대상이 없습니다.

- 위치: `index.html` 내 `SoundEngine` (IIFE)
- 방식: 순수 코드 생성 사인/삼각파 톤, 파일 용량 0바이트 추가
- 재배포/상업적 사용 제약: 없음 (자체 저작물)

## 폰트

번들 폰트 파일 없음. OS/브라우저 기본 폰트 스택만 사용합니다:
`-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Apple SD Gothic Neo", "Noto Sans KR", sans-serif`

## 이미지 / 아이콘

번들 이미지 파일 없음. 모든 시각 요소는 CSS 도형 또는 표준 유니코드 이모지(🌸🌻🔗👑 등)로,
사용자 기기/브라우저가 제공하는 폰트로 렌더링됩니다.

## 외부 라이브러리 / SDK

| 파일/모듈 | 출처 | 라이선스 | 상업적 사용 | 저작자 표시 필요 여부 |
|---|---|---|---|---|
| Firebase JS SDK (`firebase-app.js`, `firebase-firestore.js`) v12.17.1, CDN(`gstatic.com`) | Google | Apache License 2.0 | 가능 | 불필요 (NOTICE 파일 요구 없음, SDK 자체 재배포 아님) |

Firebase는 랭킹(리더보드) 저장/조회 목적의 백엔드 SDK로만 사용되며, 코드를 복사하지 않고
공식 CDN에서 그대로 import합니다.

## 정책

- 출처 불명 효과음/이미지/폰트/코드는 사용하지 않습니다.
- 향후 외부 자산을 추가할 경우 반드시 이 표에 파일명·출처·라이선스·상업적 사용 가능 여부·저작자 표시 필요 여부를 기록한 뒤 사용합니다.
- 라이선스가 불명확하면 사용하지 않습니다.
