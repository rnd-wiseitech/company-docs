# company-docs

와이즈아이텍 회사 정보 저장소입니다.  
제안서·PPT 자동 생성 시 LLM(Claude 등)에 컨텍스트로 전달하는 문서들을 관리합니다.

---

## 폴더 구조

```
company-docs/
├── company_profile.json        # 회사 기본 정보 (LLM 프롬프트 주입용)
├── design/
│   └── design.md               # WISEITECH PPT 디자인 시스템 명세
├── products/
│   ├── README.md               # 제품 목록 인덱스
│   ├── _양식.md                 # 새 제품 작성 양식
│   └── (제품명).md              # 제품별 상세 문서
├── business/
│   ├── README.md               # 사업 영역 인덱스
│   ├── _양식.md                 # 새 사업 영역 작성 양식
│   └── (영역명).md              # 사업 영역별 상세 문서
└── README.md
```

---

## 문서 목록

### 📋 회사 기본 정보
| 파일 | 설명 |
|------|------|
| [company_profile.json](./company_profile.json) | LLM 프롬프트 주입용 회사 기본 정보 (제품·실적·인증 요약) |

### 🎨 디자인 시스템
| 파일 | 설명 |
|------|------|
| [design/design.md](./design/design.md) | WISEITECH PPT 색상·타이포·컴포넌트·레이아웃 명세 |

### 📦 제품 정보
| 파일 | 설명 |
|------|------|
| [products/README.md](./products/README.md) | 제품 목록 인덱스 |
| [products/_양식.md](./products/_양식.md) | 새 제품 문서 작성 양식 |

### 🏢 주요 사업 영역
| 파일 | 설명 |
|------|------|
| [business/README.md](./business/README.md) | 사업 영역 목록 인덱스 |
| [business/_양식.md](./business/_양식.md) | 새 사업 영역 문서 작성 양식 |

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

| 상황 | 수정 대상 |
|------|-----------|
| 제품·실적·인증 변경 | `company_profile.json` + 해당 `products/(제품명).md` |
| 새 제품 추가 | `products/_양식.md` 복사 → `products/(제품명).md` 작성 → `products/README.md` 목록 추가 |
| 새 사업 영역 추가 | `business/_양식.md` 복사 → `business/(영역명).md` 작성 → `business/README.md` 목록 추가 |
| PPT 디자인 변경 | `design/design.md` + `ml-server/ppt_claude_design.py` 함께 수정 |
