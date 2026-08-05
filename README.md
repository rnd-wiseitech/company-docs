# company-docs

위세아이텍 회사 정보 저장소입니다.  
제안서·PPT 자동 생성 시 LLM(Claude 등)에 컨텍스트로 전달하는 문서들을 관리합니다.

---

## 폴더 구조

```
company-docs/
├── company_profile.json        # 회사 기본 정보 (LLM 프롬프트 주입용)
├── design/
│   ├── README.md               # 디자인 시스템 요약
│   └── design.md               # WISEITECH PPT 디자인 시스템 상세 명세
├── products/                   # 제품 하나당 폴더 하나 (KB 화면과 1:1)
│   ├── README.md               # 제품 목록 인덱스
│   ├── 작성가이드.md            # 제품 담당자용 작성 가이드
│   ├── _양식/                   # 새 제품 폴더 양식 (통째로 복사)
│   └── <제품명 한글>/
│       ├── README.md           # 제품 설명·기능 계층
│       ├── slides.md           # 제안 슬라이드 인덱스 (요구사항 ↔ 대응 문장 ↔ 원본 위치)
│       └── images/             # 제품 화면 캡쳐 png
├── business/
│   ├── README.md               # 사업 영역 인덱스
│   ├── _양식.md                 # 새 사업 영역 작성 양식
│   ├── AI데이터플랫폼.md        # Tailored AX 사업 영역
│   └── 데이터관리.md            # Data Management 사업 영역
└── databutler/
    ├── README.md               # 데이터버틀러 개요 및 인덱스
    ├── META_AI기능.md           # WiseMeta 탑재 AI 기능
    └── DQ_AI기능.md             # WiseDQ 탑재 AI 기능
```

---

## 문서 목록

### 📋 회사 기본 정보
| 파일 | 설명 |
|------|------|
| [company_profile.json](./company_profile.json) | LLM 프롬프트 주입용 회사 기본 정보 (제품·실적·데이터버틀러·인증 포함) |

### 🎨 디자인 시스템
| 파일 | 설명 |
|------|------|
| [design/README.md](./design/README.md) | 디자인 시스템 핵심 요약 (색상·폰트·컴포넌트·금지사항) |
| [design/design.md](./design/design.md) | WISEITECH PPT 색상·타이포·컴포넌트·레이아웃 상세 명세 |

### 📦 제품 정보
| 파일 | 설명 |
|------|------|
| [products/README.md](./products/README.md) | 제품 목록 인덱스 |
| [products/작성가이드.md](./products/작성가이드.md) | **제품 담당자용 작성 가이드** (새 제품 추가·보강 시 필독) |
| [products/와이즈AIOps/](./products/와이즈AIOps/) | 엔드투엔드 AI 개발·운영 플랫폼 (작성 기준 예시) |
| [products/와이즈프로펫/](./products/와이즈프로펫/) | 저코드 AI 개발 플랫폼 |
| [products/와이즈인텔리전스/](./products/와이즈인텔리전스/) | BI·시각화·**생성형 보고서** |
| [products/와이즈DQ/](./products/와이즈DQ/) | AI 기반 데이터 품질 관리 |
| [products/와이즈메타/](./products/와이즈메타/) | 메타데이터 관리·표준화 |
| [products/ASTA/](./products/ASTA/) | 시스템 영향도 분석 |
| [products/코드인슈어/](./products/코드인슈어/) | 소스코드 보안 취약점 분석 |

### 🏢 주요 사업 영역
| 파일 | 설명 |
|------|------|
| [business/README.md](./business/README.md) | 사업 영역 인덱스 |
| [business/AI데이터플랫폼.md](./business/AI데이터플랫폼.md) | Tailored AX — AI 혁신 플랫폼 사업 |
| [business/데이터관리.md](./business/데이터관리.md) | Data Management — 데이터 관리 사업 |

### 🤖 데이터버틀러 AI 기능
> **데이터버틀러**는 위세아이텍 AI 기능 전체를 통칭하는 브랜딩 명칭입니다.

| 파일 | 설명 |
|------|------|
| [databutler/README.md](./databutler/README.md) | 데이터버틀러 개요 및 사업 영역별 AI 기능 인덱스 |
| [databutler/META_AI기능.md](./databutler/META_AI기능.md) | WiseMeta — 표준용어 AI 추천 상세 |
| [databutler/DQ_AI기능.md](./databutler/DQ_AI기능.md) | WiseDQ — 검증룰 자동 매핑·간편 진단 등 상세 |

---

## LLM 연동 방식

`ml-server/app.py`의 `_load_company_profile()` 함수가 `company_profile.json`을 읽어  
PPT·제안서 생성 프롬프트 상단에 자동 주입합니다.

```
[자사 정보 — 제안서 작성 시 반드시 반영]
회사명: 위세아이텍 (WISEITECH) | AI&빅데이터 전 제품 국내 시장 점유율 1위
주요 사업: Tailored AX (WiseAIOps, WiseProphet, WiseIntelligence)
         Data Management (WiseDQ, WiseMeta, ASTA, Code Insure)
데이터버틀러 AI: 검증룰 자동 매핑, 표준용어 추천, 간편 진단 등
생성형 보고서: WiseIntelligence LLM 기반 정기 보고서 자동 생성
인증: GS인증 1등급 (WiseIntelligence), 클라우드서비스 적격 평가
납품 실적: 공공·금융 약 200여 개 시스템
```

---

## 업데이트 가이드

| 상황 | 수정 대상 |
|------|-----------|
| 제품·실적·인증 변경 | `company_profile.json` + 해당 `products/(제품명)/README.md` |
| 새 제품 추가 | `products/_양식/` 폴더 복사 → 작성 → `products/README.md` 목록 추가 ([작성가이드](./products/작성가이드.md)) |
| 새 사업 영역 추가 | `business/_양식.md` 복사 → 작성 → `business/README.md` 목록 추가 |
| 데이터버틀러 AI 기능 추가 | `databutler/` 에 새 파일 추가 → `databutler/README.md` 업데이트 |
| PPT 디자인 변경 | `design/design.md` + `ml-server/ppt_claude_design.py` 함께 수정 |
