# KiaCompare data

월별 트림×옵션 매트릭스 피드. 앱의 **최신화** 버튼이 아래 파일을 받아 반영합니다.

- `data/matrix.json` — 본문
- `data/version.json` — 버전·갱신 시각·해시

## 매달 갱신

1. 가격표 엑셀을 넣고 `kia-compare`에서 `python3 scripts/build_matrix.py` 실행
2. 생성된 `data/matrix.json`을 이 저장소 `data/matrix.json`에 덮어쓰기
3. `version.json`의 `version` / `updatedAt` / `sha256` 갱신 후 `main`에 푸시

앱은 `version.json`을 먼저 보고 해시가 바뀌면 `matrix.json`을 받아 저장합니다.
