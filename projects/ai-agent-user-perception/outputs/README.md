# Verified Outputs

이 폴더에는 리뷰 원문이 없는 소형 집계 결과만 공개합니다.

| 파일 | 설명 |
|---|---|
| [data_summary.csv](verified/data_summary.csv) | 원시·영어·최종·기간·감성별 리뷰 수 |
| [main_topic_change_negative.csv](verified/main_topic_change_negative.csv) | 부정 리뷰 상위 LDA 토픽의 전후 비중과 변화량 |
| [main_topic_change_positive.csv](verified/main_topic_change_positive.csv) | 긍정 리뷰 상위 LDA 토픽의 전후 비중과 변화량 |
| [main_lda_coherence_negative.csv](verified/main_lda_coherence_negative.csv) | 부정 리뷰 LDA의 토픽 수별 coherence |
| [main_lda_coherence_positive.csv](verified/main_lda_coherence_positive.csv) | 긍정 리뷰 LDA의 토픽 수별 coherence |
| [sub_topic_change_negative.csv](verified/sub_topic_change_negative.csv) | 변화가 큰 부정 토픽의 하위 LDA 결과 |

`delta = after - before`이며 양수는 출시 후 토픽 비중 증가, 음수는 감소를 의미합니다.

다음 산출물은 생성되더라도 Git에서 제외합니다.

- `generated/`: 실행 중 생성되는 전체 표와 그림
- `cache/`: 전처리 캐시
- `models/`: LDA 모델과 배열
- `representative_docs/`: 리뷰 원문이 포함된 대표 문서
- `removed_reviews*`: 필터링된 리뷰와 제거 사유

