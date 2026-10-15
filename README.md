# 📚 Publish or Perish Study Group

> 연구 역량 강화 및 이론적 기반 확립을 위한 집중 스터디 저장소입니다.

---

## 🎯 Curriculum Overview (총 15주)

| 순서 | 주제 | 기간 | 주교재 | 핵심 토픽 | 디렉토리 |
| :---: | :--- | :---: | :--- | :--- | :--- |
| **01** | **Linear Algebra** | 4주 | Friedberg | 벡터공간, 선형변환, 스펙트럼 분해 | [`01. Linear Algebra`](./01.%20Linear%20Algebra/) |
| **02** | **Stochastic Processes** | 3주 | Gardiner | Markov process, Langevin, Fokker–Planck | [`02. Stochastic Processes`](./02.%20Stochastic%20Processes/) |
| **03** | **Nonlinear Dynamics** | 2주 | Strogatz | Stability, bifurcation, chaos | [`03. Nonlinear Dynamics`](./03.%20Nonlinear%20Dynamics/) |
| **04** | **Complexity & Criticality** | 4주 | Christensen | Scaling, universality, SOC | [`04. Complexity & Criticality`](./04.%20Complexity%20%26%20Criticality/) |
| **05** | **Information Theory & Inference** | 2주 | Cover / Efron | Information measures, statistical inference | [`05. Information Theory & Inference`](./05.%20Information%20Theory%20%26%20Inference/) |

---

## 📂 Repository Structure

```text
Publish or Perish/
├── 01. Linear Algebra/
│   ├── attachments/
│   ├── README.md
│   ├── Week-01.md ~ Week-04.md
├── 02. Stochastic Processes/
│   ├── attachments/
│   ├── README.md
│   ├── Week-01.md ~ Week-03.md
├── 03. Nonlinear Dynamics/
│   ├── attachments/
│   ├── README.md
│   ├── Week-01.md ~ Week-02.md
├── 04. Complexity & Criticality/
│   ├── attachments/
│   ├── README.md
│   ├── Week-01.md ~ Week-04.md
├── 05. Information Theory & Inference/
│   ├── attachments/
│   ├── README.md
│   ├── Week-01.md ~ Week-02.md
├── .gitignore
└── README.md
```

---

## 🤝 Collaboration & Git Guidelines

1. **작업 시작 전 항상 최신화**
   ```bash
   git pull origin main
   ```
2. **새로운 노트 작성 / 수정 후 커밋 & 푸시**
   ```bash
   git add .
   git commit -m "docs: [주제명] Week-XX 노트 추가/수정"
   git push origin main
   ```
3. **이미지 첨부 규칙**
   * 이미지는 반드시 해당 주제 폴더 내 `attachments/` 에 저장합니다.
   * GitHub 웹 호환을 위해 마크다운 표준 상대경로 문법을 사용합니다:
     ```markdown
     ![설명](attachments/image-name.png)
     ```
4. **수식 표기**
   * 인라인 수식: `$f(x) = ax + b$`
   * 블록 수식:
     ```markdown
     $$
     \frac{dx}{dt} = \sigma (y - x)
     $$
     ```
