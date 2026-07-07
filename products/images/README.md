# 제품 문서 캡쳐 이미지

제품 `.md` 문서에 삽입되는 솔루션 화면 캡쳐를 보관하는 폴더입니다.

## 폴더 규칙

- 제품별로 하위 폴더를 둡니다. 예: `와이즈AIOps/`
- 파일명은 **`대분류-중분류[-세부]` 영문 케밥케이스**로 짓습니다.
  - 예: `data-manager-dataset.png`, `workflow-canvas.png`, `model-manager-history.png`
  - 한글 파일명은 Git·웹서버·일부 뷰어에서 인코딩 문제가 생길 수 있어 지양합니다. (본문 캡션·alt 텍스트는 한글 사용 OK)

## 마크다운 삽입 문법

```markdown
![데이터셋 관리 화면 — 등록된 데이터셋 목록과 통계 정보](./images/와이즈AIOps/data-manager-dataset.png)
```

> alt 텍스트(`[]` 안)는 화면 내용을 요약해 적습니다. LLM 제안서 생성 시 이미지 픽셀은 못 읽지만 alt 텍스트는 반영됩니다.

## 폭 조절이 필요하면 (HTML)

```html
<img src="./images/와이즈AIOps/workflow-canvas.png" alt="워크플로우 캔버스" width="700">
```
