# 📚 Publish or Perish

> Econophysics × Neuroscience — 두 명의 통계물리학 대학원생이 함께 공부하는 교재 중심 스터디

연구 적용 프로젝트가 아닌 **이론과 수학적 기초를 깊이 공부하는 세미나**입니다. 기간이나 주차별 진도는 정하지 않고, 가능한 한 빠르게 진행합니다.

## 운영 방식

- **기간 및 빈도:** 종료 기한 없음. 필요하면 일주일에 여러 번 진행
- **발표:** 한 번의 미팅(Session)에서 **두 사람이 각자 한 번씩 발표**합니다. 한 사람이 발표하는 동안 다른 사람은 질문하고 토론합니다.
- **분량:** **각 발표자별로** 교재 1~2개 Chapter를 목표로 하되, 내용이 길거나 어려우면 Section 단위로 조정합니다.
- **방식:** 핵심 개념, 정리와 증명, 예제, 토론을 중심으로 진행
- **기록:** 세션 디렉토리의 `README.md`에는 미팅 정보·발표 링크·공동 토론을, 두 발표 파일에는 각자의 발표 내용과 증명을 기록합니다.
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

**Session은 두 사람이 함께 진행하는 미팅 한 번**, **Presentation은 그 안에서 각 사람이 맡는 발표 한 번**을 뜻합니다.

1. 실제 미팅을 준비할 때 과목 폴더에 `Session-XX/`를 만듭니다. (과목별로 번호를 매김)
2. [SESSION_TEMPLATE.md](./SESSION_TEMPLATE.md)를 `Session-XX/README.md`로 복사해 **미팅 개요와 두 발표 링크**를 작성합니다.
3. [PRESENTATION_TEMPLATE.md](./PRESENTATION_TEMPLATE.md)를 각각 `01-Presenter-A.md`, `02-Presenter-B.md`로 복사합니다. 발표자는 **각자 자기 파일**에서 Markdown과 LaTeX 수식으로 내용을 정리하고 그 문서로 발표합니다.
4. 미팅이 끝나면 `Session-XX/README.md`의 **Discussion / Open Questions**에 함께 논의한 사항을 기록합니다.
5. 과목별 `README.md`의 Sessions 목록에 해당 미팅 링크(`./Session-XX/`)를 추가합니다.

발표자 A·B는 파일 구분용으로 사용한 임시 이름입니다. 실제 이름이나 GitHub 아이디에 맞춰 변경해도 됩니다. 순서나 학습 기간은 고정하지 않으며, 발표 분량은 **각자 1~2 Chapter를 기본으로 유연하게** 조절합니다.

```text
Publish-or-Perish/
├── README.md                      # 스터디 전체 소개
├── SESSION_TEMPLATE.md            # 미팅 개요 템플릿
├── PRESENTATION_TEMPLATE.md       # 개인 발표 문서 템플릿
├── 01. Linear Algebra/
│   ├── README.md                  # 과목 개요와 미팅 목록
│   └── Session-01/
│       ├── README.md              # 미팅 날짜·발표 링크·공동 토론
│       ├── 01-Presenter-A.md       # 첫 번째 발표자 원고
│       └── 02-Presenter-B.md       # 두 번째 발표자 원고
├── 02. Stochastic Processes/
│   └── README.md
├── 03. Nonlinear Dynamics/
│   └── README.md
├── 04. Complexity & Criticality/
│   └── README.md
└── 05. Information Theory & Inference/
    └── README.md
```

위 구조에서는 진행 예정인 첫 미팅만 미리 만들어두었고, 다음 세션 폴더는 실제 준비할 때 생성합니다.

## 자료와 링크 관리

- **정의·정리·증명:** 두 사람의 발표 파일(`01-Presenter-A.md`, `02-Presenter-B.md`)에 Markdown과 LaTeX로 직접 작성합니다.
- **이미지 및 직접 만든 그래프:** 필요할 때만 해당 `Session-XX/attachments/`를 만듭니다. 공통으로 사용할 이미지도 같은 미팅 폴더에 둘 수 있습니다.
- **외부 논문·강의·교재·영상:** 원본 파일 대신 가능한 한 DOI, arXiv, 저자·출판사·공식 사이트의 링크를 사용합니다.
- **공통 참고 자료:** 여러 미팅에서 공유할 자료 링크는 과목별 `README.md`의 `References`에 모읍니다.
- **현재 설정:** `.gitignore`는 PDF 등 일부 교재·문서 확장자를 기본적으로 제외하므로, 합법적으로 공유할 파일을 추가할 때도 규칙을 확인합니다.

발표 파일에서 이미지와 논문을 연결하는 예시입니다.

```markdown
![직접 그린 그림](attachments/example.png)
[참고 논문](https://doi.org/...)
```

수식은 GitHub Markdown의 `$...$` 및 `$$...$$` 문법을 사용합니다. 별도의 슬라이드 파일은 필요하지 않습니다.

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
