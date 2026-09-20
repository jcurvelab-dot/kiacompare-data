# KiaCompare data

월별 트림×옵션 매트릭스 피드. 앱의 **최신화** 버튼이 아래 파일을 받아 반영합니다.

- `data/matrix.json` — 본문 (등급별 includes 포함)
- `data/version.json` — 버전·갱신 시각·sha256
- `data/pdf_features.json` — PDF 사양 보조 인덱스

앱/APK는 DB를 내장하지 않습니다. **최신화 = GitHub raw**가 소스 오브 트루스입니다.

## 매달 갱신

1. 가격표 PDF(·엑셀)을 `kia-compare`에 넣고  
   `python3 scripts/ingest_price_pdfs.py` → `python3 scripts/build_matrix.py`
2. `SKIP_BUILD=1 bash scripts/push_feed.sh`  
   (또는 이미 빌드된 matrix면 그대로 push_feed; 기본은 build 후 push)
3. 앱에서 **최신화** — APK 재설치 불필요

`version.json.sha256`은 `matrix.json` 바이트 SHA-256과 일치해야 합니다.
