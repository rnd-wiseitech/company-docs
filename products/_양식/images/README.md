# 제품 화면 캡쳐 이미지

제품 `README.md` 본문에 삽입되는 솔루션 화면 캡쳐를 보관하는 폴더입니다.
**제품 폴더 안의 `images/`** 에 넣습니다 (예: `products/와이즈AIOps/images/`).

## 파일명 규칙

- **`대분류-중분류[-세부]` 영문 케밥케이스**로 짓습니다.
  - 예: `data-manager-dataset.png`, `workflow-canvas.png`, `model-manager-history.png`
- 한글 파일명은 Git·웹서버·일부 뷰어에서 인코딩 문제가 생길 수 있어 지양합니다.
  (본문 캡션·alt 텍스트는 한글 사용 OK)
- 형식은 `png` 권장, 한 장당 1MB 이하로 줄여주세요.

## 마크다운 삽입 문법

```markdown
![데이터셋 관리 화면 — 등록된 데이터셋 목록과 통계 정보](./images/data-manager-dataset.png)
```

> alt 텍스트(`[]` 안)는 화면 내용을 요약해 적습니다.
> 제안서 생성 시 이미지 픽셀은 읽지 못하지만 **alt 텍스트는 그대로 반영**됩니다.
> "화면1", "캡쳐" 같은 alt 는 쓰지 마세요.

## 폭 조절이 필요하면 (HTML)

```html
<img src="./images/workflow-canvas.png" alt="워크플로우 캔버스" width="700">
```

## 캡쳐 시 주의

- 고객사명·실제 데이터·계정 정보가 보이는 화면은 가리거나 데모 데이터로 다시 캡쳐하세요.
  **이 저장소는 공개(public) 입니다.**
