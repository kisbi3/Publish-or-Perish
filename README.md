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

1. 해당 주제 폴더에 `Session-01.md`, `Session-02.md`처럼 **실제 진행한 세션별로** 파일을 만듭니다.
2. [SESSION_TEMPLATE.md](./SESSION_TEMPLATE.md)를 복사하고 발표자, 날짜, Chapter/Section 등 실제 내용을 채웁니다.
3. 해당 과목 `README.md`의 세션 목록에 링크를 추가합니다.
4. 세션 번호는 **각 과목 폴더 내에서** 따로 부여합니다. (주차나 날짜와 무관)

첫 번째 Linear Algebra 세션용 `Session-01.md`만 미리 만들어 두었습니다. 다른 세션 파일은 미리 만들지 않습니다.

```text
Publish-or-Perish/
├── README.md
├── SESSION_TEMPLATE.md
├── 01. Linear Algebra/
│   ├── README.md
│   └── Session-01.md
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

이미지가 필요하다면 해당 주제 폴더 아래에 `attachments/`를 만들고, 상대 경로로 연결합니다.

```markdown
![그림 설명](attachments/figure.png)
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
