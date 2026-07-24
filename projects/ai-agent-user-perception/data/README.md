# Data Guide

## Source

- **Platform:** Google Play Store
- **App:** ChatGPT
- **Country setting:** United States (`us`)
- **Observed period:** 2023-07-26 ~ 2026-04-02
- **Comparison date:** 2025-07-17

원본 리뷰는 공개 저장소에 포함하지 않습니다. 리뷰 작성자 이름과 리뷰 본문에는 개인정보가 포함될 수 있고, 플랫폼 데이터의 재배포 조건도 별도로 확인해야 하기 때문입니다.

## Expected File

`data/raw/GPT_reviews_YYYYMMDD.csv`

최신 날짜가 포함된 파일을 노트북이 자동으로 선택합니다. 최소 필요 열은 다음과 같습니다.

| 열 | 설명 |
|---|---|
| `score` | 앱 평점 |
| `date` 또는 `at` | 리뷰 작성 시각 |
| `review` 또는 `content` | 리뷰 본문 |
| `name` 또는 `userName` | 선택 사항. 로드 직후 제거 |

## Public Reproduction

1. 본인이 합법적으로 수집·보유한 원본 CSV를 `data/raw/`에 배치합니다.
2. 먼저 `RUN_MODE = "sample"`로 실행합니다.
3. 전체 실행은 충분한 메모리와 시간을 확보한 뒤 진행합니다.

## Privacy Rules

- 원본 리뷰, 작성자 이름, 제거 리뷰 로그는 Git에 올리지 않습니다.
- 대표 문서 CSV에는 리뷰 본문이 들어가므로 `outputs/representative_docs/`에만 저장하고 공개하지 않습니다.
- 공개 결과표에는 집계값, 토픽 키워드, coherence와 토픽 비중 변화만 포함합니다.

