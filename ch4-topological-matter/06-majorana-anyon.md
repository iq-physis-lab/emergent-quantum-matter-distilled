# 마요라나와 비아벨 애니온

> *자기 자신이 반입자인 영모드($\gamma=\gamma^\dagger$), 둘이 모여야 하나의 페르미온을 이루는 입자 — 그것들을 서로 둘러 감으면 결과가 순서에 의존하는 비가환 유니터리 게이트가 되고, 그 자체로 잡음에 면역인 양자 계산이 된다.*

## 🎯 핵심 질문

- 페르미온을 둘로 쪼갠 *실수* 자유도 — 마요라나 $\gamma=\gamma^\dagger$ — 는 어떻게 가능하며, 키타에프 사슬에서 *왜* 양 끝에 영에너지 모드로 나타나는가?
- 두 마요라나가 멀리 떨어져 하나의 페르미온을 비국소적으로 부호화할 때, 그 점유 정보가 *왜* 국소 잡음에 면역인가?
- 비아벨 애니온의 브레이딩이 *왜* 비가환 유니터리 변환(순서가 결과를 바꾸는 양자 게이트)인가?

## 🌍 어디서 나타나나

- **반도체 나노선 + s-파 초전도체 + 자기장**: Rashba 나노선(InSb, InAs)에 초전도 근접 + 자기장으로 위상 초전도상 유도, 끝에 마요라나 영모드(MZM). Mourik 외(2012)가 영바이어스 전도 피크 보고(이후 해석 논쟁).
- **철 기반 초전도체 와동심·자성 원자 사슬**: $\text{FeTe}_x\text{Se}_{1-x}$ 와동 중심의 영바이어스 피크, Fe 원자 사슬 끝의 MZM 후보.
- **$\nu=5/2$ 분수 양자홀**: Moore–Read Pfaffian 상태의 준입자가 비아벨 애니온(Ising 애니온) 후보.
- **위상 양자컴퓨팅 플랫폼**: Microsoft 등이 추구하는 위상 큐비트 — 브레이딩으로 하드웨어 수준에서 보호되는 게이트.

## 🔍 직관의 함정

**함정 1 — "마요라나는 새 소립자다."** 응집물질의 마요라나는 소립자가 아니라 **초전도체 속 전자–홀 중첩의 창발적 준입자**. 입자와 반입자가 같다($\gamma=\gamma^\dagger$)는 건 보골류보프 준입자가 전자와 홀을 같은 비율로 섞었다는 뜻 — 창발적 실체이지 진공의 마요라나 페르미온이 아니다.

**함정 2 — "영바이어스 전도 피크 = 마요라나 증명."** 영바이어스 피크는 안드레예프 구속 상태·코른도·무질서 등 *다른* 원인으로도 생긴다. 마요라나의 결정적 증거는 (i) $2e^2/h$ 양자화 피크, (ii) 비국소성(양 끝 상관), (iii) 궁극적으로 브레이딩의 비아벨 통계다. 단일 피크는 필요조건일 뿐.

**함정 3 — "비아벨 = 그냥 더 복잡한 위상."** 아벨 애니온([03](./03-fractional-quantum-hall.md))은 브레이딩이 *위상 $e^{i\theta}$* (수). 비아벨은 브레이딩이 *행렬* $U$ — 축퇴된 바닥상태 공간을 회전시킨다. $U_1 U_2\neq U_2 U_1$ 이라 *교환 순서가 최종 상태를 바꾼다*. 이 비가환성이 양자 게이트의 본질이다.

## ⚙️ 제1원리 유도

### 1) 마요라나 — 페르미온을 둘로 쪼개기

복소 페르미온 연산자 $c,c^\dagger$ ($\{c,c^\dagger\}=1$)를 두 에르미트 연산자로 분해:

$$
\gamma_1=c+c^\dagger,\qquad \gamma_2=\frac{c-c^\dagger}{i}=-i(c-c^\dagger).
$$

그러면

$$
\gamma_1=\gamma_1^\dagger,\quad \gamma_2=\gamma_2^\dagger,\quad
\{\gamma_a,\gamma_b\}=2\delta_{ab},\quad \gamma_a^2=1.
$$

각 $\gamma_a$ 는 **자기 자신이 반입자**($\gamma=\gamma^\dagger$) 인 마요라나 연산자. 역변환: $c=\tfrac12(\gamma_1+i\gamma_2)$, 점유수 $n=c^\dagger c=\tfrac12(1+i\gamma_1\gamma_2)$.

$$
\boxed{\text{하나의 복소 페르미온}=\text{두 개의 마요라나}.}\quad\square
$$

핵심: 두 마요라나를 *멀리* 떨어뜨려 놓으면, 그 페르미온의 점유($n=0$ 또는 $1$)는 어느 한 곳에서 측정할 수 없는 **비국소 정보** 가 된다.

### 2) 키타에프 사슬 — 끝에 남는 짝 없는 마요라나

1차원 p-파 초전도체(Kitaev, 2001). $N$ 사이트 사슬:

$$
H=-\mu\sum_j c_j^\dagger c_j-\sum_j\big(t\,c_j^\dagger c_{j+1}+\Delta\,c_j c_{j+1}+\text{h.c.}\big).
$$

각 사이트를 두 마요라나로 분해 $c_j=\tfrac12(\gamma_{2j-1}+i\gamma_{2j})$. **특수점** $\mu=0,\ t=\Delta$ 에서 해밀토니안이 깔끔히 풀린다:

$$
H=it\sum_{j=1}^{N-1}\gamma_{2j}\,\gamma_{2j+1}.
$$

사이트 $j$ 의 둘째 마요라나가 사이트 $j+1$ 의 첫째 마요라나와 짝지어진다. 사슬을 보면 **$\gamma_1$(왼쪽 끝)과 $\gamma_{2N}$(오른쪽 끝)이 해밀토니안에 전혀 안 나타난다**:

$$
[H,\gamma_1]=[H,\gamma_{2N}]=0\quad\Longrightarrow\quad \text{두 끝 마요라나는 }E=0\text{ 영모드}.\quad\square
$$

이 짝 없는 두 끝 마요라나가 하나의 비국소 페르미온 $c_M=\tfrac12(\gamma_1+i\gamma_{2N})$ 을 이루고, 그 점유 ($n_M=0,1$)가 두 개의 축퇴된 바닥상태를 만든다. 일반 매개변수에서도 위상상($|\mu|<2t$)이면 영모드가 살아남는다(특수점은 그 위상상 안의 한 점).

### 3) 위상상 판정 — 페르미온 패리티의 부호

키타에프 사슬의 위상 불변량은 $\mathbb{Z}_2$ — BdG 해밀토니안의 두 시간역전 불변점에서 파피안 부호의 곱(Majorana number):

$$
\mathcal{M}=\text{sgn}\big[\text{Pf}(H_{\text{BdG}}(k=0))\cdot\text{Pf}(H_{\text{BdG}}(k=\pi))\big].
$$

$\mathcal{M}=-1$ 이면 위상상(끝 마요라나 존재), $+1$ 이면 자명. 이를 $\mu,t,\Delta$ 로 풀면 위상 조건:

$$
\boxed{|\mu|<2t\ \Rightarrow\ \text{위상 초전도상(마요라나 영모드)}.}\quad\square
$$

위상 상전이($\mu=\pm2t$)에서 벌크 갭이 닫히며 마요라나가 생성/소멸 — [05](./05-topological-protection.md) 의 갭 닫힘 원리와 정확히 일치.

### 4) 비국소 부호화와 보호 — 잡음이 닿을 수 없는 큐비트

두 끝 마요라나가 만든 페르미온 패리티 $P=i\gamma_1\gamma_{2N}=1-2n_M$ 은 사슬 전체에 걸친 *비국소* 양자수. 한 끝에서의 임의 국소 섭동 $\hat O(\gamma_1)$ 은 패리티를 바꾸려면 *반대쪽 끝* $\gamma_{2N}$ 까지 건드려야 한다:

$$
\langle 0|\hat O_{\text{local}}|1\rangle=0\quad(\hat O \text{ 가 한 끝에만 작용하면}).\quad\square
$$

따라서 두 축퇴 상태($n_M=0,1$)는 국소 잡음으로 구별·전이될 수 없다 — 위상 보호된 큐비트. 영모드의 에너지 갈라짐은 사슬 길이 $L$ 에 대해 지수적으로 작다, $\delta E\sim e^{-L/\xi}$ — [05](./05-topological-protection.md) 의 지수적 보호와 같은 구조.

### 5) 비아벨 브레이딩 — 교환이 비가환 게이트

$2n$ 개 마요라나는 $2^n$ 차원 *축퇴 바닥상태 공간* 을 만든다(패리티 고정 시 $2^{n-1}$). 두 마요라나 $\gamma_a,\gamma_b$ 를 실공간에서 교환(braid)하면, 단열 진화가 다음 유니터리를 구현한다:

$$
\boxed{B_{ab}=\exp\!\left(\frac{\pi}{4}\gamma_a\gamma_b\right)=\frac{1}{\sqrt2}\big(1+\gamma_a\gamma_b\big).}\quad\square
$$

이것은 바닥상태 공간 위의 회전. 결정적으로, 서로 다른 짝의 브레이딩은 **교환하지 않는다**:

$$
B_{12}B_{23}\neq B_{23}B_{12}\quad(\because [\gamma_1\gamma_2,\gamma_2\gamma_3]\neq0).
$$

따라서 브레이딩 *순서* 가 최종 상태를 바꾼다 — 비아벨 통계. 이 유니터리들은 마요라나의 *위치 교환* 이라는 위상적 조작으로 구현되므로, 경로의 세부(속도·모양)에 무관하고 국소 잡음에 면역인 **위상 양자 게이트** 가 된다.

> 주의: 마요라나(Ising 애니온) 브레이딩만으로는 클리퍼드 게이트(보호됨)만 얻고, 보편 양자 계산에는 비클리퍼드 게이트(예: $T$ 게이트)를 마법 상태 증류 등 *보호되지 않는* 방법으로 보충해야 한다. 보편성과 위상 보호의 절충이 핵심 난제다.

### 실험 1 — 키타에프 사슬: 끝에 묶인 마요라나 영모드 에너지

```python
import numpy as np

def kitaev_chain_spectrum(N, mu, t, delta):
    """1D p-파 초전도 사슬의 BdG 해밀토니안 스펙트럼.
       위상상(|mu|<2t)이면 E≈0 영모드 한 쌍(끝 마요라나)이 나타난다."""
    # Nambu (c, c†) 기저 BdG: H = [[A, B],[-B*, -A*]] 형태
    A = np.zeros((N, N), complex)   # 정상 호핑/화학퍼텐셜
    Bd = np.zeros((N, N), complex)  # 짝짓기(pairing)
    for j in range(N):
        A[j, j] = -mu
        if j+1 < N:
            A[j, j+1] = -t;     A[j+1, j] = -t
            Bd[j, j+1] = delta; Bd[j+1, j] = -delta   # 반대칭 p-파
    H = np.block([[A, Bd], [-Bd.conj(), -A.conj()]])
    return np.linalg.eigvalsh(H)

N = 40
print("위상상 판정: |mu| < 2t 이면 위상 초전도(마요라나 영모드)")
for mu in [0.0, 1.0, 2.0, 3.0]:
    ev = kitaev_chain_spectrum(N, mu=mu, t=1.0, delta=1.0)
    gap_min = np.min(np.abs(ev))   # 0에 가장 가까운 에너지
    phase = "위상상(영모드!)" if abs(mu) < 2.0 else "자명상"
    print(f"  mu={mu:.1f} (2t=2.0): 최소|E|={gap_min:.2e}  -> {phase}")
# |mu|<2 이면 최소|E| 가 지수적으로 0에 가까움(끝 마요라나),
# |mu|>2 이면 유한 갭(영모드 없음)
```

### 실험 2 — 영모드의 비국소성: 양 끝에 국소화된 마요라나 파동함수

```python
import numpy as np

def kitaev_zero_modes(N, mu, t, delta):
    A = np.zeros((N, N), complex); Bd = np.zeros((N, N), complex)
    for j in range(N):
        A[j, j] = -mu
        if j+1 < N:
            A[j, j+1] = -t; A[j+1, j] = -t
            Bd[j, j+1] = delta; Bd[j+1, j] = -delta
    H = np.block([[A, Bd], [-Bd.conj(), -A.conj()]])
    ev, evec = np.linalg.eigh(H)
    i0 = np.argsort(np.abs(ev))[:2]   # 0에 가장 가까운 두 상태
    return ev[i0], evec[:, i0]

N = 40
ev0, vecs = kitaev_zero_modes(N, mu=0.0, t=1.0, delta=1.0)
print("영모드 에너지:", np.round(ev0, 6))
# 두 영모드의 입자 성분 밀도 (사이트별)
for k in range(2):
    v = vecs[:, k]
    dens = np.abs(v[:N])**2 + np.abs(v[N:])**2  # 사이트별 가중치
    left = dens[:5].sum(); right = dens[-5:].sum()
    print(f"영모드 {k}: 왼끝 5사이트 가중치={left:.2f}, 오른끝 5사이트={right:.2f}")
# => 영모드가 사슬 양 끝에 국소화 (가운데엔 거의 0) = 비국소 페르미온 부호화
```

### 실험 3 — 브레이딩의 비가환성: $B_{12}B_{23}\neq B_{23}B_{12}$

```python
import numpy as np

# 4개 마요라나를 2x2 행렬(파울리)로 표현: γ1=σx, γ2=σy, γ3=σz⊗... 대신
# 2큐비트 표현으로 4 마요라나 구현
I = np.eye(2); X=np.array([[0,1],[1,0]]); Y=np.array([[0,-1j],[1j,0]]); Z=np.array([[1,0],[0,-1]])
def kron(*ops):
    out = np.array([[1]])
    for o in ops: out = np.kron(out, o)
    return out
# 자코비-위그너: γ1=X⊗I, γ2=Y⊗I, γ3=Z⊗X, γ4=Z⊗Y
g1 = kron(X, I); g2 = kron(Y, I); g3 = kron(Z, X); g4 = kron(Z, Y)
for g, name in [(g1,'γ1'),(g2,'γ2'),(g3,'γ3'),(g4,'γ4')]:
    assert np.allclose(g@g, np.eye(4))          # γ²=1
    assert np.allclose(g, g.conj().T)           # γ=γ† (에르미트)
def braid(ga, gb):
    return (np.eye(4) + ga@gb)/np.sqrt(2)       # B = (1+γaγb)/√2
B12 = braid(g1, g2); B23 = braid(g2, g3)
comm = B12@B23 - B23@B12
print("‖B12 B23 - B23 B12‖ =", np.round(np.linalg.norm(comm), 3))
print("=> 0이 아님: 브레이딩이 비가환 → 비아벨 통계 → 순서가 결과를 바꾼다")
```

## 🧪 실험·관측 증거

- **영바이어스 전도 피크**: InSb/NbTiN 나노선에서 마요라나 예측 위치(자기장·게이트)에 영바이어스 피크 출현(Mourik 외, *Science* 2012). 단, 안드레예프 구속 상태와의 구별이 진행 중인 논쟁.
- **$2e^2/h$ 양자화 추구**: 마요라나는 공명 안드레예프 반사로 정확히 $2e^2/h$ 피크를 예측. 일부 보고가 있었으나 재현·해석 논란(2018 *Nature* 논문 철회 사례 — 분야의 신중함을 보여줌).
- **와동 영모드**: $\text{FeTe}_{0.55}\text{Se}_{0.45}$ 와동 중심 STM 에서 영바이어스 피크·준입자 푸아송 통계 관측(Wang 외, 2018).
- **비국소성 측정**: 양 끝 동시 전도 상관(3단자 측정)으로 비국소성을 검증하려는 실험 진행 중. 브레이딩 비아벨 통계의 직접 실증은 아직 미달성.

## 🔬 경계

- **마요라나 vs 안드레예프 모방**: 무질서가 만든 준마요라나 안드레예프 구속 상태가 영바이어스 피크를 흉내내 마요라나로 오인되기 쉽다 — 분야의 핵심 난제. 양자화·비국소성·브레이딩의 3중 증거가 필요.
- **유한 길이 갈라짐**: 사슬이 짧으면 두 끝 마요라나가 겹쳐 $\delta E\sim e^{-L/\xi}\neq0$ — 큐비트 결맞음 제한.
- **준입자 중독(poisoning)**: 외부 페르미온이 들어와 패리티를 바꾸면 부호화 정보 손실. 위상 보호도 패리티 보존이 전제.
- **보편성 부족**: Ising 애니온 브레이딩은 클리퍼드 게이트만 — 보편 양자 계산엔 마법 상태 증류 등 비위상적 보충 필요. Fibonacci 애니온은 보편적이지만 실현이 더 어렵다.

## 🧬 횡단 원리

- **(→ quantum-information)**: 마요라나 큐비트·브레이딩 게이트는 위상 양자컴퓨팅의 하드웨어 보호 — [05](./05-topological-protection.md) 의 비국소 저장을 *계산* 으로 승격. 토릭 코드의 애니온과 같은 가족.
- **(→ standard-model)**: 마요라나 페르미온($\psi=\psi^c$)은 입자물리에서 중성미자 질량(시소 메커니즘)의 후보. 응집물질이 그 수학적 사촌을 실험실에서 구현.
- **(→ ch3 초전도)**: 마요라나는 BdG 초전도 준입자의 위상적 극단 — 쿠퍼 쌍 응축([../ch3-superconductivity-superfluid/03-bcs-theory.md](../ch3-superconductivity-superfluid/03-bcs-theory.md))이 p-파일 때 끝에 영모드를 남긴다.

## 🪜 창발

- **(L5 holography)**: 비국소적으로 부호화된 큐비트·위상 보호는 홀로그래피적 오류정정 부호와 같은 구조 — 경계의 국소 잡음이 벌크 정보를 못 건드림. 위상 양자 계산은 창발 시공간의 정보 처리 원형.
- **(L6 emergence)**: 전자조차 둘로 쪼개진 마요라나·순서가 결과를 바꾸는 통계 — 근본 입자·근본 통계가 다수의 얽힘에서 *재정의* 되는 창발의 극단. "More is Different" 가 양자 게이트로 결실.

## 📐 예측·반증

- **정량 예측**: 위상상($|\mu|<2t$)에서만 끝 마요라나, 영모드 갈라짐 $\delta E\sim e^{-L/\xi}$. 마요라나 공명 안드레예프 반사는 $G=2e^2/h$.
- **비아벨 예측**: 마요라나 4개로 만든 큐비트에서 브레이딩 순서를 바꾸면 측정 결과 분포가 *달라져야* 한다($B_{12}B_{23}\neq B_{23}B_{12}$).
- **반증 가능성**: 만약 영바이어스 피크가 마요라나라면 (i) 양 끝에서 상관되고, (ii) 위상상 경계($\mu=\pm2t$)에서 갭 닫힘과 함께 사라지며, (iii) 전도가 $2e^2/h$ 로 양자화돼야 한다. 이 셋이 동시에 안 나오면 안드레예프 모방으로 반증된다 — 분야가 현재 이 기준으로 검증 중.

## 🤔 다음 질문

마요라나·애니온은 *준입자* 가 분수 전하·비아벨 통계를 갖는 데까지 갔다. 그런데 더 근본적인 무언가 — *게이지장 그 자체* 가 다수에서 창발할 수 있을까? 스핀 액체에서 광자·U(1) 게이지장이 창발하면 "무엇이 근본인가" 가 역설이 된다. 다음 챕터에서 창발 게이지장으로 넘어간다.

---

🧩 **Principle** — 페르미온이 두 마요라나로 쪼개져 키타에프 사슬 양 끝에 짝 없는 영모드로 남고, 그것이 비국소 큐비트를 부호화하며 브레이딩이 비가환 유니터리 게이트를 구현한다.
🔬 **Boundary** — 안드레예프 모방·유한 길이 갈라짐·준입자 중독이 보호를 위협하고, Ising 브레이딩만으로는 보편 계산에 못 미쳐 비위상적 보충이 필요하다.
🪜 **Emergence** — 근본 입자·통계가 다수의 얽힘에서 재정의되는 이 구조는 위 레이어에서 홀로그래피적 오류정정·창발 시공간 정보 처리로 재등장하고, 위상상 영모드·$2e^2/h$·비가환 브레이딩으로 검증된다.

## 📝 연습문제

**1. (기초)** 복소 페르미온 $c=\tfrac12(\gamma_1+i\gamma_2)$ 에서 $\{\gamma_a,\gamma_b\}=2\delta_{ab}$, $\gamma_a^2=1$ 임을 $\{c,c^\dagger\}=1,\{c,c\}=0$ 로부터 직접 유도하라.

<details><summary>해설</summary>

$\gamma_1=c+c^\dagger,\ \gamma_2=-i(c-c^\dagger)$. 

$\gamma_1^2=(c+c^\dagger)^2=c^2+cc^\dagger+c^\dagger c+(c^\dagger)^2=0+\{c,c^\dagger\}+0=1$ (∵ $c^2=(c^\dagger)^2=0$, $\{c,c^\dagger\}=1$). 마찬가지로 $\gamma_2^2=-(c-c^\dagger)^2=-(c^2-cc^\dagger-c^\dagger c+(c^\dagger)^2)=-(-\{c,c^\dagger\})=1$. 

$\{\gamma_1,\gamma_2\}=\gamma_1\gamma_2+\gamma_2\gamma_1$. $\gamma_1\gamma_2=-i(c+c^\dagger)(c-c^\dagger)=-i(c^2-cc^\dagger+c^\dagger c-(c^\dagger)^2)=-i(c^\dagger c-cc^\dagger)$. $\gamma_2\gamma_1=-i(c-c^\dagger)(c+c^\dagger)=-i(cc^\dagger-c^\dagger c)$. 합 $=-i[(c^\dagger c-cc^\dagger)+(cc^\dagger-c^\dagger c)]=0$. 따라서 $\{\gamma_a,\gamma_b\}=2\delta_{ab}$. 두 마요라나는 클리퍼드 대수를 이룬다.
</details>

**2. (심화)** 키타에프 사슬 특수점($\mu=0,t=\Delta$)에서 사이트를 마요라나로 분해하면 $H=it\sum_{j=1}^{N-1}\gamma_{2j}\gamma_{2j+1}$ 가 됨을 보이고, 왜 $\gamma_1,\gamma_{2N}$ 이 영모드인지 설명하라.

<details><summary>해설</summary>

$c_j=\tfrac12(\gamma_{2j-1}+i\gamma_{2j})$ 대입. $\mu=0$ 이라 화학퍼텐셜 항 없음. 호핑+짝짓기: $-t(c_j^\dagger c_{j+1}+\text{h.c.})-\Delta(c_jc_{j+1}+\text{h.c.})$. $t=\Delta$ 일 때 정리하면 $c_j^\dagger c_{j+1}+c_jc_{j+1}+\text{h.c.}$ 의 마요라나 표현에서 $\gamma_{2j-1}$ 항이 상쇄되고 $\tfrac{i}{2}\cdot2t\,\gamma_{2j}\gamma_{2j+1}$ 만 남아 $H=it\sum_{j=1}^{N-1}\gamma_{2j}\gamma_{2j+1}$. 

이 합에는 $\gamma_2,\gamma_3,\dots,\gamma_{2N-1}$ 만 등장한다 — *왼쪽 끝* $\gamma_1$ 과 *오른쪽 끝* $\gamma_{2N}$ 은 어디에도 안 나타난다. 따라서 $[H,\gamma_1]=[H,\gamma_{2N}]=0$, 둘은 에너지 0(영모드). 둘이 비국소 페르미온 $c_M=\tfrac12(\gamma_1+i\gamma_{2N})$ 을 이루고 그 점유가 두 축퇴 바닥상태를 만든다. 위상상($|\mu|<2t$) 전역에서 영모드가 보존된다.
</details>

**3. (논문 비평)** 2012년 이후 여러 그룹이 나노선 영바이어스 피크를 마요라나 증거로 보고했으나, 2021년 한 *Nature* 논문이 철회되는 등 해석 논쟁이 이어졌다. "영바이어스 피크는 마요라나가 아닐 수 있다" 는 비판의 핵심은 무엇이며, 마요라나를 *결정적으로* 입증하려면 어떤 실험이 필요한가?

<details><summary>해설</summary>

비판의 핵심: 무질서·계면 효과가 만든 *준마요라나 안드레예프 구속 상태*(trivial ABS)가 마요라나와 똑같이 영바이어스 피크를 만들 수 있고, 심지어 $2e^2/h$ 근처 전도와 자기장 의존성까지 흉내낸다. 단일 단자 전도만으로는 위상적 마요라나와 비위상적 ABS 를 구별할 수 없다(국소 측정의 한계 — 마요라나의 본질은 *비국소성*인데 한 끝만 보고 있으니).

결정적 입증에 필요한 것: (1) **비국소 상관** — 3단자 측정으로 양 끝 마요라나가 *동시에* 나타나고 상관됨을 확인(한 끝 게이트 조작이 반대 끝에 반영); (2) **위상 갭 닫힘·재열림** — 위상 상전이 경계에서 벌크 갭이 닫히고 영모드가 그 경계를 가로질러 나타남; (3) **양자화된 $2e^2/h$** 의 안정적 재현; (4) 궁극적으로 **브레이딩의 비아벨 통계** — 두 마요라나 교환이 측정 가능한 비가환 변환을 일으킴(융합 규칙 측정). 분야가 단일 피크 보고에서 이 다중·비국소 기준으로 옮겨간 것은 위상물리 실험의 성숙을 보여준다 — 위상 보호의 *증거 기준* 자체가 위상적(비국소·전역)이어야 한다는 교훈.
</details>

---

<div align="center">

[◀ 이전: 위상 보호](./05-topological-protection.md)  ·  [📚 README](../README.md)  ·  [다음: 창발 게이지장 ▶](../ch5-emergent-gauge/01-emergent-gauge-field.md)

</div>
