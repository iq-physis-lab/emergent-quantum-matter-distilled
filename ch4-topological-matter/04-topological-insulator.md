# 위상 절연체 — 안은 절연·겉은 도체

> *자기장도, 시간역전 깨짐도 없이 — 시간역전 대칭 그 자체가 보호하는 $\mathbb{Z}_2$ 위상이, 벌크는 절연체이면서 가장자리·표면에는 결코 사라지지 않는 도체 채널을 강제한다.*

## 🎯 핵심 질문

- 시간역전 대칭이 천 수를 0으로 강제하는데도, *왜* 위상적으로 비자명한 절연체가 존재할 수 있는가 — 새 불변량 $\mathbb{Z}_2$ 는 무엇을 세는가?
- 벌크가 완전한 절연체인데 *왜* 가장자리/표면에는 갭 없는 전도 상태가 반드시 나타나는가(벌크–경계 대응)?
- 그 가장자리 상태는 *왜* 후방산란에 면역인가 — 헬리컬(스핀–운동량 잠금) 구조가 어떻게 보호를 만드는가?

## 🌍 어디서 나타나나

- **HgTe/CdTe 양자우물**: König 외(2007)가 2차원 위상 절연체(양자 스핀홀, QSH)를 처음 관측. 두께가 임계값을 넘으면 밴드가 반전되어 위상상이 됨.
- **3차원 위상 절연체**: $\text{Bi}_2\text{Se}_3$, $\text{Bi}_2\text{Te}_3$, $\text{Sb}_2\text{Te}_3$. 표면에 단일 디랙 콘. ARPES 로 디랙 표면 상태 직접 영상화(Hsieh, Xia 외, 2008–2009).
- **위상 결정 절연체·고차 위상 절연체**: SnTe(거울 대칭 보호), 코너/힌지 모드를 가진 고차 위상 물질.
- **위상 광자/음향계**: 시간역전 유사 대칭으로 보호되는 헬리컬 가장자리 모드 — 산란 없는 도파로.

## 🔍 직관의 함정

**함정 1 — "위상 절연체는 그냥 표면이 금속인 절연체."** 평범한 절연체도 표면 상태를 가질 수 있지만, 그것들은 화학적 처리로 *없앨 수 있다*. 위상 절연체의 표면 상태는 **벌크 위상이 강제**해서, 표면을 어떻게 처리해도(시간역전을 깨지 않는 한) 사라지지 않는다 — 벌크–경계 대응의 귀결.

**함정 2 — "$\mathbb{Z}_2$ 는 천 수의 작은 변형."** 천 수 $\mathbb{Z}$ 는 시간역전을 깨야 비자명하다. 시간역전을 *보존* 하면 $C=0$ 이 강제되고, 대신 $\nu\in\{0,1\}$ 의 **이진 분류** $\mathbb{Z}_2$ 가 등장한다 — "위상이 짝수 번 감겼나 홀수 번 감겼나" 라는 본질적으로 다른 불변량.

**함정 3 — "가장자리 도체니까 저항이 작다."** 핵심은 저항이 아니라 *후방산란 금지* 다. 헬리컬 가장자리에서 오른쪽으로 가는 전자는 위로, 왼쪽으로 가는 전자는 아래로 스핀이 잠겨 있어, 시간역전 불변 불순물은 둘을 연결(180° 후방산란)할 수 없다 — 크라머스 정리가 막는다.

## ⚙️ 제1원리 유도

### 1) 시간역전 대칭과 크라머스 정리 — 짝수 겹침의 강제

스핀-1/2 페르미온의 시간역전 연산자 $\Theta=i\sigma_y K$ ($K$ 는 복소켤레)는

$$
\Theta^2=(i\sigma_y K)(i\sigma_y K)=i\sigma_y(i\sigma_y^*)=\sigma_y(-\sigma_y)\cdot(-1)= -1.
$$

$\Theta^2=-1$ 이면 **크라머스 정리**: 모든 고유상태는 짝수 겹침(최소 2중). $|\psi\rangle$ 와 $\Theta|\psi\rangle$ 는 직교($\langle\psi|\Theta\psi\rangle=0$)하며 같은 에너지를 갖는 크라머스 쌍이다.

시간역전 불변점 $\mathbf{k}=-\mathbf{k}$ (TRIM: $\Gamma$, $X$, ...)에서 밴드는 반드시 크라머스 겹침이라 그곳에서 두 밴드가 붙는다. 이 겹침이 가장자리 상태 분류의 열쇠다.

### 2) $\mathbb{Z}_2$ 불변량 — 가장자리 모드의 짝/홀

블로흐 함수의 시간역전 행렬 $w_{mn}(\mathbf{k})=\langle u_m(-\mathbf{k})|\Theta|u_n(\mathbf{k})\rangle$ (반대칭). TRIM 에서 파피안(Pfaffian) $\text{Pf}[w(\Gamma_a)]$ 의 부호로 $\mathbb{Z}_2$ 불변량을 정의:

$$
\boxed{(-1)^\nu=\prod_{a}\frac{\sqrt{\det[w(\Gamma_a)]}}{\text{Pf}[w(\Gamma_a)]},\qquad \nu\in\{0,1\}.}\quad\square
$$

$\nu=0$ 은 보통 절연체, $\nu=1$ 은 위상 절연체. 직관적으로 $\nu$ 는 두 TRIM 사이에서 **크라머스 쌍이 페르미 준위를 가로지르는 횟수의 홀짝** 을 센다 — 홀수면 가장자리 모드가 후방산란으로 없앨 수 없다.

### 3) BHZ 모형 — 밴드 반전이 만드는 위상

Bernevig–Hughes–Zhang(2006) 의 2차원 모형. 4밴드(전자/홀 × 스핀 ↑↓)를 스핀별로 두 블록으로 나눈다. 한 스핀 블록의 $\mathbf{k}\cdot\mathbf{p}$ 해밀토니안:

$$
h(\mathbf{k})=\epsilon(\mathbf{k})\mathbb{1}+\mathbf{d}(\mathbf{k})\cdot\boldsymbol\sigma,\qquad
\mathbf{d}=\big(A k_x,\;A k_y,\;M-B k^2\big).
$$

이것은 [02](./02-chern-number.md) 의 2밴드 천 절연체와 같은 꼴! 이 블록의 천 수는

$$
C_\uparrow=\frac{1}{2}\big[\text{sgn}(M)+\text{sgn}(B)\big].
$$

- $M/B>0$ (밴드 반전): $C_\uparrow=\pm1$ → 비자명.
- $M/B<0$ (정상): $C_\uparrow=0$ → 자명.

반대 스핀 블록은 시간역전으로 $C_\downarrow=-C_\uparrow$. 총 천 수 $C=C_\uparrow+C_\downarrow=0$ (시간역전이 강제). 그러나 **스핀 천 수** $C_s=\tfrac12(C_\uparrow-C_\downarrow)=C_\uparrow\neq0$ 이 위상을 나르고, $\mathbb{Z}_2$ 불변량은 $\nu=C_\uparrow \bmod 2$.

$$
\boxed{\nu=1 \iff \text{밴드 반전}(M/B>0)\iff \text{헬리컬 가장자리 쌍 존재.}}\quad\square
$$

질량 $M$ 의 부호가 바뀌는 곳(HgTe 양자우물 임계 두께)에서 위상 상전이가 일어난다.

### 4) 벌크–경계 대응 — 위상이 다른 두 영역의 경계엔 갭이 없다

위상 절연체($\nu=1$)와 진공($\nu=0$, 보통 절연체)의 경계를 생각하자. 디랙 질량 $M(x)$ 가 위상상($M>0$)에서 진공($M<0$)으로 넘어가며 *부호를 바꾼다*. 1차원 디랙 방정식

$$
\big[-i v\sigma_x\partial_x+M(x)\sigma_z\big]\psi=E\psi
$$

는 $M(x)$ 가 부호를 바꾸는 곳에 **영에너지 구속 상태**(Jackiw–Rebbi)를 갖는다:

$$
\psi_0(x)\propto e^{-\frac{1}{v}\int_0^x M(x')dx'}\,\chi,\qquad \sigma_y\chi=\chi,\quad E=0.\quad\square
$$

이 영모드가 경계를 따라 분산하면(2D 경계 → 1D 카이럴/헬리컬 채널) 갭 없는 가장자리 상태가 된다. 시간역전 짝까지 합치면 위로 가는 ↑ 와 아래로 가는 ↓ 가 한 쌍 — **헬리컬 가장자리**. 벌크 위상수 차이가 경계 모드 수를 정확히 강제한다:

$$
(\text{가장자리 헬리컬 쌍 수})=\Delta\nu\pmod 2.\quad\square
$$

### 5) 3차원 위상 절연체와 디랙 표면 상태

3차원에서는 네 개의 $\mathbb{Z}_2$ 지표 $(\nu_0;\nu_1\nu_2\nu_3)$. 강한 위상 절연체($\nu_0=1$)는 표면에 **홀수 개의 디랙 콘**(예: $\text{Bi}_2\text{Se}_3$ 는 1개):

$$
H_{\text{surf}}=\hbar v_F(\sigma_x k_y-\sigma_y k_x),\qquad E=\pm\hbar v_F|\mathbf{k}|.
$$

스핀이 운동량에 수직으로 잠긴(spin–momentum locking) 단일 디랙 콘. 단일 디랙 콘은 2차원 격자에서 단독으로 존재할 수 없다(펜로즈/Nielsen–Ninomiya 페르미온 더블링) — 오직 3차원 위상 절연체의 *표면* 으로만 존재 가능. 이것이 벌크–경계 대응의 가장 극적인 형태다.

### 실험 1 — BHZ 띠(strip) 기하: 헬리컬 가장자리 모드 스펙트럼

```python
import numpy as np

# 2D BHZ 모형을 y 방향 유한 띠로 잘라 가장자리 모드를 본다.
# 한 스핀 블록: d = (A sin kx, A sin ky, M - 2B(2-cos kx-cos ky))  (격자판)
def bhz_strip_spectrum(kx, Ny, A=1.0, B=1.0, M=-1.0):
    """y 방향 Ny 사이트 띠, kx 는 보존. 4x4가 아니라 한 스핀 블록(2x2/사이트)."""
    sx = np.array([[0,1],[1,0]], complex)
    sy = np.array([[0,-1j],[1j,0]], complex)
    sz = np.array([[1,0],[0,-1]], complex)
    dim = 2*Ny
    H = np.zeros((dim, dim), complex)
    for n in range(Ny):
        # 사이트 내(on-site): kx 항 + 질량
        Mk = M - 2*B*(2 - np.cos(kx))     # y 방향 cos 는 호핑으로
        onsite = A*np.sin(kx)*sx + (Mk + 2*B)*sz   # +2B: 아래 호핑 보정 균형
        H[2*n:2*n+2, 2*n:2*n+2] += onsite
        if n+1 < Ny:
            # y 방향 호핑: -B sz (운동에너지) - (A/2i) sy (디랙)
            hop = -B*sz - (A/(2j))*sy
            H[2*n:2*n+2, 2*(n+1):2*(n+1)+2] += hop
            H[2*(n+1):2*(n+1)+2, 2*n:2*n+2] += hop.conj().T
    return np.linalg.eigvalsh(H)

Ny = 30
kxs = np.linspace(-np.pi, np.pi, 101)
# 위상상(M/B>0 가 되도록 M=-1, B=1 격자판 → 반전): 갭 안에 가장자리 모드 존재 확인
gap_states = []
for kx in kxs:
    ev = bhz_strip_spectrum(kx, Ny, A=1.0, B=1.0, M=-1.0)
    # 페르미 준위(0) 근처 띠틈 안 상태 수
    gap_states.append(np.sum(np.abs(ev) < 0.3))
print("kx 별 갭 내부 상태 수 (가장자리 모드 → 0이 아님):")
print("최소:", min(gap_states), " 최대:", max(gap_states))
print("=> 갭 한가운데를 가로지르는 가장자리 모드 존재 (벌크-경계 대응)")
```

### 실험 2 — Jackiw–Rebbi 영모드: 질량 부호 변화가 묶는 상태

```python
import numpy as np

# 1D 디랙: H = -i v sigma_x d/dx + M(x) sigma_z.  M(x) 가 부호 바꾸면 E=0 구속.
def jackiw_rebbi(N=400, L=40.0, v=1.0, M0=1.0):
    x = np.linspace(-L/2, L/2, N)
    dx = x[1]-x[0]
    Mx = M0*np.tanh(x/2.0)   # 왼쪽 -M0, 오른쪽 +M0 (부호 변화 at x=0)
    sx = np.array([[0,1],[1,0]], complex)
    sz = np.array([[1,0],[0,-1]], complex)
    H = np.zeros((2*N, 2*N), complex)
    for i in range(N):
        H[2*i:2*i+2, 2*i:2*i+2] += Mx[i]*sz
        if i+1 < N:
            D = -1j*v*sx/(2*dx)   # 중앙차분 운동량
            H[2*i:2*i+2, 2*(i+1):2*(i+1)+2] += D
            H[2*(i+1):2*(i+1)+2, 2*i:2*i+2] += D.conj().T
    ev, evec = np.linalg.eigh(H)
    return x, ev, evec

x, ev, evec = jackiw_rebbi()
i0 = np.argmin(np.abs(ev))
print(f"가장 0에 가까운 에너지: {ev[i0]:.4e}  (영모드)")
# 영모드 파동함수가 x=0 (질량 부호변화 지점)에 국소화되는지
psi = evec[:, i0].reshape(-1, 2)
density = np.sum(np.abs(psi)**2, axis=1)
peak = x[np.argmax(density)]
print(f"영모드 국소화 위치 x ≈ {peak:.2f} (질량 부호변화점 x=0 근처)")
# => 위상 경계에 묶인 갭 없는 상태 = 벌크-경계 대응의 미시 메커니즘
```

## 🧪 실험·관측 증거

- **양자 스핀홀(2007)**: HgTe 양자우물에서 두께가 임계값($6.3\,\mathrm{nm}$) 초과 시 가장자리 전도 $G=2e^2/h$ (두 헬리컬 채널) 관측 — 벌크 절연·가장자리 도체의 직접 증거.
- **ARPES 디랙 표면 상태**: $\text{Bi}_2\text{Se}_3$ 표면에 단일 디랙 콘을 각분해 광전자분광으로 직접 영상화(Xia 외, *Nature Physics* 2009). 스핀–운동량 잠금을 스핀 분해 ARPES 로 확인.
- **약반국소화 → 약국소화 전이**: 디랙 표면 상태의 베리 위상 $\pi$ 가 만드는 약반국소화 자기저항 — 위상의 수송 신호.
- **비국소 수송**: QSH 에서 가장자리 채널을 통한 비국소 저항이 헬리컬 모드 예측과 일치.

## 🔬 경계

- **시간역전이 깨지면 보호 상실**: 자성 불순물·자기장이 가장자리 갭을 열어 후방산란 허용. $\mathbb{Z}_2$ 보호는 시간역전 보존이 전제.
- **상호작용**: 강한 상호작용은 가장자리에서 자발적 시간역전 깨짐(에지 자성)이나 분수화를 일으켜 단일입자 $\mathbb{Z}_2$ 그림을 넘어선다.
- **벌크 전도 잔류**: 실제 $\text{Bi}_2\text{Se}_3$ 는 결함 도핑으로 벌크가 완전 절연이 아니어서 표면 수송을 가리기 쉽다 — 표면 신호 분리가 실험적 난제.
- **상호작용 분류의 변화**: $\mathbb{Z}_2$ (자유 페르미온) 분류가 상호작용으로 붕괴/축소되는 경우가 있다(예: $\mathbb{Z}\to\mathbb{Z}_8$ in 일부 초전도체 클래스).

## 🧬 횡단 원리

- **(→ symmetry-conservation)**: $\mathbb{Z}_2$ 위상은 *대칭이 보호하는* 위상(SPT)의 원형 — 시간역전이라는 대칭 없이는 두 상이 연속 연결된다. 대칭과 위상의 결합.
- **(→ standard-model)**: 단일 디랙 콘·페르미온 더블링 회피는 격자 게이지 이론의 카이럴 변칙과 같은 수학. 위상 절연체 표면 = 변칙 경계 이론.
- **(→ quantum-information)**: 후방산란 금지는 정보 채널이 잡음에 면역인 메커니즘 — 위상 보호(→ [05](./05-topological-protection.md))로 이어진다.

## 🪜 창발

- **(L5 holography)**: 벌크 $\nu$ 가 경계 변칙(단일 디랙 콘)을 강제하는 벌크–경계 대응은 변칙 유입(anomaly inflow)·홀로그래피의 응집물질 실현.
- **(L6 emergence)**: 보통/위상 절연체의 구분은 *국소 측정으로는 보이지 않는* 전역 성질에서 창발 — 같은 갭, 같은 대칭, 다른 위상. 창발하는 분류의 새 축.

## 📐 예측·반증

- **정량 예측**: QSH 가장자리 전도 $G=2e^2/h$ (헬리컬 쌍 1개). 밴드 반전 임계 두께에서 위상 상전이.
- **반증 가능성**: 만약 표면 상태가 위상적으로 보호된 게 아니라면, 비자성 불순물 농도를 높일 때 표면 전도가 사라져야 한다. 실측은 비자성 무질서에 강건 — $\mathbb{Z}_2$ 보호를 지지. 반대로 자성 도핑은 갭을 열어야 하고, 실제로 연다.
- **벌크–경계 검증**: 표면 디랙 콘 수의 홀짝이 벌크 $\nu_0$ 와 일치해야 한다(강 TI 는 홀수). ARPES 확인.

## 🤔 다음 질문

가장자리/표면 모드가 *왜* 그렇게 견고한가 — 후방산란 금지·연속 변형 불변성의 일반 원리는 무엇인가? 그리고 그 견고함을 어디까지 밀어붙이면 양자 정보를 보호하는 데 쓸 수 있는가? 다음 문서에서 위상 보호의 일반 메커니즘과 위상 양자 오류정정의 토대를 다룬다.

---

🧩 **Principle** — 시간역전 대칭과 크라머스 정리가 천 수를 0으로 누르는 곳에서 $\mathbb{Z}_2$ 불변량이 등장하고, 밴드 반전(BHZ)이 비자명할 때 벌크–경계 대응이 후방산란 면역의 헬리컬 가장자리·단일 디랙 표면을 강제한다.
🔬 **Boundary** — 시간역전이 깨지거나 강한 상호작용이 끼면 $\mathbb{Z}_2$ 보호가 붕괴/축소되고, 실제 시료의 벌크 잔류 전도가 표면 신호를 가린다.
🪜 **Emergence** — 국소적으로 안 보이는 전역 분류에서 보호된 경계가 창발하는 이 구조는 위 레이어에서 변칙 유입·홀로그래피·위상 정보 보호로 재등장하고, QSH 전도 $2e^2/h$·단일 디랙 콘으로 검증된다.

## 📝 연습문제

**1. (기초)** 스핀-1/2 의 시간역전 연산자가 $\Theta^2=-1$ 임을 $\Theta=i\sigma_y K$ 로 직접 보이고, 이것이 왜 크라머스 겹침(모든 준위 짝수 겹침)을 함의하는지 설명하라.

<details><summary>해설</summary>

$\Theta^2=i\sigma_y K\, i\sigma_y K=i\sigma_y\,(i\sigma_y)^* KK=i\sigma_y(-i\sigma_y^*)=i\sigma_y(-i)(-\sigma_y)=i\cdot i\,\sigma_y\sigma_y=-\sigma_y^2=-1$ (∵ $\sigma_y^*=-\sigma_y$, $K^2=1$). 

크라머스: $|\psi\rangle$ 와 $\Theta|\psi\rangle$ 는 같은 에너지($[\Theta,H]=0$)인데, 둘이 직교함을 보이자. $\langle\psi|\Theta\psi\rangle=\langle\Theta^2\psi|\Theta\psi\rangle^*=\langle-\psi|\Theta\psi\rangle^*=-\langle\Theta\psi|\psi\rangle=-\langle\psi|\Theta\psi\rangle$ (반유니터리 성질). 따라서 $\langle\psi|\Theta\psi\rangle=0$ — 두 상태는 직교한 별개 상태이고 같은 에너지를 가지므로 모든 준위는 최소 2중 겹침. TRIM 에서 밴드가 반드시 붙는 이유다.
</details>

**2. (심화)** BHZ 한 스핀 블록 $\mathbf{d}=(Ak_x,Ak_y,M-Bk^2)$ 의 천 수가 $C=\tfrac12[\text{sgn}(M)+\text{sgn}(B)]$ 임을 $\hat{\mathbf d}$ 의 무한대·원점 거동으로 논증하라. 위상 상전이가 일어나는 조건은?

<details><summary>해설</summary>

천 수는 $\hat{\mathbf d}$ 가 구를 덮는 횟수. $k\to0$ 에서 $d_z\to M$, $k\to\infty$ 에서 $d_z\to -Bk^2\to-\infty\cdot\text{sgn}(B)$. $(d_x,d_y)=(Ak_x,Ak_y)$ 는 평면에서 한 번 감긴다. $\hat d_z$ 가 원점($+\text{sgn}M$)에서 무한대($-\text{sgn}B$)로 *부호를 바꿔야* $\hat{\mathbf d}$ 가 북극·남극을 모두 덮어 $|C|=1$. 즉 $\text{sgn}(M)=\text{sgn}(B)$ 일 때 $C=\pm1$(반전상), $\text{sgn}(M)\neq\text{sgn}(B)$ 면 한쪽 극만 덮어 $C=0$(자명). 이를 합치면 $C=\tfrac12[\text{sgn}M+\text{sgn}B]$. 위상 상전이는 $M=0$ (갭 닫힘)에서 일어나며, HgTe 양자우물의 임계 두께가 바로 $M$ 의 부호가 바뀌는 곳이다.
</details>

**3. (논문 비평)** König 외(2007)의 QSH 가장자리 전도는 $2e^2/h$ 에 가까웠지만 정확히 양자화되지 않았고, 긴 시료에서는 값이 떨어졌다. 위상 보호가 후방산란을 *완전히* 금지한다면 왜 이런 편차가 생기는가? 어떤 메커니즘이 헬리컬 가장자리에서도 산란을 허용할 수 있는가?

<details><summary>해설</summary>

단일입자·시간역전 보존 한정에서만 후방산란이 엄밀히 금지된다. 실제 편차의 원인: (1) *비탄성·다체* 과정 — 두 전자가 협력하면(전자–전자 상호작용) 시간역전을 깨지 않고도 가장자리 전류를 일부 산란시킬 수 있다; (2) 자성 불순물 — 미량이라도 국소적으로 시간역전을 깨 후방산란을 연다; (3) 가장자리 사이/벌크 잔류 전도와의 누설; (4) 충전 무질서로 인한 가장자리 채널의 부분적 국소화(긴 시료일수록 누적). 따라서 "완전 양자화" 는 짧고 깨끗하며 자성 없는 극한에서만 기대되고, 긴 시료의 값 저하는 위상 보호가 *단일입자·대칭 보존 범위* 안에서만 작동함을 정직하게 드러낸다 — 보호의 경계를 보여주는 데이터다.
</details>

---

<div align="center">

[◀ 이전: 분수 양자홀](./03-fractional-quantum-hall.md)  ·  [📚 README](../README.md)  ·  [다음: 위상 보호 ▶](./05-topological-protection.md)

</div>
