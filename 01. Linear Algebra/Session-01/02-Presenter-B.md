
# Chap.2 선형변환과 행렬

여러 선형 시스템을 다룰 때, 선형변환은 입력과 출력의 관계를 기술하는 데 유용하다. 이 장에서는 선형변환의 구조를 분석하고, 유한차원에서 이를 행렬로 표현하여 합성·역변환·기저변환을 계산하는 방법을 다룬다.

이하 벡터공간은 같은 체 $\mathbb F$ 위에 두며, $T,U$ 등은 별도 언급이 없으면 선형변환으로 가정한다.

---

# 2.1 선형변환, 영공간, 상공간

> Friedberg, Insel & Spence, *Linear Algebra*, 5판, §2.1.

## 선형변환의 정의

같은 체 $\mathbb F$ 위의 벡터공간 $V,W$에 대해 사상 $T:V\to W$가

$$
T(ax+by)=aT(x)+bT(y)
\quad(\forall x,y\in V,\ \forall a,b\in\mathbb F)
$$

를 만족하면 **선형변환(linear transformation)** 이라 한다.

## 영공간과 상공간 — 정리 2.1, 2.2

$T:V\to W$에 대해

$$
N(T):=\{x\in V:T(x)=0_W\},\qquad
R(T):=\{y\in W:\exists x\in V,\ T(x)=y\}.
$$

영공간은 $0$으로 보내지는 입력들, 상공간은 가능한 출력들의 공간이다. 정리 2.1에 의해 $N(T)\leq V$, $R(T)\leq W$이다. $\beta=(v_1,\ldots,v_n)$이 $V$의 기저이면 정리 2.2에 의해

$$
R(T)=\mathrm{span}\,\lbrace T(v_1),\ldots,T(v_n)\rbrace.
$$

### 예제 8. 항등변환과 영변환

항등변환은 $I_V:V\to V$, $I_V(x):=x$이고, 영변환은 $T_0:V\to W$, $T_0(x):=0_W$이다 $(\forall x\in V)$.

| 변환 | 영공간 | 상공간 |
|---|---|---|
| $I_V$ | $\{0_V\}$ | $V$ |
| $T_0$ | $V$ | $\{0_W\}$ |

## Nullity, rank와 차원정리 — 정리 2.3

유한차원 $V$에 대해

$$
\mathrm{nullity}(T):=\dim(N(T)),\qquad
\mathrm{rank}(T):=\dim(R(T)),
$$

이며, 차원정리는

$$
\boxed{\dim(N(T))+\dim(R(T))=\dim(V)}
$$

이다.

**증명.** $\dim(V)=n$, $\dim(N(T))=k$라 하자. $N(T)$의 기저 $(v_1,\ldots,v_k)$를 $V$의 기저 $(v_1,\ldots,v_n)$으로 확장하면

$$
R(T)=\mathrm{span}\,\lbrace T(v_{k+1}),\ldots,T(v_n)\rbrace.
$$

$\sum_{i=k+1}^{n}a_iT(v_i)=0$이면 $\sum_{i=k+1}^{n}a_iv_i\in N(T)$이므로, 전체 기저의 선형독립성에서 모든 $a_i=0$을 얻는다. 따라서 위 생성집합은 기저이고 $\dim(R(T))=n-k$이다. $\square$

## 단사·전사와 판정 — 정리 2.4, 2.5

$T:V\to W$에 대해 **단사**와 **전사**는 각각

$$
\begin{aligned}
&\forall x,y\in V:\quad T(x)=T(y)\Longrightarrow x=y,\\
&\forall w\in W,\quad\exists v\in V:\quad T(v)=w
\end{aligned}
$$

를 뜻한다. 정리 2.4와 상공간의 정의에 의해

$$
T\text{가 단사}\Longleftrightarrow N(T)=\{0_V\},\qquad
T\text{가 전사}\Longleftrightarrow R(T)=W.
$$

특히 $\dim(V)=\dim(W)=n<\infty$이면 정리 2.5에 의해

$$
\boxed{T\text{가 단사}\Longleftrightarrow T\text{가 전사}
\Longleftrightarrow\mathrm{rank}(T)=n}.
$$

## 정리 2.6. 기저 위의 값으로 변환을 결정한다

$\beta=(v_1,\ldots,v_n)$이 $V$의 기저이면, $\forall(w_1,\ldots,w_n)\in W^n$에 대해

$$
T(v_i)=w_i\quad(\forall i=1,\ldots,n)
$$

를 만족하는 선형변환 $T:V\to W$가 유일하게 존재한다.

**증명.** 기저에 대한 좌표표현의 유일성을 이용하여

$$
T\left(\sum_{i=1}^{n}a_iv_i\right):=\sum_{i=1}^{n}a_iw_i
\quad(\forall(a_1,\ldots,a_n)\in\mathbb F^n)
$$

로 정의한다. 같은 기저값을 갖는 변환은 모든 벡터에서 이 식을 따라야 하므로 유일하다. $\square$

즉, **선형변환 전체는 기저벡터의 상 $n$개로 결정된다.** 공역도 $m$차원이면 이 상들을 좌표로 기록한 $mn$개의 계수가 행렬 표현을 이룬다.

## 연습문제 2.1.1: 구조 확인 (e)–(h)

같은 체 $\mathbb F$ 위의 유한차원 공간 $V,W$에 대해 다음 명제의 참·거짓을 판별하라.

**(e)** $T$가 선형이면 $\mathrm{nullity}(T)+\mathrm{rank}(T)=\dim(W)$이다.

**F :** 차원정리의 우변은 $\dim(V)$이다.

**(f)** $T$가 선형이면 $V$의 선형독립인 부분집합의 상은 $W$의 선형독립인 부분집합이다.

**F :** 영변환 $T_0:\mathbb R\to\mathbb R$은 선형독립인 $\{1\}$을 선형종속인 $\{0\}$으로 보낸다.

**(g)** $T,U:V\to W$가 선형이고 $V$의 한 기저 위에서 일치하면 $T=U$이다.

**T :** 정리 2.6의 유일성에 의해 기저 위의 값이 같으면 변환 전체가 같다.

**(h)** $x_1,x_2\in V$, $y_1,y_2\in W$를 임의로 주면, $T(x_1)=y_1$, $T(x_2)=y_2$를 만족하는 선형변환 $T:V\to W$가 존재한다.

**F :** $V=W=\mathbb R$에서 $T(1)=1$, $T(2)=0$을 요구하면 선형성에 따른 $T(2)=2T(1)=2$와 모순이다.

## $T$-불변부분공간과 제한변환

$T:V\to V$에 대해 $W\leq V$가

$$
T(W)\leq W
\quad\Longleftrightarrow\quad
\forall w\in W,\ T(w)\in W
$$

를 만족하면 **$T$-불변부분공간**이라 한다. 이때 **제한변환(restriction)**

$$
T_W:=T|_W:W\to W,\qquad
T_W(w):=T(w)\quad(\forall w\in W)
$$

으로 $T$의 작용을 $W$ 위에서 따로 분석할 수 있다.

$\{0_V\}$, $V$, $N(T)$, $R(T)$는 모두 $T$-불변부분공간이다(연습문제 29). 제한변환의 영공간과 상공간은 다음과 같다(연습문제 33).

$$
N(T_W)=N(T)\cap W,
\qquad R(T_W)=T(W).
$$

---

# 2.2, 2.3

> Friedberg, Insel & Spence, *Linear Algebra*, 5판, §§2.2–2.3.

## 순서기저와 좌표벡터

**순서기저(ordered basis)**는 순서를 지정한 기저 $\beta=(v_1,\ldots,v_n)$이다. 이 기저에 대해

$$
\forall x\in V,\quad\exists!\,(a_1,\ldots,a_n)\in\mathbb F^n:
\quad x=\sum_{i=1}^{n}a_iv_i.
$$

이때 **좌표벡터**는 $[x]_\beta:=(a_1,\ldots,a_n)^{\mathsf T}$로 정의한다.

## 행렬 표현 — 정리 2.14

$\dim(V)=n$, $\dim(W)=m$이고 순서기저를 각각 $\beta=(v_1,\ldots,v_n)$, $\gamma=(w_1,\ldots,w_m)$으로 고정하자. $T:V\to W$의 **행렬 표현**은

$$
[T]_\beta^\gamma:=
\begin{pmatrix}
[T(v_1)]_\gamma&\cdots&[T(v_n)]_\gamma
\end{pmatrix}
\in M_{m\times n}(\mathbb F).
$$

**$j$번째 열은 입력 기저벡터 $v_j$의 상을 출력 기저 $\gamma$로 나타낸 좌표벡터**다. 정리 2.14는 이 정의를 임의의 입력에 대한 계산으로 연결한다.

$$
\boxed{[T(x)]_\gamma=[T]_\beta^\gamma[x]_\beta}
\qquad(\forall x\in V).
$$

행렬은 입력의 $\beta$-좌표를 출력의 $\gamma$-좌표로 보낸다. 기저를 고정하면 $T$와 행렬은 일대일로 대응하며, $V=W$, $\beta=\gamma$이면 $[T]_\beta$로 줄여 쓴다.

## 선형변환 공간과 행렬 연산

$$
\mathcal L(V,W):=\{T:V\to W\mid T\text{는 선형}\}
$$

는 함수의 점별 덧셈과 스칼라곱을 갖는 벡터공간이다. $V=W$이면 $\mathcal L(V)$로 쓴다. 행렬 표현은 이 연산을 보존한다.

$$
[aT+bU]_\beta^\gamma
=a[T]_\beta^\gamma+b[U]_\beta^\gamma
\quad(\forall T,U\in\mathcal L(V,W),\ \forall a,b\in\mathbb F).
$$

유한차원 공간 사이의 $T:V\to W$, $U:W\to Z$와 각 공간의 순서기저 $\beta,\gamma,\delta$에 대해, **합성은 행렬곱에 대응한다**(정리 2.11).

$$
\boxed{[UT]_\beta^\delta=[U]_\gamma^\delta[T]_\beta^\gamma}.
$$

오른쪽 변환 $T$를 먼저 적용하는 순서가 행렬곱에도 그대로 반영된다.

## 좌측 곱 변환 — 정리 2.15

$A\in M_{m\times n}(\mathbb F)$의 **좌측 곱 변환**은

$$
L_A:\mathbb F^n\to\mathbb F^m,\qquad
L_A(x):=Ax\quad(\forall x\in\mathbb F^n)
$$

이다. 표준 순서기저에서 $L_A$의 행렬 표현은 $A$이며, 모든 $T:\mathbb F^n\to\mathbb F^m$는 유일한 $A$에 대해 $T=L_A$로 표현된다. 따라서 $L_A=L_B\Longleftrightarrow A=B$이고, 크기가 맞는 행렬들과 $\forall c\in\mathbb F$에 대해

$$
\begin{aligned}
L_{A+B}&=L_A+L_B,& L_{cA}&=cL_A,\\
L_{AE}&=L_A L_E,& L_{I_n}&=I_{\mathbb F^n}.
\end{aligned}
$$

## 결합행렬 (Incidence matrix)

> 교재 §2.3, pp. 94–96; 연습문제 20, p. 99.

$n$개의 대상 사이의 관계를 $i\to j$로 나타내자. 이 관계의 **결합행렬**은

$$
\forall i,j\in\{1,\ldots,n\},\qquad
A_{ij}:=
\begin{cases}
1,&i\to j,\\
0,&\text{그 외}
\end{cases}
$$

로 정의되는 $0$–$1$ 행렬이다. 이 절에서는 자기 자신과의 관계를 제외하여 $A_{ii}=0$ $(\forall i)$으로 둔다. 행은 출발점, 열은 도착점에 해당한다.

### 행렬 거듭제곱의 의미

$$
(A^2)_{ij}=\sum_{k=1}^{n}A_{ik}A_{kj}
$$

에서 각 항은 $i\to k\to j$가 존재할 때 $1$이다. 따라서 $(A^2)_{ij}$는 $i$에서 $j$로 가는 **2단계 경로의 수**다. 같은 논리로 $(A^r)_{ij}$는 $r$단계 경로의 수이며, 여기서 경로는 정점의 반복을 허용하는 보행(walk)을 뜻한다.

따라서

$$
\left(A+A^2+\cdots+A^r\right)_{ij}
$$

는 $i$에서 $j$로 가는 $1$단계 이상 $r$단계 이하 경로의 총수다. 이 값이 양수인 것은 $r$단계 이내에 도달할 수 있다는 뜻이다.

### Clique와 연습문제 2.3.20

교재에서 **clique**는 서로 다른 모든 두 구성원이 양방향으로 연결된, 원소가 $3$개 이상인 **포함관계상 극대인 집합**이다. 즉, 이 성질을 유지하면서 구성원을 더 추가할 수 없다.

양방향 관계만 남긴 행렬 $B$를

$$
\forall i,j,\qquad
B_{ij}:=A_{ij}A_{ji}
=\begin{cases}
1,&i\to j\text{이고 }j\to i,\\
0,&\text{그 외}
\end{cases}
$$

로 정의하면 $B^{\mathsf T}=B$, $B_{ii}=0$이다.

**문제.** $i$가 어떤 clique에 속할 필요충분조건이 $(B^3)_{ii}>0$임을 보여라.

**풀이.**

$$
(B^3)_{ii}=\sum_{j,k=1}^{n}B_{ij}B_{jk}B_{ki}>0
\quad\Longleftrightarrow\quad
\exists j,k:\ B_{ij}=B_{jk}=B_{ki}=1.
$$

$B_{ii}=0$이므로 $i,j,k$는 서로 다르고, $B$가 대칭이므로 이들은 모두 양방향으로 연결된다. 대상의 수가 유한하므로 이 세 원소의 집합을 극대인 집합까지 확장하면 $i$를 포함하는 clique를 얻는다. 반대로 $i$가 clique에 속하면 그 안에서 다른 두 원소 $j,k$를 택할 수 있고, 위 합에 $1$인 항이 존재한다. $\square$

### 지배관계 (Dominance relation)

서로 다른 두 대상 사이에 정확히 한 방향의 관계만 존재할 때 **지배관계** 라 한다. 즉,

$$
A_{ii}=0\quad(\forall i),\qquad
A_{ij}+A_{ji}=1\quad(\forall i\ne j).
$$

$A_{ij}=1$이면 $i$가 $j$를 직접 지배한다고 한다. 지배관계는 추이적일 필요가 없다.

$S:=A+A^2$로 두면 $S_{ij}>0$은 $i$가 $j$를 직접 또는 한 대상을 거쳐 지배한다는 뜻이다. 지배관계에서는 항상

$$
\exists p,\ \forall j\ne p:\ S_{pj}>0,
\qquad
\exists q,\ \forall i\ne q:\ S_{iq}>0.
$$

즉, **모든 다른 대상을 2단계 이내에 지배하는 대상**과 **모든 다른 대상에게 2단계 이내에 지배되는 대상**이 각각 존재한다.

**증명.** 직접 지배하는 대상의 수 $d_i:=\sum_j A_{ij}$가 최대인 $p$를 택하자. $p$에서 2단계 이내에 도달할 수 없는 $j$가 있다면 $j\to p$이다. 또한 $p\to k$인 모든 $k$에 대해 $j\to k$여야 한다. 그렇지 않으면 $p\to k\to j$이기 때문이다. 따라서 $d_j\ge d_p+1$이 되어 최대성에 모순이다. 열에 대한 주장은 지배관계의 방향을 모두 뒤집은 $A^{\mathsf T}$에 같은 논증을 적용하면 된다. $\square$

---

# 2.4 가역성과 동형사상

> Friedberg, Insel & Spence, *Linear Algebra*, 5판, §2.4, pp. 100–106.

## 역함수와 가역성

$T:V\to W$에 대해

$$
\exists U:W\to V:\qquad UT=I_V,\qquad TU=I_W
$$

이면 $T$는 **가역**이며, 유일한 역함수 $U$를 $T^{-1}$로 쓴다. 가역성은 단사이면서 전사인 것과 동치다.

1. 합성이 정의되는 가역함수에 대해 $(TU)^{-1}=U^{-1}T^{-1}$.
2. $(T^{-1})^{-1}=T$.
3. $\dim(V)=\dim(W)<\infty$이면 $T$가 가역일 필요충분조건은 $\mathrm{rank}(T)=\dim(V)$이다.

**정리 2.17.** 가역인 선형변환의 역함수도 선형이다. 또한 $V,W$ 중 하나가 유한차원이면 다른 하나도 유한차원이고 $\dim(V)=\dim(W)$이다(따름정리).

## 역행렬과 행렬 표현 — 정리 2.18

$A\in M_{n\times n}(\mathbb F)$에 대해 $AB=BA=I_n$인 $B\in M_{n\times n}(\mathbb F)$가 존재하면 $(\exists B)$, $A$는 **가역행렬**이고 이 유일한 $B$를 $A^{-1}$로 쓴다.

유한차원 $V,W$의 기저 $\beta,\gamma$에 대해

$$
T\text{가 가역}\Longleftrightarrow[T]_\beta^\gamma\text{가 가역},
\qquad
\boxed{[T^{-1}]_\gamma^\beta=\left([T]_\beta^\gamma\right)^{-1}}.
$$

역변환은 $W\to V$이므로 입력과 출력의 기저 순서도 바뀐다.

## 동형사상과 차원 — 정리 2.19

가역인 선형변환을 **동형사상(isomorphism)**이라 하며,

$$
V\cong W
\quad\Longleftrightarrow\quad
\exists T\in\mathcal L(V,W):\ T\text{는 가역}
$$

이면 두 공간이 **동형**이라 한다. 같은 체 위의 유한차원 공간에 대해

$$
\boxed{V\cong W\Longleftrightarrow\dim(V)=\dim(W)}.
$$

특히 $\dim(V)=n$일 필요충분조건은 $V\cong\mathbb F^n$이다(따름정리). 동형은 벡터의 구체적인 형태와 관계없이 같은 선형구조를 갖는다는 뜻이다.

### 예제 4. $\mathbb F^2$와 $P_1(\mathbb F)$

다음 변환이 동형사상임을 보여라.

$$
T:\mathbb F^2\to P_1(\mathbb F),\qquad
T(a_1,a_2):=a_1+a_2x
\quad(\forall(a_1,a_2)\in\mathbb F^2).
$$

**풀이.** 다항식의 계수가 유일하므로 역함수는

$$
T^{-1}(a_1+a_2x)=(a_1,a_2)
$$

로 주어진다. 따라서 $T$는 동형사상이며 $\mathbb F^2\cong P_1(\mathbb F)$이다. $\square$

### 예제 5. $P_3(\mathbb R)$과 $M_{2\times2}(\mathbb R)$

다음 변환이 동형사상임을 보여라.

$$
T:P_3(\mathbb R)\to M_{2\times2}(\mathbb R),\qquad
T(f):=
\begin{pmatrix}
f(1)&f(2)\\
f(3)&f(4)
\end{pmatrix}
\quad(\forall f\in P_3(\mathbb R)).
$$

**풀이.** $T(f)=O$이면 $f(1)=f(2)=f(3)=f(4)=0$이다. 차수가 $3$ 이하인 영이 아닌 다항식은 서로 다른 네 근을 가질 수 없으므로 $f=0$. 따라서 $N(T)=\{0\}$이고 $T$는 단사다. 또한

$$
\dim(P_3(\mathbb R))=4=\dim(M_{2\times2}(\mathbb R))
$$

이므로 정리 2.5에 의해 전사이기도 하다. 따라서 $T$는 동형사상이며 $P_3(\mathbb R)\cong M_{2\times2}(\mathbb R)$이다. $\square$

## 선형변환 공간과 행렬 공간 — 정리 2.20

$\dim(V)=n$, $\dim(W)=m$이고 기저 $\beta,\gamma$를 고정하면

$$
\Phi_\beta^\gamma:\mathcal L(V,W)\to M_{m\times n}(\mathbb F),\qquad
\Phi_\beta^\gamma(T):=[T]_\beta^\gamma
\quad(\forall T\in\mathcal L(V,W))
$$

는 동형사상이다. 따라서 선형변환 공간은 유한차원이며

$$
\boxed{\dim(\mathcal L(V,W))=mn}
$$

이다(따름정리).

## 표준표현 — 정리 2.21

$n$차원 공간 $V$의 기저 $\beta$에 대한 **표준표현**

$$
\phi_\beta:V\to\mathbb F^n,\qquad
\phi_\beta(x):=[x]_\beta\quad(\forall x\in V)
$$

은 동형사상이다. $\dim(W)=m$이고 $A=[T]_\beta^\gamma$이면

$$
\boxed{\phi_\gamma T=L_A\phi_\beta}
\quad\Longleftrightarrow\quad
L_A=\phi_\gamma T\phi_\beta^{-1}.
$$

따라서 **추상적인 두 유한차원 벡터공간 사이의 선형연산은, 기저를 선택하면 $\mathbb F^n$과 $\mathbb F^m$ 사이의 행렬곱으로 완전히 표현된다.**

---

# 2.5 좌표변환 행렬

> Friedberg, Insel & Spence, *Linear Algebra*, 5판, §2.5, pp. 110–116; 연습문제 9, p. 118.

핵심은 **같은 선형변환을 다른 기저에서 어떻게 표현하고, 기저의 선택으로 그 표현을 어떻게 단순화하는가**이다.

## 좌표변환 행렬 — 정리 2.22

유한차원 벡터공간 $V$의 두 순서기저 $\beta,\beta'$에 대해

$$
Q:=[I_V]_{\beta'}^\beta
$$

는 가역이며, **$\beta'$-좌표를 $\beta$-좌표로 바꾸는 행렬**이다.

$$
\boxed{[v]_\beta=Q[v]_{\beta'}}
\qquad(\forall v\in V).
$$

$\beta'=(v'_1,\ldots,v'_n)$이면 $Q$의 $j$번째 열은 $[v'_j]_\beta$이다. 반대 방향의 좌표변환은 $Q^{-1}$로 주어진다.

## 행렬 표현의 변환 — 정리 2.23

선형연산자 $T:V\to V$의 두 기저에 대한 행렬 표현은

$$
\boxed{[T]_{\beta'}=Q^{-1}[T]_\beta Q}
$$

로 연결된다. 오른쪽부터 $\beta'$-좌표를 $\beta$-좌표로 바꾸고, $T$를 적용한 뒤, 다시 $\beta'$-좌표로 돌아오는 과정이다.

## 닮음 (Similarity)

$A,B\in M_{n\times n}(\mathbb F)$에 대해

$$
A\sim B
\quad\Longleftrightarrow\quad
\exists Q\in M_{n\times n}(\mathbb F):\quad
Q\text{는 가역이고 }B=Q^{-1}AQ
$$

이면 $A,B$가 **닮았다(similar)**고 한다. 닮은 행렬은 같은 선형연산자를 기저를 달리하여 표현한 것이다. 따라서 적절한 기저를 선택하면 같은 변환을 더 간단한 행렬로 다룰 수 있다.

닮음은 동치관계다.

### 연습문제 2.5.9

**문제.** 닮음관계가 $M_{n\times n}(\mathbb F)$ 위의 동치관계임을 보여라.

**풀이.** $\forall A,B,C\in M_{n\times n}(\mathbb F)$에 대해 다음 세 성질을 확인한다.

- **반사성:** $A=I_n^{-1}AI_n$이므로 $A\sim A$.
- **대칭성:** $B=Q^{-1}AQ$이면 $A=QBQ^{-1}=(Q^{-1})^{-1}B(Q^{-1})$이므로 $B\sim A$.
- **추이성:** $B=Q^{-1}AQ$, $C=R^{-1}BR$이면

$$
C=R^{-1}Q^{-1}AQR=(QR)^{-1}A(QR).
$$

$QR$도 가역이므로 $A\sim C$. 따라서 닮음은 동치관계다. $\square$

---

# 2.6 쌍대공간

> Friedberg, Insel & Spence, *Linear Algebra*, 5판, §2.6, pp. 119–122.

핵심은 **벡터에 스칼라를 대응시키는 선형함수들을 하나의 공간으로 다루고, 전치행렬을 이 공간 사이의 변환으로 해석하는 것**이다.

## 쌍대공간 (Dual space)

벡터공간 $V$에서 스칼라체 $\mathbb F$로 가는 선형함수 $f:V\to\mathbb F$를 **선형범함수(linear functional)**라 한다.

이러한 함수들로 이루어진 벡터공간

$$
\boxed{V^*:=\mathcal L(V,\mathbb F)}
$$

을 $V$의 **쌍대공간** 이라 한다. 덧셈과 스칼라곱은 함수값에 대해 점별로 정의한다. $V$가 유한차원이면

$$
\dim(V^*)=\dim(V).
$$

## 쌍대기저 (Dual basis) — 정리 2.24

$V$의 순서기저 $\beta=(v_1,\ldots,v_n)$에 대해

$$
f_i(v_j)=\delta_{ij}
\quad(\forall i,j\in\{1,\ldots,n\})
$$

를 만족하는 선형범함수들의 순서기저 $\beta^*=(f_1,\ldots,f_n)$를 **$\beta$의 쌍대기저**라 한다. 여기서 $\delta_{ij}$는 $i=j$이면 $1$, 그 외에는 $0$이다. 따라서

$$
x=\sum_{j=1}^{n}a_jv_j
\quad\Longrightarrow\quad
f_i(x)=a_i.
$$

즉, $f_i$는 $i$번째 좌표를 추출하는 함수다. 정리 2.24에 의해 $\beta^*$는 실제로 $V^*$의 기저이며,

$$
\boxed{f=\sum_{i=1}^{n}f(v_i)f_i}
\qquad(\forall f\in V^*).
$$

선형범함수의 쌍대기저에 대한 좌표는 원래 기저벡터들에서의 함수값이다.

## 쌍대변환 (Dual map)

선형변환 $T:V\to W$에 대해 **쌍대변환**을 교재의 표기에 따라

$$
T^t:W^*\to V^*,\qquad
T^t(g):=gT
\quad(\forall g\in W^*)
$$

로 정의한다. 즉,

$$
\bigl(T^t(g)\bigr)(v)=g(T(v))
\quad(\forall g\in W^*,\ \forall v\in V).
$$

$T^t$는 선형이며, 교재에서는 $T$의 **전치변환(transpose)** 이라 부른다. $W$ 위의 선형범함수 $g$를 $V$ 위의 선형범함수 $gT$로 옮기므로 변환의 방향이 반대가 된다.

## 쌍대변환과 전치행렬 — 정리 2.25

$\dim(V)=n$, $\dim(W)=m$이고 순서기저를 각각 $\beta,\gamma$, 그 쌍대기저를 $\beta^*,\gamma^*$라 하자. **쌍대변환 $T^t:W^*\to V^*$의 쌍대기저에 대한 행렬 표현은 원래 선형변환 $T:V\to W$의 행렬 표현을 전치한 행렬이다.** 즉, $A=[T]_\beta^\gamma$이면

$$
\boxed{[T^t]_{\gamma^*}^{\beta^*}
=\left([T]_\beta^\gamma\right)^{\mathsf T}
=A^{\mathsf T}}.
$$

$T$의 행렬 표현이 $m\times n$이면 $T^t$의 행렬 표현은 $n\times m$이다.

실제로 $\beta=(v_1,\ldots,v_n)$, $\gamma=(w_1,\ldots,w_m)$, $\gamma^*=(g_1,\ldots,g_m)$라 하면

$$
\bigl([T^t]_{\gamma^*}^{\beta^*}\bigr)_{ij}
=T^t(g_j)(v_i)
=g_j(T(v_i))
=A_{ji}.
$$

따라서 **전치행렬은 선형범함수를 반대 방향으로 옮기는 쌍대변환의 행렬 표현**이다. 이 관계는 내적 없이 정의되며, 복소수체에서도 켤레를 취하지 않는 전치에 해당한다.

---

# 2.7 상수계수 동차 선형미분방정식

> Friedberg, Insel & Spence, *Linear Algebra*, 5판, §2.7, pp. 128–140; 초기조건: 연습문제 15, p. 143.

핵심은 **미분방정식을 미분연산자의 영공간을 구하는 문제로 바꾸고, 해공간의 기저로 일반해를 표현하는 것**이다.

## 미분연산자와 해공간 — 정리 2.28, 2.32

상수 $a_0,\ldots,a_{n-1}\in\mathbb C$에 대해 $n$차 동차 방정식

$$
y^{(n)}+a_{n-1}y^{(n-1)}+\cdots+a_1y'+a_0y=0
$$

을 생각하자. $C^\infty(\mathbb R,\mathbb C)$에서 $D:=d/dt$로 두고, **보조다항식(auxiliary polynomial)**과 미분연산자를

$$
\begin{aligned}
p(\lambda)&:=\lambda^n+a_{n-1}\lambda^{n-1}+\cdots+a_1\lambda+a_0,\\
p(D)&:=D^n+a_{n-1}D^{n-1}+\cdots+a_1D+a_0I
\end{aligned}
$$

로 정의하면 방정식은 $p(D)y=0$이다. 따라서 **해공간**은

$$
\boxed{\mathcal S:=\{y\in C^\infty(\mathbb R,\mathbb C):p(D)y=0\}=N(p(D))}
$$

이고, 정리 2.32에 의해

$$
\boxed{\dim(\mathcal S)=n}.
$$

즉, 함수공간은 무한차원이지만 이 방정식의 해공간은 $n$차원이다. 서로 독립인 해 $n$개를 찾으면 모든 해를 그 선형결합으로 나타낼 수 있다.

## 보조다항식의 근과 해공간의 기저 — 정리 2.31–2.34

지수함수에 대해서는

$$
p(D)e^{ct}=p(c)e^{ct}\qquad(\forall c\in\mathbb C)
$$

이므로, $p(c)=0$이면 $e^{ct}$가 해다. 서로 다른 근에 대응하는 지수함수들은 선형독립이다(정리 2.33).

일반적으로 서로 다른 근 $c_1,\ldots,c_r$의 중복도를 $m_1,\ldots,m_r$라 하여

$$
p(\lambda)=\prod_{j=1}^{r}(\lambda-c_j)^{m_j},
\qquad \sum_{j=1}^{r}m_j=n
$$

으로 쓰면, 정리 2.34에 의해

$$
\boxed{\mathcal B=\{t^ke^{c_jt}:1\leq j\leq r,\ 0\leq k<m_j\}}
$$

가 $\mathcal S$의 기저다. 따라서 일반해는

$$
y(t)=\sum_{j=1}^{r}\sum_{k=0}^{m_j-1}b_{jk}t^ke^{c_jt},
\qquad b_{jk}\in\mathbb C
$$

이며 각 해의 계수들은 유일하다. **중복도 $m$인 근 하나는 $e^{ct},te^{ct},\ldots,t^{m-1}e^{ct}$라는 $m$개의 기저함수를 준다.**

## 실수해와 복소근

계수가 모두 실수이면 복소근은 켤레쌍 $a\pm ib$ $(b>0)$으로 나타난다. 각 근의 중복도가 $m$일 때, 해당 지수함수들을 다음 실수 기저함수들로 바꿀 수 있다.

$$
t^ke^{at}\cos(bt),\qquad t^ke^{at}\sin(bt)
\quad(k=0,\ldots,m-1).
$$

실근에 대응하는 기저함수들과 함께 실수 계수로 선형결합하면 모든 실수해를 얻는다.

### 예제 8. 중근을 갖는 방정식

**문제.** $y'''-4y''+5y'-2y=0$의 일반해를 구하라.

**풀이.** $p(\lambda)=\lambda^3-4\lambda^2+5\lambda-2=(\lambda-1)^2(\lambda-2)$이므로 해공간의 기저는 $\{e^t,te^t,e^{2t}\}$이다. 따라서

$$
y(t)=(b_0+b_1t)e^t+b_2e^{2t}.
$$

## 초기조건의 의미

임의의 $t_0\in\mathbb R$에 대해 해를 초기값들로 보내는 사상

$$
\Phi_{t_0}:\mathcal S\to\mathbb C^n,\qquad
\Phi_{t_0}(y):=
\bigl(y(t_0),y'(t_0),\ldots,y^{(n-1)}(t_0)\bigr)
\quad(\forall y\in\mathcal S)
$$

은 동형사상이다. 따라서 $n$개의 초기값을 지정하면 해공간에서 하나의 해가 유일하게 결정된다.
