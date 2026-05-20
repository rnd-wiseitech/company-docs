# company-docs

와이즈아이텍 회사 정보 저장소입니다.  
제안서·PPT 자동 생성 시 LLM(Claude 등)에 컨텍스트로 전달하는 문서들을 관리합니다.

---

## 구조

```
company-docs/
├── company_profile.json   # 회사 기본 정보 (LLM 프롬프트 주입용)
├── design/
│   └── design.md          # WISEITECH PPT 디자인 시스템 명세
├── products/              # 주요 제품별 상세 정보 (예정)
├── business/              # 주요 사업 영역 및 실적 (예정)
└── README.md
```

---

## 파일별 설명

### `company_profile.json`
LLM 제안서·PPT 생성 시 자동으로 프롬프트에 주입되는 회사 기본 정보입니다.  
제품명, 사업 영역, 수행 실적, 보유 인증 등을 포함합니다.  
실제 정보로 업데이트해서 사용하세요.

### `design/design.md`
WISEITECH PPT 디자인 시스템 명세 문서입니다.  
색상 팔레트, 타이포그래피, 컴포넌트 스타일, 레이아웃 원칙 등을 정의합니다.  
`ppt_claude_design.py` 코드와 동기화되어 있습니다.

### `products/` (예정)
주요 제품별 상세 문서를 관리합니다.

- 제품 개요 및 주요 기능
- 기술 스택 및 아키텍처
- 도입 사례 및 레퍼런스
- 보유 인증

### `business/` (예정)
주요 사업 영역과 수행 실적을 관리합니다.

- 사업 영역별 역량 기술
- 연도별 수행 실적
- 협력사 및 파트너십

---

## LLM 연동 방식

`ml-server/app.py`의 `_load_company_profile()` 함수가 `company_profile.json`을 읽어  
PPT·제안서 생성 프롬프트 상단에 자동 주입합니다.

```
[자사 정보 — 제안서 작성 시 반드시 반영]
회사명: 와이즈아이텍 (WISEITECH)
주요 사업 영역: 공공 SI, AI/ML 솔루션, 정보보안 컨설팅 ...
주요 제품: 제품A, 제품B ...
수행 실적: 행정안전부 AI 분석 시스템(2023), ...
```

---

## 업데이트 가이드

1. 제품·사업 정보가 바뀌면 `company_profile.json` 수정 후 커밋
2. 디자인 시스템이 바뀌면 `design/design.md`와 `ppt_claude_design.py` 함께 수정
3. 세부 문서는 `products/`, `business/` 폴더에 Markdown으로 추가
