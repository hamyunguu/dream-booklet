# 드림학기제 책자 (QR 플립북)

QR을 찍고 들어오면 중철제본 느낌의 책자 표지가 보이고, 표지를 누르면 실제 책처럼 페이지를 넘기며 볼 수 있는 웹입니다.

## 사용 방법

1. **PDF 넣기** — 보여줄 책자 PDF를 이 폴더에 **`booklet.pdf`** 라는 이름으로 넣습니다.
   (이름을 바꾸고 싶으면 `index.html` 상단의 `PDF_URL` 값을 수정하세요.)
2. 끝입니다. `index.html`을 열면 동작합니다.

## 로컬에서 미리보기

브라우저로 `index.html`을 직접 열면 PDF 로딩이 막힐 수 있어, 간단한 서버로 띄우는 걸 권장합니다.

```bash
cd 드림학기제
python3 -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

## GitHub Pages 배포 (QR이 가리킬 실제 주소 만들기)

1. GitHub에 새 저장소를 만들고 이 폴더의 파일을 모두 올립니다.
2. 저장소 **Settings → Pages → Source** 를 `main` 브랜치 `/ (root)` 로 설정합니다.
3. 잠시 후 `https://<아이디>.github.io/<저장소이름>/` 주소가 생깁니다.
4. 이 주소로 **QR 코드**를 만들어 배포하면 됩니다.

## 구성

- `index.html` — 표지 + 플립북 뷰어 (모두 포함)
- `booklet.pdf` — 보여줄 책자 (직접 넣어주세요)
- 라이브러리: [PDF.js](https://mozilla.github.io/pdf.js/) (PDF 렌더), [StPageFlip](https://github.com/Nodlik/StPageFlip) (책 넘김 효과) — CDN 사용
