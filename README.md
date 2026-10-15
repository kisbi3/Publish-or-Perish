# 📚 Publish or Perish

> Econophysics × Neuroscience — 두 명의 통계물리학 대학원생이 함께 공부하는 교재 중심 스터디

연구 적용 프로젝트가 아닌 **이론과 수학적 기초를 깊이 공부하는 세미나**입니다. 기간이나 주차별 진도는 정하지 않고, 가능한 한 빠르게 진행합니다.

## 운영 방식

- **기간 및 빈도:** 종료 기한 없음. 필요하면 일주일에 여러 번 진행
- **발표:** 매 세션 한 명이 맡고, 발표자는 두 사람이 번갈아 맡는 것을 기본으로 함
- **분량:** 한 번에 교재 **1~2개 Chapter**를 목표로 하되, 내용이 길거나 어려우면 Section 단위로 조정
- **방식:** 핵심 개념, 정리와 증명, 예제, 토론을 중심으로 진행
- **기록:** 세션이 끝난 뒤 날짜·발표자·진도·핵심 내용·미해결 질문을 기록
- **별도 연구 프로젝트:** 없음. 실습이나 연습문제는 필요에 따라 자율적으로 진행

## Curriculum

과목의 **학습 순서**만 정해져 있으며, 아래 표는 기간이나 세션 수를 의미하지 않습니다.

| 순서 | 주제 | 주교재 | 핵심 토픽 | 자료 |
| :---: | :--- | :--- | :--- | :--- |
| 01 | Linear Algebra | Friedberg | Vector spaces, linear maps, eigenvalues, spectral theory, Jordan form | [바로가기](./01.%20Linear%20Algebra/README.md) |
| 02 | Stochastic Processes | Gardiner | Markov processes, master equation, Langevin, Fokker–Planck | [바로가기](./02.%20Stochastic%20Processes/README.md) |
| 03 | Nonlinear Dynamics | Strogatz | Stability, bifurcation, chaos | [바로가기](./03.%20Nonlinear%20Dynamics/README.md) |
| 04 | Complexity & Criticality | Christensen | Scaling, universality, percolation, SOC | [바로가기](./04.%20Complexity%20%26%20Criticality/README.md) |
| 05 | Information Theory & Inference | Cover / Efron | Entropy, mutual information, statistical inference | [바로가기](./05.%20Information%20Theory%20%26%20Inference/README.md) |

## 세션 기록 방법

모든 발표는 **Markdown 문서 하나**로 준비하고 진행합니다. 별도의 슬라이드나 PDF 발표 자료는 필수가 아닙니다.

1. 주제 폴더 안에 `Session-01/`, `Session-02/`처럼 **세션별 디렉토리**를 만듭니다.
2. 그 안에 `README.md`를 작성합니다. [SESSION_TEMPLATE.md](./SESSION_TEMPLATE.md)를 복사해 시작하면 편리합니다.
3. 날짜·발표자·교재 Chapter/Section과 개념·증명·토론·미해결 질문을 기록합니다. 고정된 진도나 일정은 없습니다.
4. 과목별 `README.md`에 해당 세션의 디렉토리 링크(`./Session-XX/`)를 추가합니다.
5. 세션 번호는 **각 과목별**로 부여하며, 주차 및 날짜와는 무관합니다.

첫 Linear Algebra 세션만 `Session-01/README.md`로 미리 준비되어 있습니다. 새 세션과 관련 폴더는 필요할 때 추가합니다.

```text
Publish-or-Perish/
├── README.md
├── SESSION_TEMPLATE.md
├── 01. Linear Algebra/
│   ├── README.md                   # 과목 소개 · 세션 목차 · 공통 참고 링크
│   ├── Session-01/
│   │   └── README.md               # 발표 원고 및 스터디 기록
│   └── Session-02/                 # 실제 다음 세션을 진행할 때 생성
│       ├── README.md
│       └── attachments/            # 필요한 경우에만 생성
│           └── example.png
├── 02. Stochastic Processes/
│   └── README.md
├── 03. Nonlinear Dynamics/
│   └── README.md
├── 04. Complexity & Criticality/
│   └── README.md
├── 05. Information Theory & Inference/
│   └── README.md
└── .gitignore
```

> 위 트리의 `Session-02/`와 `attachments/`는 **구조 예시**입니다. 실제 저장소에는 필요한 시점에 생성합니다.

## 자료와 링크 관리

- **정의·정리·증명:** `Session-XX/README.md`에 Markdown 및 LaTeX로 직접 작성합니다.
- **수식 그림·직접 만든 그래프·필기 이미지:** 세션에 파일이 필요한 경우에만 `Session-XX/attachments/`를 만듭니다. 미리 빈 디렉토리를 만들지 않습니다.
- **외부 논문·강의·교재·영상:** 가능하면 DOI, arXiv, 저자·출판사·공식 강의 페이지의 **링크**로 남깁니다. 저작권이 있는 교재 파일은 업로드하지 않습니다.
- **공통 자료:** 여러 세션에서 반복 사용하는 참고 링크는 과목별 `README.md`의 `References`에 모읍니다.
- **현재 설정:** `.gitignore`는 PDF/DJVU/EPUB 파일의 기본 업로드를 제외합니다. 별도 합법적 자료의 PDF가 필요하면 이 규칙을 검토하세요.

예를 들어 세션 디렉토리의 `README.md` 안에서는 다음처럼 그림과 외부 자료를 연결할 수 있습니다.

```markdown
![직접 제작한 그림](attachments/figure.png)
[참고 논문](https://doi.org/...)
```

수식은 GitHub Markdown의 `$...$` 및 `$$...$$` 문법을 사용합니다.

## 공동 작업

작업 전에 최신 내용을 받아옵니다.

```bash
git pull origin main
```

변경 후 커밋하고 푸시합니다.

```bash
git add .
git commit -m "docs: add linear algebra session notes"
git push origin main
```

같은 파일을 동시에 수정할 때는 Git 충돌에 주의하고, 큰 변경은 별도 브랜치와 Pull Request를 사용할 수 있습니다.

**권한:** Public 저장소이므로 누구나 열람할 수 있지만, 원본에 직접 Push하려면 소유자 또는 쓰기 권한을 받은 Collaborator여야 합니다. **URL만 공유해도 수정 권한이 생기는 것은 아닙니다.** 협업자는 저장소 **Settings → Collaborators → Add people**에서 GitHub 계정으로 초대해야 합니다.

> 저작권이 있는 교재 PDF는 Public 저장소에 올리지 말고 출판사나 저자가 공개한 자료를 링크하세요.
