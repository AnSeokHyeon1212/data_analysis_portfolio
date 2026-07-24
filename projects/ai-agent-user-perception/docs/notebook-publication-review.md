# Notebook Publication Review

검토 대상: `notebooks/01_full_analysis.ipynb`

## Verdict

분석 흐름과 방법론은 GitHub에 공개하기 적절합니다. 다만 원본 그대로 올리는 대신 경로, 출력 위치, 개인정보와 대용량 파일 규칙을 정리한 공개용 사본을 사용해야 합니다.

## What Is Good

- 원시 리뷰 로드부터 전처리, VADER, 통합 LDA, 하위 LDA, 시각화까지 순서가 명확합니다.
- 사용자 이름을 제거하고 리뷰 ID를 사용합니다.
- 출시일 당일을 제외해 전후 구분의 모호함을 줄였습니다.
- 전후 문서를 같은 LDA 토픽 공간에서 비교합니다.
- 토픽 수 탐색, 대표 문서, 결과표와 그림을 자동 저장합니다.
- 결과를 인과효과로 해석하지 않도록 주의 문구가 있습니다.
- 노트북 출력이 비어 있어 원문 리뷰나 로컬 경로가 결과 셀에 노출되지 않습니다.

## Changes Made for Public Use

- 프로젝트 탐색 기준을 로컬 `GPT/` 폴더가 아닌 저장소의 `data/`와 `notebooks/` 구조로 변경
- 입력 경로를 `data/raw/`, 생성 결과를 `outputs/generated/`로 분리
- 특정 PC의 `D:/fonts` 경로 제거
- 기본 실행 모드를 `sample`로 변경
- 원시 데이터, 제거 로그, 대표 리뷰, 모델과 대용량 산출물을 `.gitignore`에 추가
- 실제 import 기준으로 `requirements.txt` 보완

## Remaining Verification

| 점검 | 상태 |
|---|---|
| 노트북 JSON 구조와 코드 셀 오류 출력 없음 | 완료 |
| 기존 검증 CSV와 README 핵심 수치 대조 | 완료 |
| 공개 경로와 링크 점검 | 완료 |
| 공개용 사본 sample 모드 실행 | 미실행 |
| 공개용 사본 full 모드 전체 재실행 | 미실행 |

현재 실행 환경에는 `langdetect`, `nltk`, `spaCy`, `gensim`이 설치되어 있지 않아 공개용 사본을 위에서 아래까지 다시 실행하지 않았습니다. 또한 full 모드는 200만 건 이상의 원시 리뷰를 처리하므로 별도의 장시간 실행 검증이 필요합니다.

따라서 저장소의 `outputs/verified/`는 기존 연구 실행 결과와 대조된 소형 결과표이고, 공개 노트북은 **재현용으로 리팩터링했지만 아직 전체 재실행 검증 전인 버전**입니다.

## Before Publishing a Fully Executed Notebook

1. 새 가상환경에서 `requirements.txt` 설치
2. `RUN_MODE = "sample"`로 전체 셀 실행
3. sample 결과의 행 수, 기간, 토픽 테이블과 그림 생성 확인
4. `RUN_MODE = "full"`, `USE_CACHE = False`로 장시간 전체 실행
5. 새 결과와 `outputs/verified/`의 차이를 분석
6. 대표 리뷰와 제거 로그가 Git 추적 대상이 아닌지 최종 확인

