# 얽힘과 물질의 상

> *얽힘 엔트로피 $S(A)=-\mathrm{Tr}\,\rho_A\ln\rho_A$ 의 면적 법칙 $S\sim\alpha L-\gamma$ 와 위상항 $\gamma=\ln\mathcal{D}$ 가 — 국소 질서변수 없이 — 물질의 상을 규정한다.*

## 🎯 핵심 질문

- 얽힘 엔트로피 $S(A)=-\mathrm{Tr}\,\rho_A\ln\rho_A$ 는 부분계 $A$ 가 나머지와 *얼마나 얽혔는지* 를 잰다. 이것이 어떻게 물질의 *상(phase)* 을 분류하는 도구가 되는가?
- 왜 갭 있는 바닥상태는 부피가 아니라 *경계 면적* 에 비례($S\sim\alpha L$)하고, 임계점에서는 *로그* 보정($S\sim\frac{c}{3}\ln L$)이 붙는가?
- 면적 법칙의 음의 상수항 $-\gamma$(위상 얽힘 엔트로피, $\gamma=\ln\mathcal{D}$)이 어떻게 위상 질서를 *단일 바닥상태에서* 진단하는가?

## 🌍 어디서 나타나나

- **갭 있는 위상 상**: 토릭 코드·분수 양자홀에서 위상 엔트로피 $\gamma=\ln\mathcal{D}$ ($Z_2$: $\ln2$, 라플린 $1/3$: $\tfrac12\ln3$) — 단일 바닥상태에서 위상 질서 진단.
- **1D 임계계**: 양자 임계 스핀 사슬(횡장 이징의 임계점)에서 $S\sim\frac{c}{3}\ln L$, 중심 전하 $c$ 가 보편 부류를 식별.
- **DMRG·텐서 네트워크**: 면적 법칙은 1D 갭 계의 *효율적 시뮬레이션 가능성*(MPS) 의 근거. 얽힘 구조가 수치 방법의 한계를 결정.
- **양자 시뮬레이터**: 냉원자(양자 가스 현미경)·이온 트랩에서 Rényi 얽힘 엔트로피를 직접 측정 (Islam et al., Nature 2015; Kaufman et al., 2016).
- **L5 홀로그래피**: 류-다카야나기 공식 — 얽힘 엔트로피가 최소 곡면 넓이로 기하화. 응집물질 얽힘이 시공간 기하로 연결.

## 🔍 직관의 함정

- **"엔트로피는 무질서·열역학"** — 아니다. 얽힘 엔트로피는 $T=0$ 바닥상태(순수 상태!)에서도 0이 아니다. 이것은 열적 무질서가 아니라 *양자 얽힘* 의 척도다. 전체는 순수 상태인데 부분계 $\rho_A$ 는 혼합 상태가 된다 — 순수한 양자적 효과.
- **"얽힘은 부피에 비례한다(많은 자유도 = 많은 얽힘)"** — 갭 있는 바닥상태는 *경계 면적* 에 비례한다(면적 법칙). 부피 법칙은 무작위·고에너지 상태의 특징이다. 면적 법칙이 "낮은 얽힘" 구조를 보장해 텐서 네트워크가 작동한다.
- **"얽힘 엔트로피는 비물리적 계산량"** — 아니다. Rényi 엔트로피는 양자 가스 현미경·이온 트랩에서 *측정* 된다(복제 간섭). 위상항 $\gamma$ 도 수치로 추출돼 위상 질서를 식별.
- **"상은 국소 질서변수로 정의"** — 위상 질서는 국소 질서변수가 없다(→ 03). 얽힘 패러다임은 *비국소* 얽힘 구조로 상을 정의해 란다우를 보완·대체한다.

## ⚙️ 제1원리 유도

### 1. 얽힘 엔트로피의 정의와 의미

전체 계가 순수 바닥상태 $|\Psi\rangle$ 이고, 공간을 $A$ 와 $B$ 로 나눈다. 부분계 $A$ 의 환원 밀도행렬:

$$\rho_A = \mathrm{Tr}_B\,|\Psi\rangle\langle\Psi|$$

얽힘 엔트로피는 이 $\rho_A$ 의 폰노이만 엔트로피:

$$S(A) = -\mathrm{Tr}\,(\rho_A\ln\rho_A) = -\sum_i \lambda_i\ln\lambda_i$$

여기서 $\lambda_i$ 는 $\rho_A$ 의 고윳값. 슈미트 분해 $|\Psi\rangle=\sum_i\sqrt{\lambda_i}\,|i\rangle_A|i\rangle_B$ 에서 $\lambda_i$ 가 슈미트 계수의 제곱이다. $|\Psi\rangle$ 이 곱상태면 슈미트 계수 하나만 1 → $S=0$(얽힘 없음). 최대 얽힘이면 $\lambda_i$ 균등 → $S=\ln(\dim)$. 핵심: 전체가 순수해도 $S(A)>0$ 일 수 있고, 이 $S$ 가 *양자 얽힘의 양* 이다. $\square$

### 2. 면적 법칙 — 왜 부피가 아니라 경계인가

갭 있는 바닥상태에서 상관 길이 $\xi$ 가 유한하다. 얽힘은 *경계 근처* $\xi$ 두께의 자유도에서만 일어난다(멀리 떨어진 자유도는 갭 때문에 얽히지 않음). 따라서 $d$ 차원에서 경계 $\partial A$ 면적 $L^{d-1}$ 에 비례:

$$S(A) \sim \alpha\,L^{d-1} \qquad(\text{면적 법칙})$$

$\alpha$ 는 비보편적(자외선 척도 의존) 상수. 1D($d=1$)에서는 경계가 점이라 $S\sim\text{const}$. 직관 유도: 갭 $\Delta$ 가 있으면 상관함수 $\langle O(0)O(r)\rangle\sim e^{-r/\xi}$ 로 지수 감쇠 → 거리 $\gg\xi$ 자유도는 사실상 분리(곱상태) → 얽힘 기여 0 → 경계만 기여. 이것이 면적 법칙의 물리적 기원이고, 텐서 네트워크(MPS/PEPS)가 갭 계를 효율적으로 표현하는 근거다. $\square$

### 3. 임계점의 로그 위반 — 중심 전하

임계점에서는 갭이 닫혀 $\xi\to\infty$, 면적 법칙이 *위반* 된다. 1D 임계계(공형장론, CFT)에서:

$$S(L) = \frac{c}{3}\ln L + \text{const} \qquad(\text{주기경계})$$

또는 열린 경계에서 $\frac{c}{6}\ln L$. 여기서 $c$ 는 CFT의 **중심 전하** — 보편 부류를 식별하는 정수/유리수(자유 페르미온 $c=1/2$, 자유 보손 $c=1$). 유도 골자: CFT의 복제(replica) 트릭으로 $\mathrm{Tr}\,\rho_A^n$ 을 $n$-시트 리만면 위 분배함수로 계산하면 트위스트 연산자의 차원이 $\frac{c}{12}(n-1/n)$ 을 주고, $S=-\partial_n\mathrm{Tr}\rho_A^n|_{n=1}$ 에서 $\frac{c}{3}\ln L$ 이 나온다. 핵심: 얽힘 엔트로피의 *로그 증가* 와 그 계수가 임계 보편 부류를 직접 드러낸다. $\square$

### 4. 위상 얽힘 엔트로피 — 음의 상수항이 위상을 센다

갭 있는 2D 위상 질서에서 면적 법칙에 *보편적 음의 상수* 가 붙는다 (Kitaev-Preskill, Levin-Wen 2006):

$$S(A) = \alpha L - \gamma + \mathcal{O}(1/L), \qquad \gamma = \ln\mathcal{D}$$

여기서 $\mathcal{D}=\sqrt{\sum_a d_a^2}$ 는 *전체 양자 차원*($d_a$=애니온 양자 차원). 토릭 코드($Z_2$): 애니온 $1,e,m,\varepsilon$ 모두 $d_a=1$ → $\mathcal{D}=\sqrt{4}=2$ → $\gamma=\ln2$. 라플린 $1/q$: $\mathcal{D}=\sqrt{q}$ → $\gamma=\tfrac12\ln q$.

$\gamma$ 추출법(Kitaev-Preskill): 평면을 세 영역 $A,B,C$ 로 나누고 *비위상* 면적항이 상쇄되는 조합을 만든다:

$$S_{\text{topo}} = S_A + S_B + S_C - S_{AB} - S_{BC} - S_{AC} + S_{ABC} = -\gamma$$

경계 길이 기여가 모두 상쇄되고 *위상항만* 살아남는다. 핵심: $\gamma>0$ 은 단일 바닥상태가 *긴 거리 얽힘*(위상 질서)을 가진다는 비국소 증거다. 곱상태·대칭 깨짐 상은 $\gamma=0$. $\square$

### 실험 1 — 1D 스핀 사슬: 면적 법칙 vs 로그 위반

횡장 이징 사슬을 자유 페르미온으로 정확히 풀어, 갭 상에서 $S=$상수(면적 법칙), 임계점에서 $S\sim\frac{c}{6}\ln L$ ($c=1/2$)임을 확인한다.

```python
import numpy as np

# 횡장 이징 H = -Σ σ^x_i σ^x_{i+1} - h Σ σ^z_i  (열린 사슬)
# 조던-위그너 -> 자유 페르미온(BdG). 부분계 얽힘 엔트로피를
# 나무(Nambu) 상관행렬 M 의 고윳값(ν)으로 계산 (Peschel/Vidal 방법).
def ising_entropy(N, h, lA):
    t, Delta, mu = 1.0, 1.0, 2.0*h        # 호핑/페어링/화학퍼텐셜
    A = np.zeros((N, N)); B = np.zeros((N, N))
    for i in range(N):
        A[i, i] = -mu
    for i in range(N-1):
        A[i, i+1] += -t;    A[i+1, i] += -t
        B[i, i+1] += Delta; B[i+1, i] += -Delta
    Hbdg = np.block([[A, B], [-B, -A]])
    w, U = np.linalg.eigh(Hbdg)
    order = np.argsort(w)
    Uf = U[:, order[:N]]                   # 음의 에너지(채워진) 모드
    g, h2 = Uf[:N, :], Uf[N:, :]
    C  = h2.conj() @ h2.T                  # <c_i^† c_j>
    Fp = h2.conj() @ g.T                   # <c_i^† c_j^†>
    Ga, Fa = C[:lA, :lA], Fp[:lA, :lA]     # 부분계 A=[0,lA) 블록
    M = np.block([[Ga, Fa], [Fa.conj().T, np.eye(lA) - Ga.conj().T]])
    nu = np.clip(np.linalg.eigvalsh(M).real, 1e-12, 1 - 1e-12)
    nu = nu[nu <= 0.5]                      # (ν, 1-ν) 쌍 -> 절반만
    return -np.sum(nu*np.log(nu) + (1-nu)*np.log(1-nu))

N = 400
for h, label in [(3.0, "갭 상(강한 상자성)"), (2.0, "갭 상(상자성)"), (1.0, "임계점 h=1")]:
    Ss = [ising_entropy(N, h, lA) for lA in [20, 40, 60, 80]]
    print(f"h={h} {label}: S(lA=20..80) = {np.round(Ss,3)}")
# 갭 상(h=2,3): S 가 부분계 크기에 무관한 상수 (면적 법칙, 1D 에서 상수)
# 임계점 h=1: S 가 lA(=L) 에 따라 로그 증가  (~ (c/6) ln L, c=1/2)
```

갭 상($h=2,3$)에서는 $S$ 가 부분계 크기에 무관한 상수(면적 법칙=1D에서 상수), 임계점($h=1$)에서만 로그 증가 — 얽힘이 *상을 구분* 함을 보인다. (강자성 쪽 $h<1$ 은 바닥상태 2겹 겹침 때문에 별도 처리가 필요해 상자성 쪽으로 면적 법칙을 보였다.)

### 실험 2 — 임계 이징의 중심 전하 추출

임계점 데이터에 $S=\frac{c}{6}\ln(\frac{N}{\pi}\sin\frac{\pi l}{N})+\text{const}$ (Calabrese-Cardy) 를 피팅해 $c\approx1/2$ 를 얻는다.

```python
import numpy as np

# (실험 1 의 ising_entropy 와 동일한 BdG 방법 재사용)
def ising_entropy(N, h, lA):
    t, Delta, mu = 1.0, 1.0, 2.0*h
    A = np.zeros((N, N)); B = np.zeros((N, N))
    for i in range(N):
        A[i, i] = -mu
    for i in range(N-1):
        A[i, i+1] += -t;    A[i+1, i] += -t
        B[i, i+1] += Delta; B[i+1, i] += -Delta
    Hbdg = np.block([[A, B], [-B, -A]])
    w, U = np.linalg.eigh(Hbdg)
    Uf = U[:, np.argsort(w)[:N]]
    g, h2 = Uf[:N, :], Uf[N:, :]
    C, Fp = h2.conj() @ h2.T, h2.conj() @ g.T
    Ga, Fa = C[:lA, :lA], Fp[:lA, :lA]
    M = np.block([[Ga, Fa], [Fa.conj().T, np.eye(lA) - Ga.conj().T]])
    nu = np.clip(np.linalg.eigvalsh(M).real, 1e-12, 1-1e-12)
    nu = nu[nu <= 0.5]
    return -np.sum(nu*np.log(nu)+(1-nu)*np.log(1-nu))

N = 400
ls = np.arange(20, N-20, 16)
S = np.array([ising_entropy(N, 1.0, int(l)) for l in ls])
# Calabrese-Cardy 척도변수 (열린경계): x = ln(N/π · sin(π l /N)), 기울기 = c/6
x = np.log((N/np.pi) * np.sin(np.pi*ls/N))
slope, b = np.polyfit(x, S, 1)
print(f"피팅 기울기 = {slope:.4f}  ->  c ≈ {6*slope:.3f}")
print("(횡장 이징 임계점 c = 1/2 = 0.5 예측)")
```

추출된 중심 전하 $c\approx0.5$ 가 임계 이징의 보편 부류를 식별한다 — 얽힘 엔트로피가 *상전이의 지문* 을 담는다.

## 🧪 실험·관측 증거

- **냉원자 Rényi 엔트로피**: 양자 가스 현미경으로 보스-허바드 사슬의 2차 Rényi 얽힘 엔트로피를 복제 간섭으로 직접 측정 (Islam et al., Nature 2015; Kaufman et al., Science 2016) — 면적 법칙·열화 동역학 관측.
- **위상 엔트로피 수치**: 토릭 코드·키타에프 모형 DMRG에서 $\gamma=\ln2$ 추출; 라플린 $1/3$ 에서 $\gamma=\tfrac12\ln3$.
- **중심 전하 측정**: 임계 사슬 시뮬레이션에서 $S\sim\frac{c}{3}\ln L$ 로 $c$ 추출, CFT 예측과 일치.
- **MPS/텐서 네트워크**: 면적 법칙이 1D 갭 계를 다항 자원으로 표현 가능케 함 — DMRG의 성공 자체가 면적 법칙의 실증.

## 🔬 경계

- **부피 법칙 상**: 강하게 얽힌(예: 열화된, 또는 측정 유발 전이의 한 쪽) 상태는 *부피 법칙* $S\sim L^d$ 을 따라 텐서 네트워크로 효율적 표현 불가 — 강상관 수치의 근본 장벽(얽힘 장벽, → Ch6-05).
- **2D 면적 법칙의 미증명**: 1D 갭 계의 면적 법칙은 엄밀히 증명됐지만(Hastings), 2D 이상은 일반적으로 *미증명*(예외·반례 가능성).
- **$\gamma$ 추출의 미묘함**: 위상 엔트로피는 유한 크기·경계 효과·들뜸에 민감하다. 정확한 영역 분할(Kitaev-Preskill/Levin-Wen)과 외삽이 필요.
- **유한 온도·동역학**: 위 결과는 $T=0$ 바닥상태에 대한 것. 유한 온도·비평형에서 얽힘 구조는 복잡해진다(열적 엔트로피와 혼합).

## 🧬 횡단 원리

- **위상 질서**: $\gamma=\ln\mathcal{D}$ 가 위상 질서를 단일 바닥상태에서 진단한다 — 03의 바닥상태 겹침과 같은 정보를 얽힘으로 부호화(→ ch5-emergent-gauge/03-topological-order.md).
- **창발 게이지장**: $\mathcal{D}$ 가 창발 게이지 군의 차원을 센다(→ ch5-emergent-gauge/01-emergent-gauge-field.md).
- **양자 정보**: 얽힘 엔트로피는 양자 정보의 중심 자원 척도. 면적 법칙이 효율적 부호화·시뮬레이션을 가능케 한다(→ quantum-information).
- **대칭 깨짐과 대비**: 란다우의 국소 질서변수 대신 *비국소 얽힘* 으로 상을 정의 — 패러다임 전환(→ ch1-more-is-different/04-symmetry-breaking-order.md).

## 🪜 창발

- **L5 holography**: 류-다카야나기 공식 $S(A)=\frac{\text{Area}(\gamma_A)}{4G_N}$ — 얽힘 엔트로피가 휜 시공간의 *최소 곡면 넓이* 로 기하화된다. 응집물질의 면적 법칙이 중력의 면적(엔트로피)과 같은 구조.
- **L5 emergent-spacetime**: "얽힘이 시공간을 짓는다"(ER=EPR, 텐서 네트워크 홀로그래피). 부분계 얽힘 패턴이 창발 기하의 연결성을 결정 — 같은 아이디어의 극단.
- **L6 emergence**: 얽힘이 상·기하·게이지장을 모두 조직하는 더 근본적 자원일 수 있다 — "무엇이 근본인가" 에 대한 정보론적 답.

## 📐 예측·반증

- **면적 법칙**: 갭 있는 바닥상태는 $S\sim\alpha L^{d-1}$. 부피 법칙이면 갭 없음(또는 비바닥상태).
- **로그 위반 + 중심 전하**: 1D 임계계 $S\sim\frac{c}{3}\ln L$, $c$ 가 보편 부류를 식별 — 측정으로 검증(실험 2).
- **위상 엔트로피**: 위상 질서 $\gamma=\ln\mathcal{D}>0$ (토릭 코드 $\ln2$, 라플린 $1/3$ $\tfrac12\ln3$). 자명 상 $\gamma=0$.
- **반증 조건**: 갭 상에서 (1) 부피 법칙이 나오거나, (2) 위상 질서로 주장된 상에서 $\gamma=0$ 이거나, (3) 임계계에서 추출한 $c$ 가 주장된 보편 부류와 다르면, 해당 얽힘 분류는 반증된다.

## 🤔 다음 질문

얽힘이 상을 규정한다면, 상*전이* 는 얽힘 구조의 어떤 변화인가? $T=0$ 에서 양자 요동이 일으키는 **양자 상전이** — 결합상수를 돌릴 때 얽힘·갭·질서가 어떻게 재조직되는지 — 를 다음 챕터에서 다룬다. 그리고 여기서 만난 얽힘-기하 연결은 위 레이어(L5 홀로그래피·창발 시공간)에서 *시공간 자체의 창발* 로 폭발한다.

---

🧩 **Principle** — 얽힘 엔트로피 $S=-\mathrm{Tr}\rho_A\ln\rho_A$ 의 면적 법칙·로그 위반·위상항 $\gamma=\ln\mathcal{D}$ 이 국소 질서변수 없이 물질의 상을 *규정* 한다.
🔬 **Boundary** — 부피 법칙 상은 텐서 네트워크 표현 불가(얽힘 장벽), 2D 면적 법칙은 미증명, $\gamma$ 추출은 유한 크기·경계 효과에 민감하다.
🪜 **Emergence** — 위 레이어(L5 holography·emergent-spacetime·L6)에서 같은 면적 구조가 류-다카야나기 공식으로 시공간 기하를 짓고, 냉원자 Rényi 엔트로피·중심 전하 $c$·위상항 $\gamma=\ln2$ 로 검증된다.

## 📝 연습문제

**1. (기초)** 두 큐비트 벨 상태 $|\Psi\rangle=\frac{1}{\sqrt2}(|00\rangle+|11\rangle)$ 에 대해 한 큐비트의 환원 밀도행렬 $\rho_A$ 와 얽힘 엔트로피 $S(A)$ 를 계산하라. 곱상태 $|00\rangle$ 와 비교하라.

<details><summary>해설</summary>

벨 상태: $\rho_A=\mathrm{Tr}_B|\Psi\rangle\langle\Psi|$. $|\Psi\rangle\langle\Psi|=\tfrac12(|00\rangle+|11\rangle)(\langle00|+\langle11|)$. B를 대각합:
$$\rho_A=\tfrac12(|0\rangle\langle0|+|1\rangle\langle1|)=\tfrac12 I.$$
고윳값 $\lambda=\tfrac12,\tfrac12$. 따라서
$$S(A)=-\tfrac12\ln\tfrac12-\tfrac12\ln\tfrac12=\ln2.$$
최대 얽힘(1 ebit). 반면 곱상태 $|00\rangle$ 은 $\rho_A=|0\rangle\langle0|$, 고윳값 $1,0$ → $S=-1\ln1-0=0$. 얽힘 없음. 핵심: 전체는 둘 다 *순수 상태* 인데, 벨 상태만 부분계가 혼합($S>0$)이 된다 — 이것이 양자 얽힘의 본질이고, 다체계로 확장하면 면적 법칙·위상항이 된다. $\square$
</details>

**2. (심화)** 1D 갭 있는 계에서 얽힘 엔트로피가 부분계 크기에 무관한 상수(면적 법칙)임을, 상관 길이 $\xi$ 가 유한하다는 사실로부터 직관적으로 유도하라. 임계점($\xi\to\infty$)에서 왜 로그 위반이 생기는가?

<details><summary>해설</summary>

갭 $\Delta>0$ → 상관함수 $\langle O(0)O(r)\rangle\sim e^{-r/\xi}$ 로 지수 감쇠($\xi\sim v/\Delta$ 유한). 부분계 $A$ 와 나머지 $B$ 사이 얽힘은 *경계 근처* $\xi$ 두께 영역의 자유도에서만 발생 — 경계에서 $\gg\xi$ 떨어진 자유도는 사실상 분리되어 곱상태처럼 행동(얽힘 기여 0). 1D에서 경계는 *점*(0차원)이므로 얽힘 기여가 부분계 길이 $l$ 에 무관한 *상수* → $S\sim$ const(면적 법칙의 1D판). 

임계점에서는 갭이 닫혀 $\xi\to\infty$, 모든 척도의 요동이 얽힘에 기여한다. 스케일 불변성에 의해 각 길이 척도 $\xi_n\sim 2^n$ 가 비슷한 양 $\sim c$ 만큼 기여하고, $l$ 까지의 척도 수가 $\sim\ln l$ 개이므로 $S\sim c\cdot\ln l$ → $\frac{c}{3}\ln l$(정확한 계수는 CFT). 핵심: 유한 $\xi$ = 면적 법칙, $\xi\to\infty$ = 로그 위반. 실험 1·2가 이를 수치로 보인다. $\square$
</details>

**3. (논문 비평)** Kitaev-Preskill / Levin-Wen (2006)은 위상 얽힘 엔트로피 $\gamma=\ln\mathcal{D}$ 를 위상 질서의 보편 지표로 제안했다. (a) 영역 분할 조합 $S_A+S_B+S_C-S_{AB}-\cdots+S_{ABC}$ 가 어떻게 면적항을 상쇄하고 $\gamma$ 만 남기는지, (b) 실제 수치/실험에서 $\gamma$ 추출이 신뢰성을 잃는 함정을 비판적으로 논하라.

<details><summary>해설</summary>

(a) 각 영역의 $S\approx\alpha(\text{경계 길이})-\gamma$. Kitaev-Preskill 조합 $S_{\text{topo}}=S_A+S_B+S_C-S_{AB}-S_{BC}-S_{CA}+S_{ABC}$ 에서, 영역들을 *공통 경계를 공유* 하도록 배치하면 모든 경계 길이($\alpha L$ 항)가 부호 조합으로 정확히 상쇄된다(들어가는 +항과 빼는 −항의 경계 기여가 같음). 한편 *상수* $-\gamma$ 는 영역 수 계수 $(3-3+1)=1$ 로 $-\gamma$ 만 남는다 → $S_{\text{topo}}=-\gamma$. 비위상 면적항을 빼고 위상 정보만 추출하는 영리한 설계.

(b) 함정: ① **유한 크기·코너 기여** — 영역 모서리가 추가 보편/비보편 코너항을 줄 수 있어 $\gamma$ 추정을 오염. ② **상관 길이 vs 영역 크기** — 영역이 $\xi$ 보다 충분히 크지 않으면 면적항 상쇄가 불완전해 가짜 $\gamma$. ③ **들뜸·유한 온도** — 애니온이 섞이면 $\gamma$ 가 줄거나 사라짐. ④ **외삽 의존성** — 여러 크기에서 외삽해야 하며, 외삽 방식에 따라 $\gamma$ 가 달라질 수 있다. ⑤ **DMRG의 경우** 원통 기하의 둘레 의존성·경계 모드 오염. 핵심 비판: $\gamma=\ln\mathcal{D}$ 는 원리적으로 강력하지만, 실제 추출은 신중한 영역 설계·크기 외삽·들뜸 통제 없이는 신뢰할 수 없다. 바닥상태 겹침·애니온 통계 같은 독립 증거와 교차 검증이 권장된다. $\square$
</details>

---

<div align="center">

[◀ 이전: 위상 질서 — 대칭 깨짐 없는 질서](03-topological-order.md)  ·  [📚 README](../README.md)  ·  [다음: 양자 상전이 ▶](../ch6-quantum-phase-correlation/01-quantum-phase-transition.md)

</div>
