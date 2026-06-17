# 밴드 구조 계산 — 긴밀결합 모형

> *전자가 격자에 갇히면 불연속 원자 준위가 연속 띠(band)로 번진다. 그 띠의 모양 $E(\mathbf{k})$ 와 — 디머라이즈된 SSH 사슬에서는 — 그 띠의 *위상* 까지, numpy 몇 줄로 직접 그릴 수 있다.*

## 🎯 핵심 질문

- 한 원자 준위에 묶여 있던 전자가 이웃으로 *터널링* 할 수 있을 때, 왜 단일 준위가 폭 $4t$ 의 띠 $E(k)=-2t\cos(ka)$ 로 퍼지는가 — 그리고 이 한 줄에 격자 주기성·블로흐 정리·창발하는 유효 질량이 모두 들어 있는가?
- 같은 긴밀결합을 디머라이즈(intra hopping $t_1$ ≠ inter hopping $t_2$)하면 왜 두 밴드와 띠틈이 생기고, $t_1<t_2$ 일 때만 유한 사슬에 *영에너지 가장자리 모드* 가 붙는가?
- 이 가장자리 모드의 존재를 벌크 밴드의 한 정수 — Zak 위상(0 또는 $\pi$) — 이 *강제* 한다는 벌크–경계 대응을, 코드로 어떻게 검증하나?

## 🌍 어디서 나타나나

- **모든 고체의 전자 구조**: 실제 DFT 밴드 계산의 개념적 원형. 금속/절연체/반도체의 구분이 곧 띠의 채움과 띠틈의 문제.
- **폴리아세틸렌**: SSH(Su–Schrieffer–Heeger) 모형의 실제 무대. 이중결합/단일결합 교대 = 디머라이즈, 결함에 묶인 솔리톤 = 가장자리/도메인벽 영모드.
- **냉원자 광격자·광자 결정·음향 메타물질**: 긴밀결합 모형을 *인공적으로 설계* 해 SSH 띠와 위상 가장자리 상태를 직접 구현·관측.
- **위상 광자/회로**: SSH 의 영모드는 결함에 견디는 국소 모드로, 위상 보호 도파로·레이저에 응용.

## 🔍 직관의 함정

**함정 1 — "밴드는 그냥 원자 준위의 모임이다."** 아니다. 고립 원자의 준위는 한 점이다. 띠 $E(k)=-2t\cos(ka)$ 의 *폭* $4t$ 와 *분산 모양* 은 전적으로 **터널링(이웃과의 결맞음)** 에서 창발한다. 전자가 한 원자에 갇혀 있으면 띠는 없다. 다수의 원자 + 결맞은 터널링 → 연속 띠라는 새 자유도.

**함정 2 — "위상(topology)은 강한 상호작용에서만 나온다."** SSH 는 *완전한 단일입자(비상호작용)* 모형인데도 위상 절연체와 자명 절연체를 가른다. 위상은 상호작용의 전유물이 아니라 — 채워진 밴드 파동함수의 기하에서 이미 나온다.

**함정 3 — "$t_1<t_2$ 와 $t_1>t_2$ 는 단위격자를 한 칸 옮긴 같은 물리다."** 무한 사슬에서는 그렇게 보인다. 그러나 *경계가 있는* 유한 사슬에서는 단위격자를 어디서 자르는가가 물리적 차이를 만든다 — 한쪽은 잘린 결합이 영모드를 남기고, 다른 쪽은 안 남긴다. 이것이 벌크–경계 대응의 핵심.

## ⚙️ 제1원리 유도

### 1) 긴밀결합 — 터널링이 준위를 띠로 번지게 한다

격자점 $n$ 에 국소화된 원자 궤도 $|n\rangle$ (Wannier 함수). 전자는 같은 자리 에너지 $\epsilon_0$ 를 갖고, 이웃으로 진폭 $-t$ 로 도약(hopping)한다:

$$
H=\epsilon_0\sum_n |n\rangle\langle n|-t\sum_n\big(|n\rangle\langle n+1|+|n+1\rangle\langle n|\big).
$$

격자 주기성 → 블로흐 정리: 고유상태는 $|k\rangle=\sum_n e^{ikna}|n\rangle$. 대입하면

$$
H|k\rangle=\Big(\epsilon_0-t(e^{ika}+e^{-ika})\Big)|k\rangle,\qquad
\boxed{E(k)=\epsilon_0-2t\cos(ka).}\quad\square
$$

단일 원자 준위 $\epsilon_0$ 가 폭 $4t$ 의 띠로 퍼졌다. 띠 바닥 $k=0$ 근처에서 $E\approx\epsilon_0-2t+t a^2 k^2$ — 자유전자처럼 보이되, **유효 질량** $m^*=\hbar^2/(2ta^2)$ 가 창발한다. 터널링이 약하면($t$ 작음) 무겁고, 강하면 가볍다. 질량조차 다수의 격자에서 나오는 유효 개념임을 본다. $\epsilon_0$ 는 에너지 원점이므로 이하 $\epsilon_0=0$.

### 2) 2D 정사각격자 — 띠가 면을 이룬다

2차원으로 올리면 $x,y$ 방향 터널링이 더해져

$$
\boxed{E(k_x,k_y)=-2t(\cos k_x a+\cos k_y a),}\quad\square
$$

띠폭 $8t$. 반쯤 채우면 페르미면이 정사각형($\cos k_x+\cos k_y=0$)이 되고, 이 *완전 네스팅(nesting)* 이 모트 절연체·반강자성·고온 초전도(→ [../ch6-quantum-phase-correlation/03-mott-insulator.md](../ch6-quantum-phase-correlation/03-mott-insulator.md)) 의 무대가 된다. 띠 구조 한 줄에서 강상관의 씨앗이 보인다.

### 3) SSH — 디머라이즈가 띠틈과 위상을 연다

단위격자 안에 두 부격자 $A,B$ 를 두고, intra(같은 격자) 도약 $t_1$, inter(이웃 격자) 도약 $t_2$ 로 교대시킨다. 블로흐 해밀토니안은 $2\times2$:

$$
H(k)=\begin{pmatrix}0 & h(k)\\ h^*(k) & 0\end{pmatrix},\qquad
h(k)=t_1+t_2 e^{-ika}.
$$

고유값

$$
\boxed{E_\pm(k)=\pm|h(k)|=\pm\sqrt{t_1^2+t_2^2+2t_1t_2\cos ka}.}\quad\square
$$

$k=\pi/a$ 에서 갭 $=2|t_1-t_2|$. $t_1=t_2$ 에서 갭이 닫히며 — 그 점이 두 위상 상을 가르는 상전이점이다.

### 4) Zak 위상 — 1D 밴드의 위상 불변량

$h(k)=t_1+t_2e^{-ika}$ 는 복소평면 위 곡선이다. $k$ 가 $0\to2\pi/a$ 를 돌 때 이 곡선이 **원점을 감싸면**($t_2>t_1$) 위상적, **안 감싸면**($t_1>t_2$) 자명. 이 감김 수를 측정하는 것이 채워진 밴드의 Zak 위상:

$$
\boxed{\gamma_{\text{Zak}}=i\oint_{\text{BZ}}\langle u_-(k)|\partial_k u_-(k)\rangle\,dk\in\{0,\pi\}\ (\text{mod }2\pi).}\quad\square
$$

$\gamma=\pi$ ↔ 위상(감김 1), $\gamma=0$ ↔ 자명(감김 0). 키랄 대칭이 $\gamma$ 를 0 또는 $\pi$ 로 고정한다. **벌크–경계 대응**: $\gamma=\pi$ 인 사슬을 유한하게 자르면 양 끝에 영에너지 모드가 강제로 나타난다.

### 실험 1 — 1D·2D 긴밀결합 밴드와 유효 질량

```python
import numpy as np
import matplotlib.pyplot as plt

t, a = 1.0, 1.0

# --- 1D 밴드: E(k) = -2t cos(ka), 띠폭 = 4t 확인 ---
k = np.linspace(-np.pi/a, np.pi/a, 400)
E1d = -2*t*np.cos(k*a)
print(f"1D 띠폭 = {E1d.max()-E1d.min():.4f}  (이론 4t = {4*t})")

# 바닥 근처 유효 질량: E ≈ E0 + (ħ²/2m*) k²,  m* = ħ²/(2 t a²)
# 수치 2차 미분으로 곡률 → 유효 질량 (ħ=1)
d2 = np.gradient(np.gradient(E1d, k), k)
m_eff = 1.0 / d2[len(k)//2]          # k=0 에서
print(f"수치 m* = {m_eff:.4f},  이론 1/(2t) = {1/(2*t):.4f}")

# --- 2D 정사각격자: E = -2t(cos kx + cos ky), 띠폭 8t ---
kx, ky = np.meshgrid(np.linspace(-np.pi,np.pi,200), np.linspace(-np.pi,np.pi,200))
E2d = -2*t*(np.cos(kx)+np.cos(ky))
print(f"2D 띠폭 = {E2d.max()-E2d.min():.4f}  (이론 8t = {8*t})")

# 반충전 페르미면(E=0): cos kx + cos ky = 0 — 완전 네스팅된 정사각형
fig, ax = plt.subplots(1,2, figsize=(10,4))
ax[0].plot(k, E1d); ax[0].set_title("1D  E(k)=-2t cos(ka)")
ax[0].set_xlabel("k"); ax[0].set_ylabel("E")
ax[1].contour(kx, ky, E2d, levels=[0], colors='r')   # 페르미면
ax[1].set_title("2D 페르미면 (반충전, 완전 네스팅)")
ax[1].set_aspect('equal')
plt.tight_layout(); plt.savefig("tb_bands.png", dpi=110)
print("저장: tb_bands.png")
```

출력: 1D 띠폭 `4.0000`, 유효 질량 `0.5000`(=$1/2t$), 2D 띠폭 `8.0000`. 단일 준위에서 띠와 유효 질량이 정확히 창발한다.

### 실험 2 — SSH 유한 사슬의 가장자리 영모드

```python
import numpy as np

def ssh_chain(N_cells, t1, t2):
    """N_cells 단위격자(2N 사이트) 열린 사슬의 실공간 해밀토니안."""
    N = 2*N_cells
    H = np.zeros((N, N))
    for n in range(N_cells):
        A, B = 2*n, 2*n+1
        H[A, B] = H[B, A] = t1                 # intra-cell (A-B)
        if n < N_cells-1:
            H[B, 2*(n+1)] = H[2*(n+1), B] = t2  # inter-cell (B-A')
    return H

for t1, t2, label in [(1.0, 0.5, "자명  t1>t2"), (0.5, 1.0, "위상  t1<t2")]:
    H = ssh_chain(20, t1, t2)
    w, v = np.linalg.eigh(H)
    n_zero = np.sum(np.abs(w) < 1e-4)        # 유한 사슬: 갭 중앙 ~1e-6 까지 영모드로 간주
    print(f"{label}: 영에너지 모드 {n_zero}개,  최소 |E| = {np.min(np.abs(w)):.2e}")
    if n_zero > 0:
        # 영모드의 공간 분포: 양 끝에 국소화되었는지 확인
        zero_modes = v[:, np.abs(w) < 1e-4]
        weight = np.sum(np.abs(zero_modes)**2, axis=1)
        print(f"   왼쪽 4 사이트 가중치 {weight[:4].sum():.3f}, "
              f"오른쪽 4 사이트 {weight[-4:].sum():.3f}  (끝에 집중)")
# 자명: 0개,  위상: 2개 (양 끝 국소화) — 벌크 띠틈 안의 보호된 가장자리 상태
```

출력: 자명 상은 영모드 0개, 위상 상은 영모드 2개가 양 끝에 강하게 국소화. 벌크 디머라이즈 패턴이 가장자리 모드를 *강제* 한다.

### 실험 3 — Zak 위상으로 위상/자명을 가른다

```python
import numpy as np

def zak_phase(t1, t2, Nk=400):
    """채워진(아래) 밴드의 Zak 위상 — 이산 베리 위상(게이지 불변)."""
    ks = np.linspace(0, 2*np.pi, Nk, endpoint=False)
    lower = []
    for k in ks:
        h = t1 + t2*np.exp(-1j*k)
        H = np.array([[0, h], [np.conj(h), 0]])
        w, v = np.linalg.eigh(H)
        lower.append(v[:, 0])           # E<0 고유벡터
    # 인접 k 의 겹침을 곱한 위상 = 윌슨 루프 (게이지 임의성 상쇄)
    prod = 1.0 + 0j
    for i in range(Nk):
        prod *= np.vdot(lower[i], lower[(i+1) % Nk])
    return abs(np.angle(prod))           # 키랄 대칭으로 0 또는 π 로 고정

for t1, t2 in [(1.0, 0.5), (0.5, 1.0)]:
    gamma = zak_phase(t1, t2)
    phase = "위상(π)" if abs(gamma-np.pi) < 0.3 else "자명(0)"
    print(f"t1={t1}, t2={t2}:  Zak γ = {gamma:.4f}  →  {phase}")
# t1>t2 → γ≈0 (감김 0, 자명),  t1<t2 → γ≈π (감김 1, 위상) — 가장자리 모드 유무와 일치
```

출력: $t_1>t_2$ 에서 $\gamma\approx0$, $t_1<t_2$ 에서 $\gamma\approx\pi$. 실험 2의 가장자리 모드 유무와 한 치도 어긋나지 않는다 — 벌크 정수가 경계를 예언한다.

## 🧪 실험·관측 증거

- **폴리아세틸렌**: 디머라이즈 갭과 결합 교대가 분광으로 측정됨. 도메인벽(솔리톤)에 묶인 중간갭 상태 = SSH 영모드의 실물.
- **냉원자 광격자**: SSH 띠와 위상 가장자리 상태를 Bloch 진동·국소 밀도로 직접 측정(Atala 외 2013, Zak 위상 측정).
- **광자/음향 SSH**: 도파로 배열·공진기 사슬에서 위상 가장자리 모드가 제작 결함을 견디며 국소화 — 위상 보호의 광학적 시연.
- **ARPES**: 실제 고체의 $E(\mathbf{k})$ 를 직접 찍는다. 긴밀결합 분산이 정성적 골격, DFT 가 정량적 보정.

## 🔬 경계

- **단일입자 근사**: 긴밀결합·SSH 는 전자–전자 상호작용을 무시. 반쯤 채운 강상관에서는 밴드 이론이 절연체를 놓친다(모트, → [../ch6-quantum-phase-correlation/03-mott-insulator.md](../ch6-quantum-phase-correlation/03-mott-insulator.md)).
- **긴거리 도약·곡률**: 실제 고체는 2차 이상 이웃 도약·궤도 혼성이 있어 단순 $-2t\cos$ 에서 벗어난다. 정량 정확도는 DFT/Wannier 화 필요.
- **위상의 보호 한계**: SSH 영모드는 *키랄 대칭* 이 보호한다. 대각 무질서(자리 에너지 요동)가 키랄 대칭을 깨면 영모드가 갭에서 밀려난다.
- **수치 게이지 함정**: Zak 위상을 직접 미분으로 구하면 게이지 임의성으로 흔들린다. 윌슨 루프(겹침 곱) 방식이 게이지 불변이라 안정적(→ [02-chern-number-numerics.md](./02-chern-number-numerics.md) 의 FHS 와 같은 정신).

## 🧬 횡단 원리

- **(→ symmetry-conservation)**: 블로흐 정리는 격자 병진 대칭의 직접 귀결 — 대칭이 좋은 양자수 $k$ 를 낳는다. 키랄 대칭이 Zak 위상을 0/$\pi$ 로 양자화.
- **(→ quantum-information)**: SSH 영모드는 가장 단순한 위상 보호 자유도 — 마요라나 사슬(Kitaev)의 형제. 위상 큐비트 직관의 출발점(→ [../ch4-topological-matter/06-majorana-anyon.md](../ch4-topological-matter/06-majorana-anyon.md)).
- **(→ standard-model)**: $h(k)$ 의 원점 감김 수는 1D 위상 항(윈딩)으로, 2D 천 수·게이지장 인스탄톤과 같은 수학 계보.

## 🪜 창발

- **(L5 holography)**: 벌크 Zak 위상이 경계 영모드를 강제하는 구조는 벌크–경계 대응의 최소 모형 — 벌크 기하가 경계 자유도를 결정한다는 홀로그래피 정신의 1D 씨앗.
- **(L6 emergence)**: 연속적 실수 파라미터($t_1,t_2$)에서 *이산 정수*(Zak 0/$\pi$, 영모드 개수)가 창발하는 구조. 국소 도약에서 전역 위상이, 미시 격자에서 거시 보호가 나온다.

## 📐 예측·반증

- **정량 예측**: 1D 띠폭 = $4t$, 2D = $8t$, 유효 질량 $m^*=\hbar^2/2ta^2$. SSH 갭 = $2|t_1-t_2|$, $t_1=t_2$ 에서만 갭 닫힘.
- **벌크–경계 정리**: $t_1<t_2$(Zak $\pi$)인 유한 사슬은 *정확히* 2개의 가장자리 영모드(양 끝)를 가져야 하고, $t_1>t_2$ 는 0개여야 한다. 실험 2·3이 확증.
- **반증 가능성**: 만약 Zak 위상이 $\pi$ 인데 가장자리 모드가 없다면(키랄 대칭 보존 하에서) 벌크–경계 대응이 깨진 것 — 관측되지 않았다.

## 🤔 다음 질문

SSH 의 위상 불변량은 1D 의 Zak 위상(감김 수) 하나였다. 2차원으로 올라가면 밴드의 위상은 더 풍부한 *천 수* 가 되고, 그것이 홀 전도도를 양자화한다. 다음 문서에서 2밴드 $\mathbf{d}(\mathbf{k})$ 모형의 베리 곡률을 적분해 천 수가 *정말 정수로* 양자화됨을 — 그리고 거친 격자에서도 정확한 정수를 주는 Fukui–Hatsugai–Suzuki 방법을 — numpy 로 직접 확인한다.

---

🧩 **Principle** — 국소 원자 준위가 다수의 격자 + 결맞은 터널링에서 폭 $4t$ 의 연속 띠 $E(k)=-2t\cos ka$ 와 유효 질량으로 창발하고, 디머라이즈된 SSH 에서는 채워진 밴드의 Zak 위상(0/$\pi$)이 가장자리 영모드의 존재를 강제한다.
🔬 **Boundary** — 단일입자 근사라 강상관 모트를 놓치고, 키랄 대칭을 깨는 무질서는 영모드를 갭에서 밀어내며, 직접 미분 Zak 은 게이지로 흔들린다.
🪜 **Emergence** — 연속 도약에서 이산 위상 정수가 나오는 이 구조는 위 레이어에서 벌크–경계 홀로그래피·위상 큐비트로 재등장하고, SSH 갭 $2|t_1-t_2|$ 와 영모드 2개(위상)/0개(자명)로 검증된다.

## 📝 연습문제

**1. (기초)** 1D 긴밀결합 $E(k)=-2t\cos(ka)$ 에서 군속도 $v_g=\frac1\hbar\frac{dE}{dk}$ 와 유효 질량 $m^*=\hbar^2/(d^2E/dk^2)$ 를 구하고, 띠 바닥($k=0$)과 띠 꼭대기($k=\pi/a$)에서 유효 질량의 부호가 반대임을 보여라.

<details><summary>해설</summary>

$v_g=\frac{2ta}{\hbar}\sin(ka)$, $d^2E/dk^2=2ta^2\cos(ka)$ 이므로 $m^*=\hbar^2/(2ta^2\cos ka)$. $k=0$: $\cos=+1\Rightarrow m^*=+\hbar^2/2ta^2>0$(전자 같은 띠 바닥). $k=\pi/a$: $\cos=-1\Rightarrow m^*<0$(정공 같은 띠 꼭대기). 음의 유효 질량이 곧 정공 개념의 기원 — 다수의 격자에서 창발한 유효 자유도가 부호까지 바꾼다.
</details>

**2. (심화)** SSH 블로흐 해밀토니안 $h(k)=t_1+t_2e^{-ika}$ 에 대해, $k:0\to2\pi$ 일 때 복소평면 위 $h(k)$ 의 자취가 원점을 감싸는 횟수(winding number)가 $t_2>t_1$ 이면 1, $t_1>t_2$ 이면 0 임을 보이고, 이 감김 수가 Zak 위상 $\gamma=\pi\times(\text{winding})$ 과 같음을 논하라.

<details><summary>해설</summary>

$h(k)=t_1+t_2e^{-ika}$ 는 중심 $t_1$, 반지름 $t_2$ 인 원. 원점이 이 원 *안*($t_2>t_1$)이면 $k$ 가 한 바퀴 돌 때 $h$ 의 편각이 $-2\pi$ 변해 감김 수 1; 원점이 원 *밖*($t_1>t_2$)이면 편각 순변화 0 → 감김 0. 키랄 대칭($\sigma_z H\sigma_z=-H$)이 있는 2밴드에서 Zak 위상은 $h(k)$ 편각의 총 변화의 절반이라 $\gamma=\pi\cdot w$. 따라서 $w=1\Rightarrow\gamma=\pi$(위상), $w=0\Rightarrow\gamma=0$(자명). 실험 3의 수치와 일치.
</details>

**3. (논문 비평)** SSH 모형은 키랄(부격자) 대칭이 영모드를 정확히 $E=0$ 에 고정한다. 실제 폴리아세틸렌에는 자리 에너지 차이·전자–포논 결합·전자–전자 상호작용이 있다. 이런 섭동들이 (a) 키랄 대칭을 깨는지, (b) 가장자리/솔리톤 모드를 갭 중앙에서 얼마나 밀어내는지를 분석하고, "위상 보호" 가 실험적으로 얼마나 견고한지 비판적으로 논하라.

<details><summary>해설</summary>

(a) 두 부격자의 자리 에너지가 다르면($\epsilon_A\neq\epsilon_B$) 대각 항 $\propto\sigma_z$ 가 생겨 키랄 대칭($\sigma_z H\sigma_z=-H$)이 깨진다 — 이때 갭은 열린 채로도 영모드가 $E=0$ 에서 벗어나 갭 안 어딘가로 이동한다. 전자–포논(Peierls)은 디머라이즈 자체의 기원이라 오히려 위상을 *만들고*, 전자–전자 상호작용은 단일입자 그림을 넘어 솔리톤 스핀–전하 분리를 낳는다. (b) 키랄 대칭을 *보존* 하는 섭동(도약 무질서)은 영모드를 정확히 0에 묶어 두므로 위상 보호가 견고하다. 깨는 섭동(자리 무질서)이 작으면 영모드는 지수적으로 작은 갭만 얻어 *근사적으로* 보호된다. 결론: SSH 의 위상 보호는 키랄 대칭이라는 *조건부* 보호 — 대칭이 깨지는 정도만큼 보호가 약해진다. 실제 물질의 위상 견고함은 어떤 대칭이 얼마나 잘 보존되느냐의 정량 문제이지, 무조건적 마법이 아니다.
</details>

---

<div align="center">

[◀ 이전: 강상관의 최전선](../ch6-quantum-phase-correlation/05-strong-correlation-frontier.md)  ·  [📚 README](../README.md)  ·  [다음: 천 수 계산 ▶](./02-chern-number-numerics.md)

</div>
