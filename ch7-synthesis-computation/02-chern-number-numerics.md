# 천 수 계산 — 위상 불변량의 수치

> *베리 곡률 $\Omega(\mathbf{k})$ 는 운동량 공간 어디서나 매끈한 실수값이다. 그런데 그것을 브릴루앙 영역 전체에서 적분하면 — 매번, 정확히 — 정수가 나온다. 이 "연속에서 이산의 창발" 을 numpy 로 직접 목격한다.*

## 🎯 핵심 질문

- 2밴드 $\mathbf{d}(\mathbf{k})$ 모형(Qi–Wu–Zhang)의 채워진 밴드 베리 곡률을 적분한 천 수 $C=\frac{1}{4\pi}\int\hat{\mathbf{d}}\cdot(\partial_{k_x}\hat{\mathbf{d}}\times\partial_{k_y}\hat{\mathbf{d}})\,d^2k$ 가, 질량 $m$ 을 연속적으로 바꾸어도 *정수에서 정수로 점프* 만 하는가?
- 거친 격자에서 직접 미분으로 천 수를 구하면 게이지 임의성 때문에 정수에서 벗어나는데, Fukui–Hatsugai–Suzuki(FHS) 격자 게이지 불변 방법은 *왜* 거친 격자에서도 정확히 정수를 주는가?
- 천 수가 바뀌는 $m=0,\pm2$ 에서 무슨 일이 일어나는가 — 디랙 콘이 닫혔다 열리며 곡률 한 단위가 생성/소멸하는 위상 상전이를 코드로 어떻게 보나?

## 🌍 어디서 나타나나

- **정수 양자홀·천 절연체**: $\sigma_{xy}=C\,e^2/h$ 의 정수 $C$ 가 곧 채워진 밴드 천 수의 합(TKNN, → [../ch4-topological-matter/02-chern-number.md](../ch4-topological-matter/02-chern-number.md)).
- **양자 변칙홀 효과**: 자기장 없이도 $C\neq0$ — Cr 도핑 $(\text{Bi,Sb})_2\text{Te}_3$ 박막에서 $B=0$, $\sigma_{xy}=e^2/h$.
- **냉원자·광자/음향 천 밴드**: 인공 게이지장으로 천 수를 설계·측정. 일방향 가장자리 모드.
- **수치 위상물질학의 표준 도구**: FHS 방법은 실제 위상물질 코드(Z2Pack, WannierTools 등)의 천 수·Z2 계산 알고리즘의 핵심.

## 🔍 직관의 함정

**함정 1 — "곡률을 적분하면 정수가 나오는 건 정의상 당연하다."** 전혀. $\Omega(\mathbf{k})$ 자체는 임의의 실수값 함수다. 그것의 BZ 전체 적분이 *반드시* $2\pi$ 의 정수배가 되는 것은 토러스 위 $U(1)$ 다발의 천 정리라는 깊은 위상수학적 사실 — 코드를 돌려 매번 정수가 나오는 것을 보는 것은 그 정리를 눈으로 확인하는 일이다.

**함정 2 — "격자가 거칠면 천 수는 부정확할 수밖에 없다."** 직접 미분 방법은 그렇다(게이지 임의성이 곡률을 흔든다). 그러나 FHS 방법은 플라켓(작은 사각형)당 베리 위상을 게이지 불변하게 정의해, 거친 격자($N=20$)에서도 *정확히* 정수를 준다. 위상 불변량의 견고함이 알고리즘 수준에서 실현된다.

**함정 3 — "천 수의 부호는 물리적으로 의미 없다."** 부호는 카이럴리티 — 가장자리 모드가 도는 방향, 홀 전류의 방향을 결정한다. 다만 직접 미분과 FHS 가 부호 규약(고유벡터 위상 선택, 곡률 정의의 $\pm$)에 따라 전체 부호가 갈릴 수 있으므로, *상대적* 부호와 정수성에 주목한다.

## ⚙️ 제1원리 유도

### 1) 2밴드 모형 — 천 수가 $\hat{\mathbf{d}}$ 의 구 감김 수

임의의 2밴드 블로흐 해밀토니안은 파울리 행렬로

$$
H(\mathbf{k})=\mathbf{d}(\mathbf{k})\cdot\boldsymbol\sigma,\qquad E_\pm=\pm|\mathbf{d}|.
$$

채워진(아래) 밴드의 베리 곡률은 깔끔한 닫힌 형태(→ [../ch4-topological-matter/02-chern-number.md](../ch4-topological-matter/02-chern-number.md) 에서 유도):

$$
\Omega(\mathbf{k})=-\tfrac12\,\hat{\mathbf{d}}\cdot(\partial_{k_x}\hat{\mathbf{d}}\times\partial_{k_y}\hat{\mathbf{d}}),\qquad
\hat{\mathbf{d}}=\frac{\mathbf{d}}{|\mathbf{d}|}.
$$

따라서

$$
\boxed{C=\frac{1}{2\pi}\int_{\text{BZ}}\Omega\,d^2k=\frac{1}{4\pi}\int_{\text{BZ}}\hat{\mathbf{d}}\cdot(\partial_{k_x}\hat{\mathbf{d}}\times\partial_{k_y}\hat{\mathbf{d}})\,d^2k.}\quad\square
$$

이 적분은 정확히 사상 $\hat{\mathbf{d}}:T^2\to S^2$ 가 단위 구를 **몇 번 감싸는가(degree)** — 토폴로지가 정수를 강제한다.

### 2) Qi–Wu–Zhang 모형 — 위상 상전이의 최소 무대

$$
\mathbf{d}(\mathbf{k})=(\sin k_x,\ \sin k_y,\ m+\cos k_x+\cos k_y).
$$

갭 $|\mathbf{d}|$ 이 닫히는 곳: $\sin k_x=\sin k_y=0$ 이고 $m+\cos k_x+\cos k_y=0$. 고대칭점에서

- $(0,0)$: $m+2=0\Rightarrow m=-2$,
- $(\pi,\pi)$: $m-2=0\Rightarrow m=2$,
- $(\pi,0),(0,\pi)$: $m=0$.

이 세 값 사이에서 천 수는

$$
\boxed{C=\begin{cases}0 & |m|>2\\ +1 & -2<m<0\\ -1 & 0<m<2\end{cases}}\quad\square
$$

(부호는 곡률 정의의 규약에 의존; 핵심은 $|m|>2$ 자명, $0<|m|<2$ 위상.) 질량을 연속적으로 줄여도 천 수는 정수 점프만 한다 — 갭이 닫히는 순간에만.

### 3) Fukui–Hatsugai–Suzuki — 격자 게이지 불변 천 수

연속 적분을 격자에서 흉내 낼 때 직접 미분은 고유벡터의 임의 위상(게이지)에 오염된다. FHS 는 **링크 변수** 를 정의한다:

$$
U_\mu(\mathbf{k})=\frac{\langle u(\mathbf{k})|u(\mathbf{k}+\hat\mu)\rangle}{|\langle u(\mathbf{k})|u(\mathbf{k}+\hat\mu)\rangle|},
$$

각 플라켓(작은 사각형) 둘레의 링크 곱의 편각을 그 플라켓의 베리 곡률(필드 세기)로 삼는다:

$$
F_{12}(\mathbf{k})=\arg\big[U_1(\mathbf{k})\,U_2(\mathbf{k}+\hat1)\,U_1(\mathbf{k}+\hat2)^{-1}\,U_2(\mathbf{k})^{-1}\big]\in(-\pi,\pi].
$$

게이지 위상이 인접 링크에서 상쇄되므로 $F_{12}$ 는 게이지 불변. 천 수는

$$
\boxed{C=\frac{1}{2\pi}\sum_{\text{plaquettes}}F_{12}(\mathbf{k})\in\mathbb{Z}\ (\text{격자에서 정확히 정수}).}\quad\square
$$

$\arg$ 가 자동으로 $2\pi$ 가지치기(branch)를 처리해, 거친 격자에서도 윈딩이 정수로 떨어진다. 이것이 FHS 의 마법이다.

### 실험 1 — QWZ 천 수: 직접 베리 곡률 적분

```python
import numpy as np

def d_vector(kx, ky, m):
    """QWZ 2밴드: d = (sin kx, sin ky, m + cos kx + cos ky)."""
    return np.array([np.sin(kx), np.sin(ky), m + np.cos(kx) + np.cos(ky)])

def chern_direct(m, N=200):
    """C = (1/4π) ∫ d̂·(∂x d̂ × ∂y d̂) d²k — d̂ 의 구 감김 수(직접 미분)."""
    ks = np.linspace(-np.pi, np.pi, N, endpoint=False)
    dk = ks[1] - ks[0]
    C = 0.0
    for kx in ks:
        for ky in ks:
            d  = d_vector(kx, ky, m)
            dx = (d_vector(kx+dk, ky, m) - d) / dk     # ∂x d
            dy = (d_vector(kx, ky+dk, m) - d) / dk     # ∂y d
            n  = np.linalg.norm(d)
            C += np.dot(d/n, np.cross(dx, dy)) / n**2  # d̂·(∂d×∂d)/|d|²
    return C * dk*dk / (4*np.pi)

print("직접 베리 곡률 적분:")
for m in [-3.0, -1.0, 1.0, 3.0]:
    print(f"  m={m:+.1f}  →  C ≈ {chern_direct(m):+.3f}")
# |m|>2 → 0 (자명),  -2<m<0 → +1,  0<m<2 → -1 (또는 부호 규약상 반대)
```

출력: $m=\pm3$ 에서 $C\approx0$, $m=\mp1$ 에서 $C\approx\pm1$. 직접 미분도 격자가 충분히 고우면($N=200$) 정수에 매우 가깝게 수렴.

### 실험 2 — FHS 방법: 거친 격자에서도 정확한 정수

```python
import numpy as np

def H_qwz(kx, ky, m):
    sx = np.array([[0,1],[1,0]], complex)
    sy = np.array([[0,-1j],[1j,0]], complex)
    sz = np.array([[1,0],[0,-1]], complex)
    return np.sin(kx)*sx + np.sin(ky)*sy + (m+np.cos(kx)+np.cos(ky))*sz

def lower_band(kx, ky, m):
    w, v = np.linalg.eigh(H_qwz(kx, ky, m))
    return v[:, 0]                       # 채워진 밴드 고유벡터

def chern_fhs(m, N=20):
    """FHS 링크 변수 — 거친 격자(N=20)에서도 정확히 정수."""
    ks = np.linspace(-np.pi, np.pi, N, endpoint=False)
    U = np.empty((N, N, 2), complex)
    for i, kx in enumerate(ks):
        for j, ky in enumerate(ks):
            U[i, j] = lower_band(kx, ky, m)
    F_total = 0.0
    for i in range(N):
        for j in range(N):
            ip, jp = (i+1) % N, (j+1) % N
            # 플라켓 둘레 링크 곱의 편각 = 게이지 불변 베리 곡률
            U1 = np.vdot(U[i,j],   U[ip,j])
            U2 = np.vdot(U[ip,j],  U[ip,jp])
            U3 = np.vdot(U[ip,jp], U[i,jp])
            U4 = np.vdot(U[i,jp],  U[i,j])
            F_total += np.angle(U1*U2*U3*U4)
    return F_total / (2*np.pi)

print("FHS 방법 (N=20, 거친 격자):")
for m in [-3.0, -1.0, 1.0, 3.0]:
    print(f"  m={m:+.1f}  →  C (FHS) = {chern_fhs(m):+.4f}")
# 거친 격자에서도 정확히 0, ±1 — 위상 불변량의 견고함이 알고리즘에 반영됨
```

출력: $N=20$ 의 거친 격자에서도 $C$ 가 정확히 $0,\pm1$. 직접 미분(실험 1)이 $N=200$ 을 요구한 정수성을 FHS 는 $N=20$ 에서 정확히 달성한다.

### 실험 3 — $m$ 스캔: 위상 상전이의 정수 점프

```python
import numpy as np
import matplotlib.pyplot as plt

# (실험 2의 H_qwz, lower_band, chern_fhs 재사용 가정)
ms = np.linspace(-3.5, 3.5, 71)
Cs = [chern_fhs(m, N=24) for m in ms]

# 갭(최소 |d|)도 함께: 천 수 점프와 갭 닫힘이 같은 m 에서 일어나는지 확인
def min_gap(m, N=200):
    ks = np.linspace(-np.pi, np.pi, N, endpoint=False)
    g = np.inf
    for kx in ks:
        for ky in ks:
            d = np.array([np.sin(kx), np.sin(ky), m+np.cos(kx)+np.cos(ky)])
            g = min(g, 2*np.linalg.norm(d))   # 갭 = 2|d|
    return g

gaps = [min_gap(m, N=120) for m in ms]

fig, ax1 = plt.subplots(figsize=(7,4))
ax1.step(ms, Cs, where='mid', color='C0', label='Chern C')
ax1.set_xlabel("m"); ax1.set_ylabel("Chern number C", color='C0')
ax1.axhline(0, ls=':', c='gray')
ax2 = ax1.twinx()
ax2.plot(ms, gaps, 'C3--', label='gap')
ax2.set_ylabel("band gap", color='C3')
for mc in [-2, 0, 2]:
    ax1.axvline(mc, ls=':', c='k', alpha=0.4)   # 갭 닫힘 = 천 수 점프
plt.title("QWZ: 천 수 점프 ↔ 갭 닫힘 (m=0,±2)")
plt.tight_layout(); plt.savefig("chern_transition.png", dpi=110)

# 점프 위치 출력
Cs = np.array(Cs)
jumps = ms[:-1][np.abs(np.diff(Cs)) > 0.5]
print("천 수 점프 위치 m ≈", np.round(jumps, 2))
print("→ 갭이 닫히는 m=0,±2 와 일치")
```

출력: 천 수가 $m\approx-2,0,2$ 에서만 점프하고, 정확히 그 점에서 갭이 0으로 닫힌다. 위상 상전이는 *반드시* 갭 닫힘을 동반한다.

## 🧪 실험·관측 증거

- **양자 변칙홀 효과**: $B=0$ 에서 $\sigma_{xy}=Ce^2/h$, $C=1$ 관측(Chang 외 2013) — 천 수가 자기장 없이 양자화를 만든다는 직접 증거.
- **냉원자 천 수 측정**: 광격자 반홀 변위로 $C=1$ 직접 측정(Aidelsburger 외 2015, Jotzu 외 2014).
- **광자/음향 위상 절연체**: 천 밴드의 일방향 가장자리 모드가 결함을 우회 — 천 수의 벌크–경계 대응 시연.
- **수치 검증**: 모든 알려진 사례에서 양자홀 고원 정수 = 채워진 밴드 천 수 합. FHS 가 위상물질 코드의 표준 알고리즘으로 광범위 재현.

## 🔬 경계

- **갭 닫힘에서 정의 불가**: $m=0,\pm2$ 에서 천 수는 정의되지 않고 정수 점프만 한다. 갭이 닫혀 있으면 적분 자체가 발산/불연속.
- **시간역전 보존계**: 시간역전 대칭이면 $C=0$ 이 강제됨. 그 경우 $\mathbb{Z}_2$ 불변량이 필요(→ [../ch4-topological-matter/04-topological-insulator.md](../ch4-topological-matter/04-topological-insulator.md)).
- **상호작용 강한 경우**: 단일입자 밴드 천 수는 약상관에서만. 분수 양자홀에서는 다체 천 수가 분수가 될 수 있다(→ [../ch4-topological-matter/03-fractional-quantum-hall.md](../ch4-topological-matter/03-fractional-quantum-hall.md)).
- **다밴드·축퇴**: 밴드가 축퇴되면 비아벨 베리 곡률(행렬값)이 필요. FHS 는 채워진 부분공간 전체의 행렬식으로 일반화해야 한다.

## 🧬 횡단 원리

- **(→ standard-model)**: 천 수는 게이지장 위상 전하($\int F$)와 같은 수학 — 자기 단극·인스탄톤 양자화와 동일 구조. $\hat{\mathbf{d}}$ 감김 수 = 비선형 시그마 모형의 위상 항.
- **(→ quantum-information)**: 정수성·견고함이 위상 양자 메모리가 국소 잡음에 견디는 이유(→ [../ch4-topological-matter/05-topological-protection.md](../ch4-topological-matter/05-topological-protection.md)).
- **(→ symmetry-conservation)**: 베리 위상은 단열 불변량 — 대칭과 보존량의 기하학적 일반화. 아하로노프–봄 위상의 운동량 공간판.

## 🪜 창발

- **(L5 holography)**: 벌크 천 수 = 가장자리 카이럴 CFT 중심전하라는 대응은 벌크가 경계를 강제하는 홀로그래피의 응집물질 원형.
- **(L6 emergence)**: 매끈한 실수 곡률 $\Omega(\mathbf{k})$ 에서 *정수* $C$ 가 창발하는 구조 — 연속에서 이산, 국소에서 전역. FHS 의 $\arg$ 가지치기는 그 창발을 알고리즘으로 구현한다.

## 📐 예측·반증

- **정량 예측**: QWZ 에서 $-2<m<0$ 이면 $|C|=1$, $0<m<2$ 면 $|C|=1$(반대 부호), $|m|>2$ 면 $C=0$. 점프는 $m=0,\pm2$ 에서만.
- **반증 가능성**: 천 절연체에서 $B=0$ 양자화가 정수 $e^2/h$ 의 배수가 *아니라면* TKNN 이 틀린 것 — 실측은 정확히 정수배.
- **수치 검증**: FHS 가 $N=20$ 거친 격자에서 $C$ 를 정수로 재현해야 한다(실험 2 확증). 천 수 점프 ↔ 갭 닫힘 일치(실험 3 확증).

## 🤔 다음 질문

천 수는 *단일입자 밴드* 의 위상이었다. 이제 시선을 상호작용으로 돌린다. 포논 매개 인력이 페르미면을 불안정하게 만들면 쿠퍼 쌍이 응축하고 에너지 갭 $\Delta$ 가 자기일관적으로 열린다. 다음 문서에서 BCS 갭 방정식 $1=g\sum_k\frac{1}{2E_k}\tanh\frac{E_k}{2k_BT}$ 를 반복 수렴으로 풀어 $\Delta(T)$ 곡선·$T_c$, 그리고 보편비 $\Delta(0)/k_BT_c\approx1.764$ 를 numpy 로 직접 확인한다.

---

🧩 **Principle** — 매끈한 실수 베리 곡률을 BZ 토러스 전체에서 적분한 천 수는 $\hat{\mathbf{d}}:T^2\to S^2$ 의 구 감김 수라 정수이고, 질량을 연속으로 바꾸어도 갭이 닫히는 점에서만 정수 점프한다.
🔬 **Boundary** — 갭 닫힘에서 정의 불가, 시간역전 보존이면 $C=0$, 강상관·축퇴에서는 다체/비아벨 천 수가 필요하다.
🪜 **Emergence** — 연속에서 이산이 창발하는 이 구조는 위 레이어에서 벌크–경계 홀로그래피·위상 메모리로 재등장하고, FHS 가 거친 격자에서 정수를 재현함으로써 검증된다.

## 📝 연습문제

**1. (기초)** QWZ 모형에서 갭 $|\mathbf{d}|$ 이 닫히는 $\mathbf{k}$ 점과 그때의 $m$ 값을 모두 찾아라($m=-2,0,+2$ 각각에서). 이 세 값이 천 수의 점프 위치와 같음을 설명하라.

<details><summary>해설</summary>

$|\mathbf{d}|=0$ 은 $\sin k_x=\sin k_y=0$(즉 $k_{x,y}\in\{0,\pi\}$)이고 $m+\cos k_x+\cos k_y=0$. 네 고대칭점: $(0,0)\Rightarrow m=-2$; $(\pi,\pi)\Rightarrow m=+2$; $(\pi,0)$ 과 $(0,\pi)\Rightarrow m=0$(두 점 동시). 각 점에서 디랙 콘이 닫혔다 열리며 베리 곡률 한 단위($\pm1$)가 생성/소멸 → 천 수가 정수 점프. 갭이 닫히지 않으면 $C$ 는 연속 변형 불변량이므로 바뀔 수 없다 — 따라서 갭 닫힘은 위상 상전이의 필요조건이고, 그래서 점프 위치 = 갭 닫힘 위치다.
</details>

**2. (심화)** FHS 방법에서 플라켓 베리 곡률 $F_{12}=\arg[U_1 U_2 U_3 U_4]$ 가 게이지 변환 $|u(\mathbf{k})\rangle\to e^{i\phi(\mathbf{k})}|u(\mathbf{k})\rangle$ 하에서 불변임을 보여라. 또 왜 $\arg$ 가 천 수의 정수성을 자동으로 보장하는지 설명하라.

<details><summary>해설</summary>

게이지 변환 시 각 링크 $U_\mu(\mathbf{k})\propto\langle u(\mathbf{k})|u(\mathbf{k}+\hat\mu)\rangle\to e^{-i\phi(\mathbf{k})}e^{i\phi(\mathbf{k}+\hat\mu)}\langle\cdots\rangle$. 플라켓을 한 바퀴 돌면 각 꼭짓점에서 $e^{+i\phi}$ 와 $e^{-i\phi}$ 가 정확히 한 번씩 나타나 모두 상쇄 → $U_1U_2U_3U_4$ 는 게이지 불변, 따라서 $F_{12}$ 도 불변. 정수성: $\arg$ 는 항상 $(-\pi,\pi]$ 로 주값을 잡으므로, 전체 합 $\sum F_{12}$ 는 각 플라켓의 "감긴" 베리 위상에서 $2\pi$ 의 정수배 모호성을 자동 제거한다. 닫힌 토러스에서 모든 링크가 두 플라켓에 공유되어 내부 기여가 상쇄되고, 남는 것은 전역 윈딩 = $2\pi\times$정수. 그래서 $C=\frac1{2\pi}\sum F_{12}$ 가 격자에서도 정확히 정수.
</details>

**3. (논문 비평)** Fukui–Hatsugai–Suzuki(2005)의 방법은 단일 비축퇴 밴드를 가정한다. 실제 위상 절연체는 다밴드·스핀 축퇴·시간역전 보존($\mathbb{Z}_2$)이 흔하다. 비아벨(다밴드) 천 수와 $\mathbb{Z}_2$ 불변량 계산에서 FHS 를 어떻게 일반화해야 하는지, 그리고 게이지 불변성을 유지하는 데 어떤 어려움이 있는지 논하라.

<details><summary>해설</summary>

다밴드: 링크 변수를 스칼라 겹침이 아니라 채워진 부분공간 사이의 *겹침 행렬* $M_\mu(\mathbf{k})_{mn}=\langle u_m(\mathbf{k})|u_n(\mathbf{k}+\hat\mu)\rangle$ 로 바꾸고, 플라켓 둘레의 행렬 곱의 *행렬식의 편각* 을 곡률로 삼는다($U(N)$ 비아벨 윌슨 루프). 이때 부분공간 회전(비아벨 게이지)에 불변. $\mathbb{Z}_2$: 시간역전 보존계는 $C=0$ 이므로 천 수가 무용 — 대신 시간역전 짝(Kramers pair)의 부분 윈딩 또는 Wilson 루프 스펙트럼(혼성 Wannier 중심)의 교환 패리티를 본다(Fukui–Hatsugai 2007, Soluyanov–Vanderbilt). 어려움: (a) Kramers 축퇴에서 게이지를 시간역전 대칭하게 고정해야 $\mathbb{Z}_2$ 가 잘 정의됨, (b) 행렬식 편각의 $2\pi$ 가지치기가 다밴드에서 더 미묘, (c) 첫원리(DFT) 파동함수의 임의 위상·밴드 교차에서 수치 안정성. 그래서 실무에서는 혼성 Wannier 중심의 연속적 흐름(Wilson 루프 흐름)을 추적하는 방식이 더 견고하다 — 이는 정수/패리티 불변량을 게이지 불변하게, 밴드 교차에도 강건하게 읽어낸다.
</details>

---

<div align="center">

[◀ 이전: 밴드 구조 계산](./01-band-structure.md)  ·  [📚 README](../README.md)  ·  [다음: BCS 갭 방정식 ▶](./03-bcs-gap-equation.md)

</div>
