# 허바드/이징 다체 — 정확 대각화

> *평균장이 깨지는 곳에서는 정직한 길밖에 없다 — 전체 힐베르트 공간을 통째로 대각화하는 것. 4 사이트 허바드 행렬을 scipy.sparse 로 풀면, 밴드 이론이 놓치는 모트 갭이 $U$ 와 함께 열리고 스핀이 반강자성으로 정렬되는 강상관의 맛을, 근사 없이 직접 본다.*

## 🎯 핵심 질문

- 점유수(occupation number) 기저에서 허바드 해밀토니안 $H=-t\sum c^\dagger c+U\sum n_\uparrow n_\downarrow$ 을 어떻게 페르미온 부호까지 정확히 행렬로 짜고, 작은 격자(2~4 사이트)에서 *전체* 스펙트럼을 얻나?
- 밴드 이론은 반쯤 채운 격자를 항상 *금속* 이라 하는데, 왜 허바드 $U$ 가 충분히 크면 똑같은 격자가 *절연체*(모트)가 되는가 — 전하 갭이 $U$ 와 함께 어떻게 열리나?
- 같은 바닥상태에서 이웃 스핀 상관 $\langle S^z_iS^z_j\rangle$ 이 $U$ 와 함께 음(반강자성)으로 깊어지는 것, 그리고 횡자기장 이징의 양자 상전이를 정확 대각화로 어떻게 보나?

## 🌍 어디서 나타나나

- **모트 절연체**: $\text{La}_2\text{CuO}_4$ 등 강상관 산화물 — 밴드 이론은 금속이라 예측하나 실제는 절연체. 허바드 $U$ 가 원인(→ [../ch6-quantum-phase-correlation/03-mott-insulator.md](../ch6-quantum-phase-correlation/03-mott-insulator.md)).
- **고온 초전도 모(母)물질**: 도핑된 허바드/t–J 모형이 구리 산화물 초전도의 출발점.
- **냉원자 광격자**: 허바드 모형을 *그대로* 양자 시뮬레이션 — 모트 절연체–초유체 전이를 직접 관측.
- **횡자기장 이징**: 양자 상전이의 정준 모형. 양자 어닐링·D-Wave 하드웨어의 기본 해밀토니안.

## 🔍 직관의 함정

**함정 1 — "반쯤 채우면 무조건 금속이다."** 밴드 이론(단일입자)의 결론이다. 그러나 두 전자가 같은 자리에 오면 $U$ 의 벌금이 붙어 — $U\gg t$ 면 전자들이 자리당 하나씩 *얼어붙어* 도약을 못 한다. 같은 밴드 채움에도 절연체. 상호작용이 만드는 절연체가 모트다.

**함정 2 — "정확 대각화는 큰 계도 풀 수 있다."** 힐베르트 공간이 사이트 수에 *지수적* 으로 커진다($4^L$ for 허바드). 4 사이트면 256, 16 사이트면 ~$4\times10^9$ — 한계가 빠르다. 그래서 "작은 격자의 정확한 맛보기" 다. 큰 계는 QMC·DMRG·텐서망 필요(→ [../ch6-quantum-phase-correlation/05-strong-correlation-frontier.md](../ch6-quantum-phase-correlation/05-strong-correlation-frontier.md)).

**함정 3 — "페르미온 부호는 무시해도 된다."** 절대 안 된다. 전자는 반대칭이라 도약 시 사이에 낀 전자 수의 패리티만큼 부호가 붙는다($(-1)^{\#}$). 이 Jordan–Wigner 부호를 빠뜨리면 스펙트럼이 통째로 틀린다.

## ⚙️ 제1원리 유도

### 1) 허바드 모형 — 도약과 자리 반발의 경쟁

$$
\boxed{H=-t\sum_{\langle ij\rangle,\sigma}\big(c^\dagger_{i\sigma}c_{j\sigma}+\text{h.c.}\big)+U\sum_i n_{i\uparrow}n_{i\downarrow}.}
$$

$t$: 비국소화(운동에너지)를 선호 → 금속. $U$: 이중점유를 벌금 → 국소화(절연체). 이 둘의 경쟁이 모트 전이의 본질. $U/t$ 가 유일한 무차원 제어변수.

### 2) 점유수 기저와 페르미온 부호

각 사이트는 $\{|0\rangle,|\uparrow\rangle,|\downarrow\rangle,|\uparrow\downarrow\rangle\}$. $L$ 사이트면 차원 $4^L$. 스핀별 점유를 비트마스크로 표현. 도약 $c^\dagger_j c_i$ 는

$$
c^\dagger_j c_i|\cdots\rangle=(-1)^{\sum_{i<l<j}n_l}|\cdots\rangle\ (\text{사이에 낀 입자 수 패리티}).
$$

이 부호가 페르미 통계의 핵심. 보존량($N_\uparrow,N_\downarrow$, 총 $S^z$)으로 블록 대각화해 차원을 줄인다.

### 3) 2 사이트 — 손으로 푸는 검증대

반충전(↑ 하나, ↓ 하나) 2 사이트는 4차원 부분공간. 정확한 바닥상태 에너지

$$
\boxed{E_0=\frac{U-\sqrt{U^2+16t^2}}{2}.}\quad\square
$$

$U=0$: $E_0=-2t$(완전 비국소화). $U\to\infty$: $E_0\to-4t^2/U$(초교환 $J=4t^2/U$ 의 반강자성). 코드가 이 해석해를 재현해야 한다.

### 4) 모트 갭 — 전하 들뜸의 비용

전하(모트) 갭은 전자 하나 더하고 빼는 비용:

$$
\boxed{\Delta_c=E_0(N+1)+E_0(N-1)-2E_0(N).}\quad\square
$$

$U=0$ 이면 밴드 채움의 띠틈만(작은 격자에선 유한). $U\gg t$ 면 $\Delta_c\approx U$ — 이중점유를 만드는 비용. 밴드 이론이 못 보는 절연체 갭이 $U$ 와 함께 자란다.

### 5) 횡자기장 이징 — 양자 상전이의 정준 모형

$$
\boxed{H=-J\sum_i\sigma^z_i\sigma^z_{i+1}-g\sum_i\sigma^x_i.}
$$

$g\ll J$: $\sigma^z$ 정렬(강자성, 이중축퇴 바닥). $g\gg J$: $\sigma^x$ 정렬(상자성, 유일 바닥). $g=J$ 에서 양자 임계점 — 갭이 닫힌다(무한계). 작은 계에서도 갭 최소가 임계점 신호.

### 실험 1 — 2 사이트 허바드: 정확 대각화 vs 해석해

```python
import numpy as np
from scipy.sparse import lil_matrix, csr_matrix
from itertools import combinations

def hubbard_H(L, t, U, Nup, Ndn, pbc=False):
    """점유수(비트마스크) 기저 허바드 H — 페르미온 부호 포함."""
    up = [sum(1<<i for i in c) for c in combinations(range(L), Nup)] if Nup>0 else [0]
    dn = [sum(1<<i for i in c) for c in combinations(range(L), Ndn)] if Ndn>0 else [0]
    idx, basis = {}, []
    for a in up:
        for b in dn:
            idx[(a,b)] = len(basis); basis.append((a,b))
    H = lil_matrix((len(basis), len(basis)))
    bonds = [(i,(i+1)%L) for i in range(L if pbc else L-1)]
    for n,(a,b) in enumerate(basis):
        H[n,n] += U * bin(a & b).count("1")          # 이중점유 에너지
        for mask, spin in [(a,'u'),(b,'d')]:
            for (i,j) in bonds:
                for (s,d) in [(i,j),(j,i)]:           # 양방향 도약
                    if (mask>>s)&1 and not (mask>>d)&1:
                        new = (mask & ~(1<<s)) | (1<<d)
                        lo, hi = min(s,d), max(s,d)
                        between = bin(mask & (((1<<hi)-1) & ~((1<<(lo+1))-1))).count("1")
                        sign = (-1)**between          # Jordan–Wigner 부호
                        key = (new,b) if spin=='u' else (a,new)
                        H[n, idx[key]] += -t * sign
    return csr_matrix(H)

print("2 사이트 반충전 (↑1, ↓1):")
for U in [0.0, 2.0, 4.0, 8.0]:
    H = hubbard_H(2, 1.0, U, 1, 1, pbc=False)
    E0 = np.linalg.eigvalsh(H.toarray())[0]
    E0_an = (U - np.sqrt(U**2 + 16))/2
    print(f"  U={U:>4.1f}:  수치 E0={E0:+.5f}   해석해={E0_an:+.5f}")
# 수치와 해석해가 완전 일치 — 페르미온 부호·기저 구성이 정확
```

출력: 모든 $U$ 에서 수치 $E_0$ 가 해석해 $(U-\sqrt{U^2+16})/2$ 와 정확히 일치. 부호 처리가 옳음을 확증.

### 실험 2 — 4 사이트 허바드: 모트 갭이 $U$ 와 함께 열린다

```python
import numpy as np
# (실험 1의 hubbard_H 재사용)

def gs_energy(L, U, Nup, Ndn, pbc=True):
    H = hubbard_H(L, 1.0, U, Nup, Ndn, pbc)
    return np.linalg.eigvalsh(H.toarray())[0]

print("4 사이트 PBC 반충전 모트(전하) 갭 Δc = E0(N+1)+E0(N-1)-2E0(N):")
Us, gaps = [], []
for U in [0, 1, 2, 4, 6, 8, 12]:
    EN = gs_energy(4, U, 2, 2)     # 반충전 (↑2, ↓2)
    Ep = gs_energy(4, U, 3, 2)     # 전자 하나 추가
    Em = gs_energy(4, U, 1, 2)     # 전자 하나 제거
    dc = Ep + Em - 2*EN
    Us.append(U); gaps.append(dc)
    print(f"  U={U:>3}:  Δc = {dc:.4f}")
# U=0: 갭 ≈ 0 (금속),  U 증가 → 갭 선형 성장 (Δc ≈ U - O(t)),  모트 절연체
print("\n큰 U 점근: Δc ≈ U (이중점유 비용) →", gaps[-1], "vs U=12")
```

출력: $U=0$ 에서 갭 $\approx0$(금속), $U$ 가 커지면 갭이 선형으로 성장($\Delta_c\approx U$ 점근). 밴드 이론이 금속이라 우기는 격자가 상호작용 때문에 절연체가 된다 — 모트 갭을 직접 본다.

### 실험 3 — 반강자성 스핀 상관

```python
import numpy as np
from itertools import combinations
# (실험 1의 hubbard_H 재사용)

def nn_spin_corr(L, U, i, j, pbc=True):
    """반충전 바닥상태에서 <S^z_i S^z_j>."""
    up = [sum(1<<x for x in c) for c in combinations(range(L), L//2)]
    dn = up
    idx, basis = {}, []
    for a in up:
        for b in dn:
            idx[(a,b)] = len(basis); basis.append((a,b))
    H = hubbard_H(L, 1.0, U, L//2, L//2, pbc).toarray()
    w, v = np.linalg.eigh(H)
    gs = v[:, 0]
    corr = 0.0
    for n,(a,b) in enumerate(basis):
        szi = 0.5*(((a>>i)&1) - ((b>>i)&1))   # S^z = (n↑-n↓)/2
        szj = 0.5*(((a>>j)&1) - ((b>>j)&1))
        corr += abs(gs[n])**2 * szi * szj
    return corr

print("4 사이트 최근접 스핀 상관 <Sz_0 Sz_1> (반강자성이면 음수):")
for U in [0, 2, 4, 8, 12]:
    c = nn_spin_corr(4, U, 0, 1)
    print(f"  U={U:>3}:  <Sz0 Sz1> = {c:+.4f}")
# U=0: 0 (무상관),  U 증가 → 음으로 깊어짐 (이웃 스핀 반평행 선호)
# → 초교환 J=4t²/U 가 만드는 반강자성, 밴드 이론엔 없는 강상관 효과
```

출력: $U=0$ 에서 상관 0(무상관), $U$ 증가 시 음으로 깊어짐 — 이웃 스핀이 반평행을 선호하는 반강자성. 초교환 $J=4t^2/U$ 가 만드는 강상관 효과를 정확 대각화로 목격.

### 실험 4 — 횡자기장 이징의 양자 상전이

```python
import numpy as np

def tfim_H(L, J, g, pbc=True):
    """H = -J Σ σz σz - g Σ σx  (스핀-1/2, 전체 대각화)."""
    sx = np.array([[0,1],[1,0]]); sz = np.array([[1,0],[0,-1]]); I = np.eye(2)
    def op(o, site):
        m = np.array([[1.0]])
        for k in range(L):
            m = np.kron(m, o if k==site else I)
        return m
    H = np.zeros((2**L, 2**L))
    nb = L if pbc else L-1
    for i in range(nb):
        H += -J * op(sz, i) @ op(sz, (i+1) % L)
    for i in range(L):
        H += -g * op(sx, i)
    return H

print("횡자기장 이징 (L=8): 두 갭의 거동으로 임계점 진단")
gs = np.linspace(0.0, 2.0, 21)
print(f"{'g':>5} {'E0':>9} {'갭1(E1-E0)':>12} {'갭2(E2-E0)':>12}")
for g in gs[::2]:
    w = np.linalg.eigvalsh(tfim_H(8, 1.0, g))
    gap1 = w[1] - w[0]      # 강자성 이중축퇴의 분열 (g<1 에서 지수적으로 작음)
    gap2 = w[2] - w[0]      # 대칭 섹터 들뜸 갭 — 임계점에서 최소(∝1/L)
    print(f"{g:>5.1f} {w[0]:>9.3f} {gap1:>12.4f} {gap2:>12.4f}")
# 갭1: g<1 강자성에서 두 대칭깨짐 상태가 거의 축퇴(갭1→0), g>1 상자성에서 큼
# 갭2(대칭 섹터 들뜸): g≈1 임계점 부근에서 최소 — 유한계의 양자 임계점 신호
```

출력: 갭1(이중축퇴 분열)은 강자성($g<1$)에서 지수적으로 작고 상자성($g>1$)에서 커진다. 대칭 섹터 들뜸 갭2 는 임계점 $g\approx1$ 부근에서 최소가 되어 — 유한 계에서 본 양자 임계점의 신호다(무한계에서 정확히 0으로 닫힘). 무한 사슬에서는 $g=J$ 가 정확한 양자 상전이점.

## 🧪 실험·관측 증거

- **모트 절연체**: $\text{La}_2\text{CuO}_4$ 등이 밴드 이론 예측(금속)과 달리 절연체 — 허바드 $U$ 의 직접 증거. 광전도도에서 모트 갭 $\sim2$ eV 관측.
- **냉원자 허바드**: 광격자에서 모트–초유체 전이를 밀도 측정으로 직접 관측(Greiner 외 2002). 반강자성 상관도 측정(Mazurenko 외 2017).
- **중성자 산란**: 모(母)물질의 반강자성 스핀 상관 — 초교환 $J=4t^2/U$ 예언과 일치.
- **양자 시뮬레이터**: 횡자기장 이징의 양자 상전이를 이온 트랩·초전도 큐비트로 재현.

## 🔬 경계

- **지수 장벽**: 힐베르트 공간 $4^L$ — 정확 대각화는 ~16~20 사이트가 한계. 열역학 극한·임계지수에는 부족.
- **유한 크기 효과**: 작은 격자는 진짜 상전이가 없다(갭이 정확히 0 안 됨). 임계점은 *최소 갭·교차* 로만 추정. 스케일링 외삽 필요.
- **부호 문제**: 도핑된 허바드의 QMC 는 페르미온 부호 문제로 막힘(→ [../ch6-quantum-phase-correlation/05-strong-correlation-frontier.md](../ch6-quantum-phase-correlation/05-strong-correlation-frontier.md)). 정확 대각화는 부호 문제는 없지만 크기 한계.
- **모형 자체의 한계**: 단일밴드 허바드는 실제 물질의 다궤도·긴거리 쿨롱·전자–포논을 단순화. 정성 골격이지 정량 정답 아님.

## 🧬 횡단 원리

- **(→ symmetry-conservation)**: 보존량($N_\sigma$, $S^z$)으로 블록 대각화 — 대칭이 계산을 *지수적으로* 줄인다. 대칭과 보존량의 실용적 위력.
- **(→ quantum-information)**: 정확 대각화 바닥상태의 얽힘 엔트로피로 위상 질서·임계성을 진단(→ [../ch5-emergent-gauge/04-entanglement-phases.md](../ch5-emergent-gauge/04-entanglement-phases.md)). 면적 법칙이 텐서망 가능성을 결정.
- **(→ statistical-mechanics)**: 횡자기장 이징은 2D 고전 이징과 양자–고전 대응으로 등가($d\to d+z$)(→ [../ch6-quantum-phase-correlation/01-quantum-phase-transition.md](../ch6-quantum-phase-correlation/01-quantum-phase-transition.md)).

## 🪜 창발

- **(L5 holography)**: 강상관 허바드의 도핑된 모트가 스트레인지 메탈로 가는 곳에서 홀로그래피(AdS/CMT)가 비페르미 액체를 기술 — 정확 대각화가 멈추는 곳의 다른 언어.
- **(L6 emergence)**: 같은 격자·같은 채움인데 $U/t$ 하나로 금속↔절연체가 갈리는 것 — 미시 파라미터에서 거시 상이 창발하는, 환원주의가 못 보는 More is Different 의 수치 표본.

## 📐 예측·반증

- **정량 예측**: 2 사이트 $E_0=(U-\sqrt{U^2+16t^2})/2$, 큰 $U$ 모트 갭 $\Delta_c\approx U$, 초교환 $J=4t^2/U$, 횡자기장 이징 임계점 $g/J=1$.
- **반증 가능성**: 만약 반충전 허바드가 $U\to\infty$ 에서도 금속이면 모트 그림이 틀린 것 — 정확 대각화·냉원자 실험은 절연체를 확증.
- **수치 검증**: 정확 대각화가 2 사이트 해석해를 재현(실험 1), 모트 갭이 $U$ 와 함께 열림(실험 2), 스핀 상관이 음으로 깊어짐(실험 3) — 모두 확증.

## 🤔 다음 질문

지금까지 우리는 밴드(천 수)·초전도(BCS 갭)·강상관(허바드 대각화)을 각각 numpy/scipy 로 풀었다. 준입자가 창발하고, 위상이 물질을 분류하고, 평균장이 응축을 낳고, 상호작용이 모트를 만드는 — 이 모든 조각이 하나의 큰 그림을 이룬다. 마지막 문서에서 이 레포 전체를 회고하며, 응집물질이 왜 "More is Different 의 살아있는 증거" 인지, 그리고 창발이 어떻게 위 레이어(L5 홀로그래피·L6 창발의 정수)로 발사되는지를 종합한다.

---

🧩 **Principle** — 점유수 기저에서 페르미온 부호까지 정확히 짠 허바드 행렬을 전체 대각화하면, 같은 격자·같은 채움인데 $U/t$ 하나로 금속↔모트 절연체가 갈리고(전하 갭 $\Delta_c\approx U$), 바닥상태 스핀이 초교환 $J=4t^2/U$ 로 반강자성 정렬한다.
🔬 **Boundary** — 힐베르트 공간 $4^L$ 의 지수 장벽으로 ~16 사이트가 한계이고, 유한 크기라 진짜 상전이 대신 최소 갭으로만 임계점을 추정하며, 단일밴드 모형 자체가 단순화다.
🪜 **Emergence** — 미시 $U/t$ 에서 거시 상이 창발하는 이 구조는 위 레이어에서 홀로그래픽 스트레인지 메탈·창발의 정수로 재등장하고, 2 사이트 해석해 재현·$U$ 와 함께 열리는 모트 갭·음의 스핀 상관으로 검증된다.

## 📝 연습문제

**1. (기초)** 2 사이트 반충전(↑1, ↓1) 허바드의 4차원 부분공간 기저 $\{|\uparrow,\downarrow\rangle,|\downarrow,\uparrow\rangle,|\uparrow\downarrow,0\rangle,|0,\uparrow\downarrow\rangle\}$ 에서 $H$ 의 $4\times4$ 행렬을 적고, 바닥상태 에너지가 $E_0=(U-\sqrt{U^2+16t^2})/2$ 임을 보여라.

<details><summary>해설</summary>

도약은 단일점유 두 상태($|\uparrow,\downarrow\rangle$, $|\downarrow,\uparrow\rangle$)를 이중점유 두 상태($|\uparrow\downarrow,0\rangle$, $|0,\uparrow\downarrow\rangle$)와 섞는다. 스핀 단일항 조합 $|s\rangle=\frac1{\sqrt2}(|\uparrow,\downarrow\rangle-|\downarrow,\uparrow\rangle)$ 와 이중점유 대칭 조합 $|d\rangle=\frac1{\sqrt2}(|\uparrow\downarrow,0\rangle+|0,\uparrow\downarrow\rangle)$ 만 섞이며 $2\times2$:
$$H_{2\times2}=\begin{pmatrix}0 & -2t\\ -2t & U\end{pmatrix}.$$
고유값 $\frac{U\pm\sqrt{U^2+16t^2}}{2}$. 낮은 쪽 $E_0=\frac{U-\sqrt{U^2+16t^2}}{2}$. $U=0$: $-2t$. $U\gg t$: $E_0\approx-4t^2/U$ — 초교환 $J=4t^2/U$. 삼중항(반평행 못 섞이는)·평행 스핀 상태는 도약 막혀 $E=0$. 실험 1이 이를 수치로 확증.
</details>

**2. (심화)** 4 사이트 허바드에서 $U/t$ 를 0→∞ 로 키울 때, 운동에너지 $\langle T\rangle$ 와 이중점유 $\langle\sum_i n_{i\uparrow}n_{i\downarrow}\rangle$ 이 어떻게 변하는지 정확 대각화로 계산하라(코드 확장). 큰 $U$ 에서 이중점유가 $\sim t^2/U^2$ 로 억제됨을 보이고, 이것이 모트 국소화의 신호임을 논하라.

<details><summary>해설</summary>

$\langle\sum n_\uparrow n_\downarrow\rangle=\partial E_0/\partial U$ (헬만–파인만). 2 사이트로 보면 $E_0=\frac{U-\sqrt{U^2+16t^2}}2$ → $\partial E_0/\partial U=\frac12(1-\frac{U}{\sqrt{U^2+16t^2}})$. $U=0$: $1/2$(자유 이중점유). $U\gg t$: $\frac12(1-(1-8t^2/U^2))=4t^2/U^2\to0$ — 이중점유가 $t^2/U^2$ 로 억제. 운동에너지 $\langle T\rangle\approx-2\langle T\rangle_0\cdot(\text{이중점유와 연동})\to-8t^2/U$(초교환 규모)로 줄어든다. 큰 $U$ 에서 전자가 이중점유를 피해 자리당 하나씩 *얼어붙고*(charge frozen), 운동에너지가 사라지며 도약이 막힘 → 모트 절연체. 남은 자유도는 스핀뿐이고, 그것이 초교환 $J=4t^2/U$ 로 반강자성 정렬(실험 3). 코드로는 바닥상태에서 $\sum_i|gs_n|^2\cdot(\text{이중점유 수})$ 를 합산하면 직접 확인된다.
</details>

**3. (논문 비평)** 정확 대각화는 ~16 사이트가 한계라 열역학 극한·임계지수를 직접 못 본다. 도핑된 2D 허바드(고온 초전도의 핵심)에서 (a) QMC 의 부호 문제, (b) DMRG 의 1D 편향·면적 법칙 제약, (c) 정확 대각화의 크기 한계가 각각 왜 발목을 잡는지 비교하고, 2D 허바드 상도(phase diagram)가 아직 미해결인 이유를 비판적으로 논하라.

<details><summary>해설</summary>

(a) QMC: 도핑된 페르미온 허바드는 분배함수의 가중치가 음수가 될 수 있어(페르미온 부호 문제) 통계 오차가 계 크기·역온도에 *지수적* 으로 폭발 — 저온·유한 도핑에서 신뢰 불가. 부호 문제 자체가 NP-난해(Troyer–Wiese)로 일반 해법이 없다. (b) DMRG: 1D 사슬·좁은 띠에서는 면적 법칙(얽힘 $\propto$ 경계)이 작아 결합차원이 다항으로 충분하나, 2D 에서는 경계가 폭에 비례해 얽힘이 폭과 함께 커지고 결합차원이 *지수적* 으로 필요 → 넓은 2D 계에 부적합. (c) 정확 대각화: $4^L$ 지수 장벽으로 ~16~20 사이트 한계, 유한 크기라 진짜 임계점·d-파 초전도 장거리 질서를 분해 못 함. 결과: 2D 허바드의 바닥상태가 스트라이프냐 d-파 초전도냐 균일 상이냐가 방법마다 다른 답을 주고, 미세한 에너지 차이(meV/사이트)가 상을 가르는데 어떤 수치도 그 정밀도를 열역학 극한에서 보장 못 한다. 이것이 강상관의 정직한 미해결 — "More is Different" 가 계산적으로도 벽이라는 증거다. 최근 여러 방법의 *교차 검증*(2D 허바드 벤치마크, Simons Collaboration)이 합의를 좁히고 있으나, 완전한 상도는 여전히 열린 문제다.
</details>

---

<div align="center">

[◀ 이전: BCS 갭 방정식](./03-bcs-gap-equation.md)  ·  [📚 README](../README.md)  ·  [다음: 종합 ▶](./05-synthesis.md)

</div>
