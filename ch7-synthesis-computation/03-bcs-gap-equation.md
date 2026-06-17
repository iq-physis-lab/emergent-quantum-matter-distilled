# BCS 갭 방정식 — 자기일관 풀이

> *갭 $\Delta$ 는 방정식의 우변에도 좌변에도 들어 있다. 자기 자신을 입력으로 받아 자기 자신을 출력하는 이 자기일관 고리를 numpy 반복으로 돌리면 — $\Delta(T)$ 곡선이, $T_c$ 가, 그리고 물질에 무관한 보편비 $\Delta(0)/k_BT_c\approx1.764$ 가 저절로 나온다.*

## 🎯 핵심 질문

- BCS 갭 방정식 $1=g\sum_{\mathbf{k}}\frac{1}{2E_{\mathbf{k}}}\tanh\frac{E_{\mathbf{k}}}{2k_BT}$ 는 왜 $\Delta=0$ 이 항상 자명해이면서도, 결합 $g>0$ 이면 *유한한* $\Delta\neq0$ 해가 더 낮은 에너지로 존재하는가 — 페르미면이 무한소 인력에도 불안정한 이유는?
- 이 비선형 방정식을 손으로 못 푸는데, 자기일관 반복(고정점 iteration)으로 어떻게 수렴시키고, 온도를 올리면 $\Delta(T)$ 가 어떻게 0으로 떨어져 $T_c$ 를 정의하나?
- 약결합 극한에서 $\Delta(0)$ 와 $T_c$ 가 각각 $g$ 에 지수적으로 의존하는데도, 그 비 $\Delta(0)/k_BT_c$ 가 *물질·결합에 무관한 보편 상수 1.764* 인 이유는 — 그리고 코드가 정말 그 수를 뱉는가?

## 🌍 어디서 나타나나

- **모든 BCS 초전도체**: Al, Pb, Nb 등 전통 초전도체의 갭·$T_c$·비열 점프를 정량 예측. $\Delta(0)/k_BT_c$ 가 1.7~1.8 로 측정됨.
- **터널링 분광·ARPES**: 초전도 갭 $\Delta(T)$ 의 온도 의존을 직접 측정 — BCS 곡선과 비교.
- **냉원자 페르미 기체**: BCS–BEC 크로스오버에서 갭 방정식의 강결합 확장을 검증.
- **수치 초전도학의 기초**: 엘리아시버그(Eliashberg) 이론·BdG 자기일관 풀이의 개념적·알고리즘적 원형.

## 🔍 직관의 함정

**함정 1 — "약한 인력이면 초전도도 약하게만 생긴다."** 아니다. 갭과 $T_c$ 는 결합에 $e^{-1/N(0)g}$ 로 *지수적* 으로 의존 — 비섭동적이다. 페르미면은 *아무리 약한* 인력에도 불안정하다(쿠퍼 불안정). 결합이 작으면 $\Delta$ 가 지수적으로 작아질 뿐, 0이 되지는 않는다.

**함정 2 — "갭 방정식은 일반 방정식처럼 풀면 된다."** 갭이 우변($E_k=\sqrt{\xi_k^2+\Delta^2}$ 안)과 정규화 조건 양쪽에 들어 있어 *자기일관* — $\Delta_{\text{out}}=F[\Delta_{\text{in}}]$ 의 고정점을 반복으로 찾아야 한다. 평균장 자기일관성의 전형.

**함정 3 — "비 $\Delta(0)/k_BT_c$ 는 물질마다 다를 것이다."** 약결합 BCS 에서는 결합·차단·상태밀도가 모두 지수에 같은 방식으로 들어가 비에서 상쇄된다. 남는 것은 순수한 수 $\pi/e^\gamma\approx1.764$ — 보편 상수다. 실험이 이를 확증한다.

## ⚙️ 제1원리 유도

### 1) 평균장 BCS 해밀토니안과 갭 방정식

포논 매개 인력 $-g$ (페르미면 근처 에너지 창 $|\xi_k|<\hbar\omega_D$ 안에서)에서 BCS 축약 해밀토니안을 평균장 처리(보골류보프 변환)하면 준입자 에너지

$$
E_{\mathbf{k}}=\sqrt{\xi_{\mathbf{k}}^2+\Delta^2},\qquad \xi_{\mathbf{k}}=\epsilon_{\mathbf{k}}-\mu,
$$

그리고 갭의 자기일관 조건(→ [../ch3-superconductivity-superfluid/03-bcs-theory.md](../ch3-superconductivity-superfluid/03-bcs-theory.md) 에서 유도):

$$
\boxed{\Delta=g\sum_{\mathbf{k}}\frac{\Delta}{2E_{\mathbf{k}}}\tanh\frac{E_{\mathbf{k}}}{2k_BT}
\;\Longleftrightarrow\;
1=g\sum_{\mathbf{k}}\frac{1}{2E_{\mathbf{k}}}\tanh\frac{E_{\mathbf{k}}}{2k_BT}\ (\Delta\neq0).}\quad\square
$$

$\Delta=0$ 은 늘 해(정상상태). $\Delta\neq0$ 해가 존재하면 그것이 더 낮은 자유에너지 → 초전도가 이긴다.

### 2) 연속 극한 — 상태밀도로 적분

페르미면 근처에서 합을 상태밀도 $N(0)$(페르미준위 단위 에너지당)로 적분으로 바꾸고, 인력이 $|\xi|<\hbar\omega_D$ 에서만 작동하면

$$
1=N(0)g\int_0^{\hbar\omega_D}\frac{d\xi}{\sqrt{\xi^2+\Delta^2}}\tanh\frac{\sqrt{\xi^2+\Delta^2}}{2k_BT}.
$$

무차원 결합 $\lambda\equiv N(0)g$. 이 한 적분 방정식이 모든 것을 담는다.

### 3) $T=0$, 약결합 — 갭의 지수적 작음

$T=0$ 이면 $\tanh\to1$. 적분 $\int_0^{\hbar\omega_D}d\xi/\sqrt{\xi^2+\Delta^2}=\operatorname{arcsinh}(\hbar\omega_D/\Delta)\approx\ln(2\hbar\omega_D/\Delta)$ ($\Delta\ll\hbar\omega_D$). 따라서

$$
1=\lambda\ln\frac{2\hbar\omega_D}{\Delta(0)}\;\Longrightarrow\;
\boxed{\Delta(0)=2\hbar\omega_D\,e^{-1/\lambda}.}\quad\square
$$

지수적 의존 — 섭동론으로는 절대 나올 수 없는 비해석적 결과. 쿠퍼 불안정의 정량적 얼굴.

### 4) $\Delta\to0$ 극한 — 임계온도

$T\to T_c$ 에서 $\Delta\to0$, $E\to|\xi|$. 갭 방정식이 선형화되어

$$
1=\lambda\int_0^{\hbar\omega_D}\frac{d\xi}{\xi}\tanh\frac{\xi}{2k_BT_c}.
$$

표준 적분 결과(오일러 상수 $\gamma\approx0.5772$):

$$
\boxed{k_BT_c=\frac{2e^\gamma}{\pi}\hbar\omega_D\,e^{-1/\lambda}\approx1.134\,\hbar\omega_D\,e^{-1/\lambda}.}\quad\square
$$

### 5) 보편비 — 물질을 잊는 상수

$\Delta(0)$ 와 $k_BT_c$ 를 나누면 $\hbar\omega_D e^{-1/\lambda}$ 가 정확히 상쇄:

$$
\boxed{\frac{\Delta(0)}{k_BT_c}=\frac{2\hbar\omega_D e^{-1/\lambda}}{(2e^\gamma/\pi)\hbar\omega_D e^{-1/\lambda}}=\frac{\pi}{e^\gamma}\approx1.764.}\quad\square
$$

결합·차단진동수·상태밀도가 모두 사라지고 — 순수한 수만 남는다. 이것이 BCS 의 가장 아름다운 예언이다.

### 실험 1 — 갭 방정식 자기일관 반복으로 $\Delta(0)$ 풀기

```python
import numpy as np

def gap_at_T(T, lam=0.3, wD=1.0, Nk=4000, tol=1e-11):
    """1 = λ ∫₀^wD dξ (Δ/E) tanh(E/2T) 를 Δ 에 대해 고정점 반복.
       (ħ=k_B=1, ξ 는 [0,wD] 양쪽 대칭의 절반, 상태밀도 N(0) 는 λ 에 흡수)"""
    xi = np.linspace(0, wD, Nk)
    D = 0.5 * wD                       # 초기 추정
    for _ in range(10000):
        E = np.sqrt(xi**2 + D**2)
        tanh = np.ones_like(E) if T < 1e-12 else np.tanh(E/(2*T))
        D_new = lam * np.trapezoid(D / E * tanh, xi)   # 우변 = 새 Δ
        if abs(D_new - D) < tol:
            D = D_new; break
        D = D_new
    return D

lam, wD = 0.3, 1.0
D0 = gap_at_T(0.0, lam, wD)
D0_analytic = 2*wD*np.exp(-1/lam)
print(f"수치   Δ(0) = {D0:.6f}")
print(f"이론   Δ(0) = 2ωD e^(-1/λ) = {D0_analytic:.6f}")
print(f"상대오차 = {abs(D0-D0_analytic)/D0_analytic*100:.2f}%")
# 자기일관 반복이 약결합 해석해와 0.X% 이내로 일치
```

출력: $\Delta(0)\approx0.07144$, 해석해 $2\omega_D e^{-1/\lambda}=0.07135$ 와 0.13% 이내 일치. 자기 자신을 먹는 고리가 정확히 수렴한다.

### 실험 2 — $\Delta(T)$ 곡선과 $T_c$, 그리고 보편비 1.764

```python
import numpy as np
import matplotlib.pyplot as plt

# (실험 1의 gap_at_T 재사용)
lam, wD = 0.3, 1.0
D0 = gap_at_T(0.0, lam, wD)

# Δ(T) 스캔
Ts = np.linspace(0.001, 0.05, 120)
Ds = np.array([gap_at_T(T, lam, wD) for T in Ts])

# Tc 정밀 결정: 갭이 사라지는 온도를 이분법으로
def has_gap(T):
    return gap_at_T(T, lam, wD) > 1e-4
lo, hi = 0.001, 0.06
for _ in range(45):
    mid = (lo+hi)/2
    if has_gap(mid): lo = mid
    else: hi = mid
Tc = (lo+hi)/2

print(f"Δ(0)        = {D0:.5f}")
print(f"Tc          = {Tc:.5f}")
print(f"Δ(0)/k_B Tc = {D0/Tc:.4f}   (BCS 보편비 π/e^γ = {np.pi/np.exp(0.5772):.4f})")

plt.figure(figsize=(6,4))
plt.plot(Ts/Tc, Ds/D0, 'o-', ms=3)
plt.xlabel(r"$T/T_c$"); plt.ylabel(r"$\Delta(T)/\Delta(0)$")
plt.title("BCS 갭의 온도 의존 (자기일관 풀이)")
plt.axhline(0, c='gray', ls=':'); plt.axvline(1, c='r', ls=':')
plt.tight_layout(); plt.savefig("bcs_gap_T.png", dpi=110)
print("저장: bcs_gap_T.png")
# 출력: Δ(0)/kTc ≈ 1.76 — 물질·결합에 무관한 보편 상수, 코드가 직접 재현
```

출력: $\Delta(0)/k_BT_c\approx1.76$ — 보편비 $\pi/e^\gamma=1.7639$ 를 직접 재현. $\Delta(T)/\Delta(0)$ 곡선은 $T_c$ 근처에서 $\sqrt{1-T/T_c}$ 처럼 0으로 떨어진다.

### 실험 3 — 결합 $\lambda$ 를 바꿔도 비는 불변 (보편성 시연)

```python
import numpy as np

# (gap_at_T 재사용)
wD = 1.0
print(f"{'λ':>6} {'Δ(0)':>12} {'Tc':>12} {'Δ(0)/Tc':>10}")
for lam in [0.2, 0.3, 0.4, 0.5]:
    D0 = gap_at_T(0.0, lam, wD)
    # Tc 이분법
    lo, hi = 1e-4, 0.4
    for _ in range(45):
        mid = (lo+hi)/2
        if gap_at_T(mid, lam, wD) > 1e-4: lo = mid
        else: hi = mid
    Tc = (lo+hi)/2
    print(f"{lam:>6.2f} {D0:>12.6f} {Tc:>12.6f} {D0/Tc:>10.4f}")
# Δ(0) 와 Tc 는 λ 에 따라 지수적으로 크게 변하지만, 그 비는 ~1.76 으로 고정
# (강결합 λ→0.5 에서 약결합 근사가 약간 벗어나 1.76 에서 살짝 이탈)
```

출력: $\lambda$ 가 0.2→0.5 로 바뀌면 $\Delta(0)$ 와 $T_c$ 는 자릿수가 달라지지만, 비는 약결합에서 1.76 근처로 고정. 보편성을 수치로 목격.

## 🧪 실험·관측 증거

- **터널링 분광**: Al $\Delta(0)/k_BT_c\approx1.7$, Sn $\approx1.75$, Pb $\approx2.15$(강결합 보정). 약결합 BCS 1.764 와 정량 일치/체계적 이탈.
- **갭의 온도 의존**: 측정된 $\Delta(T)$ 가 BCS 곡선($T_c$ 근처 $\sqrt{1-T/T_c}$)을 따른다.
- **비열 점프**: $T_c$ 에서 $\Delta C/\gamma T_c\approx1.43$(BCS 예언) 관측.
- **동위원소 효과**: $T_c\propto M^{-1/2}$ — $\hbar\omega_D\propto M^{-1/2}$ 가 지수 앞 인자로 들어가는 BCS 예언 확증, 포논 매개의 직접 증거.

## 🔬 경계

- **강결합**: $\lambda\gtrsim0.3$ 이면 약결합 근사가 깨져 비가 1.764 를 벗어남(Pb $\approx2.15$). 엘리아시버그 이론(지연·감쇠 포함)이 필요.
- **비등방·비전통 짝짓기**: d-파(고온 초전도)·p-파는 $\Delta(\mathbf{k})$ 가 방향 의존 — 단일 스칼라 갭 방정식으로 안 됨. 노드·각의존 비.
- **고온 초전도**: 의사갭·강상관에서 BCS 평균장 자체가 의심받음(→ [../ch6-quantum-phase-correlation/04-high-tc-superconductivity.md](../ch6-quantum-phase-correlation/04-high-tc-superconductivity.md)). 메커니즘 미해결.
- **요동**: 저차원·작은 결맞음 길이에서 평균장이 무너지고 위상 요동이 지배(→ [../ch2-many-body-quasiparticle/05-mean-field-beyond.md](../ch2-many-body-quasiparticle/05-mean-field-beyond.md)).

## 🧬 횡단 원리

- **(→ phase-transitions)**: 갭 방정식은 자기일관 평균장 — 강자성 Weiss 장·란다우 이론과 같은 구조. $\Delta$ 는 초전도 질서변수의 크기.
- **(→ symmetry-conservation)**: 초전도는 $U(1)$ 게이지 대칭의 자발 깨짐. $\Delta=|\Delta|e^{i\varphi}$ 의 위상 $\varphi$ 가 골드스톤(앤더슨–힉스로 흡수)(→ [../ch3-superconductivity-superfluid/04-macroscopic-coherence.md](../ch3-superconductivity-superfluid/04-macroscopic-coherence.md)).
- **(→ statistical-mechanics)**: $\tanh(E/2k_BT)$ 는 보골류보프 준입자의 페르미–디랙 점유에서 직접. 유한온도 응축의 통계.

## 🪜 창발

- **(L5 holography)**: 홀로그래픽 초전도체(전하 응축의 중력 쌍대)에서도 같은 모양의 갭·$T_c$ 가 블랙홀 불안정으로 창발 — 강상관 초전도의 홀로그래피 기술.
- **(L6 emergence)**: 자기 자신을 입력으로 받는 자기일관 고리에서 거시적 결맞음·저항 0 이 창발하는 구조 — 미시 인력에서 거시 질서가 비섭동적으로 나오는 창발의 정량 모형.

## 📐 예측·반증

- **정량 예측**: 약결합 $\Delta(0)/k_BT_c=\pi/e^\gamma\approx1.764$, 비열 점프 1.43, $\Delta(0)=2\hbar\omega_D e^{-1/\lambda}$.
- **반증 가능성**: 만약 약결합 단순금속에서 비가 1.764 와 크게(>10%) 다르면 BCS 가 틀린 것 — Al·Sn 등이 정확히 1.7~1.8 로 확증.
- **수치 검증**: 자기일관 반복이 $\lambda$ 와 무관하게 약결합에서 비를 1.76 으로 재현해야 함(실험 2·3 확증).

## 🤔 다음 질문

BCS 는 *평균장* 이다 — 쿠퍼 쌍을 응축장으로 다루어 다체 문제를 단일입자 문제로 환원했다. 그러나 강한 상호작용(허바드 $U$)에서는 평균장이 통째로 무너진다. 거기서는 작은 격자라도 *전체* 힐베르트 공간을 정직하게 대각화하는 길밖에 없다. 다음 문서에서 점유수 기저로 허바드·횡자기장 이징 해밀토니안을 scipy.sparse 로 정확 대각화해, 모트 갭이 $U$ 와 함께 열리는 것과 반강자성 스핀 상관을 직접 본다.

---

🧩 **Principle** — 페르미면은 아무리 약한 인력에도 불안정하여, 자기 자신을 입력으로 받는 갭 방정식의 고정점에서 유한 갭 $\Delta(0)=2\hbar\omega_D e^{-1/\lambda}$ 와 거시 결맞음이 창발하고, 비 $\Delta(0)/k_BT_c=\pi/e^\gamma\approx1.764$ 는 물질을 잊는 보편 상수다.
🔬 **Boundary** — 강결합·비등방 짝짓기·고온 초전도·저차원 요동에서 약결합 평균장과 보편비가 깨진다.
🪜 **Emergence** — 자기일관 고리에서 비섭동적 질서가 나오는 이 구조는 위 레이어에서 홀로그래픽 초전도로 재등장하고, Al·Sn 의 측정 비 1.7~1.8 과 자기일관 반복의 1.76 재현으로 검증된다.

## 📝 연습문제

**1. (기초)** $T=0$ 갭 방정식 $1=\lambda\int_0^{\hbar\omega_D}d\xi/\sqrt{\xi^2+\Delta^2}$ 에서 $\Delta\ll\hbar\omega_D$ 근사로 $\Delta(0)=2\hbar\omega_D e^{-1/\lambda}$ 를 유도하라. 적분이 $\operatorname{arcsinh}(\hbar\omega_D/\Delta)$ 임을 이용.

<details><summary>해설</summary>

$\int_0^{a}d\xi/\sqrt{\xi^2+\Delta^2}=\operatorname{arcsinh}(a/\Delta)=\ln\!\big(a/\Delta+\sqrt{(a/\Delta)^2+1}\big)$. $a=\hbar\omega_D\gg\Delta$ 이면 $\approx\ln(2a/\Delta)=\ln(2\hbar\omega_D/\Delta)$. 갭 방정식 $1=\lambda\ln(2\hbar\omega_D/\Delta)$ → $\ln(2\hbar\omega_D/\Delta)=1/\lambda$ → $\Delta=2\hbar\omega_D e^{-1/\lambda}$. 지수의 $-1/\lambda$ 가 비해석적 — 섭동급수 $\sum c_n\lambda^n$ 으로는 $\lambda=0$ 근방에서 절대 재현 불가. 이것이 초전도가 "섭동으로 안 보이는" 이유.
</details>

**2. (심화)** 갭 방정식을 $T_c$ 근처에서 선형화($\Delta\to0$)하면 $1=\lambda\int_0^{\hbar\omega_D}\frac{d\xi}{\xi}\tanh\frac{\xi}{2k_BT_c}$. 이 적분에서 $k_BT_c=\frac{2e^\gamma}{\pi}\hbar\omega_D e^{-1/\lambda}$ 가 나옴을 보이고(부분적분·디감마 함수 점근), 보편비 $\Delta(0)/k_BT_c=\pi/e^\gamma$ 를 확인하라.

<details><summary>해설</summary>

$I=\int_0^{w}\frac{d\xi}{\xi}\tanh\frac{\xi}{2T}$ ($w=\hbar\omega_D$, $k_B=1$). 부분적분 $u=\tanh(\xi/2T)$, $dv=d\xi/\xi$ 로 $\ln\xi$ 항이 나오고, $\xi\gg T$ 에서 $\tanh\to1$, $\xi\ll T$ 에서 $\tanh\approx\xi/2T$. 표준 결과는 $I=\ln\frac{2e^\gamma w}{\pi T}$ ($w\gg T$, $\gamma$=오일러 상수). 갭 방정식 $1=\lambda\ln\frac{2e^\gamma w}{\pi T_c}$ → $T_c=\frac{2e^\gamma}{\pi}w\,e^{-1/\lambda}$. 한편 $\Delta(0)=2w e^{-1/\lambda}$. 나누면 $\Delta(0)/T_c=\frac{2}{(2e^\gamma/\pi)}=\frac{\pi}{e^\gamma}=\frac{3.1416}{1.781}\approx1.764$. 지수와 $w$ 가 완전 상쇄 → 보편 상수.
</details>

**3. (논문 비평)** BCS 약결합 비 1.764 는 단순금속에서 잘 맞지만, Pb($\approx2.15$)·고온 초전도체($\approx4{-}8$, d-파)에서는 크게 벗어난다. (a) Pb 의 이탈을 엘리아시버그(강결합·지연) 관점에서, (b) 고온 초전도의 큰 비를 d-파 갭·강상관·의사갭 관점에서 설명하고, "보편비" 라는 표현이 어디까지 유효한지 비판적으로 논하라.

<details><summary>해설</summary>

(a) Pb: 전자–포논 결합 $\lambda\approx1.5$ 로 강결합. BCS 의 순간 인력 가정이 깨지고, 포논 교환의 *지연*(retardation)과 준입자 *감쇠* 를 엘리아시버그 방정식이 포함하면 비가 1.764 에서 위로 보정($\sim2.1$)된다 — $T_c/\omega_D$ 가 커질수록 강결합 보정 $\sim(T_c/\omega_D)\ln(\omega_D/T_c)$ 가 비를 키운다. (b) 고온 초전도: 갭이 d-파($\Delta_{\mathbf{k}}\propto\cos k_x-\cos k_y$)라 노드가 있고 최대 갭이 평균보다 커, "$\Delta_{\max}/k_BT_c$" 로 정의하면 $4{-}8$ 로 치솟는다. 게다가 의사갭이 $T_c$ 위에서 이미 갭을 열어 $T_c$ 와 갭이 *분리* — 단일 평균장 비 자체가 무의미해진다. 결론: "보편비 1.764" 는 *약결합·s-파·BCS 평균장* 이라는 좁은 가정에서만 보편적이다. 강결합·비등방·강상관으로 가면 비는 물질·메커니즘 의존이 되고, 1.764 는 보편 상수가 아니라 *이상적 BCS 의 기준점* 으로 읽어야 한다. 측정된 비가 1.764 에서 벗어나는 정도가 곧 "BCS 에서 얼마나 멀어졌는가" 의 진단 지표다.
</details>

---

<div align="center">

[◀ 이전: 천 수 계산](./02-chern-number-numerics.md)  ·  [📚 README](../README.md)  ·  [다음: 허바드/이징 다체 ▶](./04-hubbard-ising-exact-diag.md)

</div>
