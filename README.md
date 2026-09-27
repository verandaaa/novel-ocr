# novel-ocr

스캔된 소설 이미지에서 텍스트를 추출하는 프로젝트. EasyOCR(한글)을 사용하며,
로컬 GPU 없이도 Google Colab 무료 GPU로 처리할 수 있게 노트북을 구성했습니다.

## 사용법 (Colab, 추천)

1. [Google Colab](https://colab.research.google.com)에 접속 후 이 저장소의
   `novel_ocr_colab.ipynb`를 업로드해서 엽니다. (파일 > 노트북 업로드)
2. 상단 메뉴 **런타임 > 런타임 유형 변경 > T4 GPU** 선택 후 저장.
3. Google Drive에 스캔 이미지 폴더(예: `novel_scans`)를 올려둡니다.
4. 노트북 셀을 위에서부터 순서대로 실행 (Shift+Enter).
   - Drive 마운트 시 인증 창에서 로그인/권한 허용
   - `IMAGE_FOLDER` 경로를 본인 Drive 경로에 맞게 수정
5. 결과는 `novel_ocr_output/novel_text.txt`로 Drive에 자동 저장됩니다.
   중간에 세션이 끊겨도 이미 처리된 페이지는 남아있고, 다시 실행하면
   처리 안 된 파일만 이어서 처리합니다.

## 로컬에서 실행하려면

```bash
pip install -r requirements.txt
python ocr_batch.py
```

## 참고

- 세로쓰기 옛날 소설이나 손글씨는 별도 대응이 필요할 수 있습니다.
- 이미지가 기울어졌거나 노이즈가 많으면 인식률이 떨어질 수 있어 전처리가
  필요할 수 있습니다.
