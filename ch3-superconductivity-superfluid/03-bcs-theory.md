# BCS 이론 — 쿠퍼 쌍의 창발

> *페르미면 위의 두 전자는 *아무리 약한* 인력에도 묶인다 — 이 로그 발산이 페르미 바다를 불안정하게 만들어, 포논 매개 쿠퍼 쌍이 응축하고 에너지 갭 $\Delta$ 가 창발한다.*

## 🎯 핵심 질문

- 전자끼리는 쿨롱 반발을 하는데, *어떻게* 인력이 생겨 짝을 짓는가? 그리고 왜 인력이 *아무리 약해도* 묶임이 일어나는가(쿠퍼 문제의 로그 발산)?
- 페르미 바다가 짝짓기에 *불안정* 하다는 것 — 진짜 바닥상태가 채워진 페르미 구가 아니라 *응축한 쌍* 임을 — 어떻게 보이는가(BCS 변분·보골류보프)?
- 에너지 갭 $\Delta$ 는 갭 방정식 $1=g\sum_k\frac{1}{2E_k}\tanh\frac{E_k}{2k_BT}$ 에서 어떻게 자기일관으로 결정되며, 왜 보편비 $\Delta(0)/k_BT_c\approx1.76$ 이 나오는가?

## 🌍 어디서 나타나나

- **원소·합금 초전도체**: Al·Sn·Pb·Nb. BCS 가 정량적으로 가장 잘 맞는 무대 — 동위원소 효과($T_c\propto M^{-1/2}$)가 *포논 매개* 임을 직접 증명.
- **터널링 분광**(Giaever): 초전도체–절연체–금속 접합의 I–V 곡선에서 갭 $\Delta$ 가 직접 측정된다 — 전류가 $eV=\Delta$ 에서 켜진다.
- **비열의 지수적 거동**: $T_c$ 아래에서 전자 비열이 $e^{-\Delta/k_BT}$ 로 떨어짐 — 갭의 존재를 열역학으로 확인.
- **He-3 초유체**: 중성 페르미온의 p-파 BCS 짝짓기 — BCS 가 전하 없는 계에도 작동하는 보편 메커니즘임을 보임.
- **냉원자 페르미 기체의 BEC–BCS 크로스오버**: $^6$Li 의 페시바흐 공명으로 상호작용을 조절해 BCS 쌍(느슨한 쿠퍼 쌍)부터 BEC(꽉 묶인 분자)까지 연속적으로 연결.

## 🔍 직관의 함정

**함정 1 — "전자는 서로 반발하니 짝지을 리 없다."** 동적 차폐를 무시한 오해. 한 전자가 양이온 격자를 *끌어당겨* 일시적 양전하 과잉을 남기면, 그 자리를 다른 전자가 *지연된 인력* 으로 느낀다. 이 포논 매개 인력은 $\omega<\omega_D$(드바이 진동수) 영역에서 차폐된 쿨롱 반발을 *이긴다*.

**함정 2 — "쿠퍼 쌍은 두 전자가 손잡고 다니는 작은 분자다."** 아니다. 쿠퍼 쌍의 크기(결맞음 길이 $\xi_0\sim100$ nm–$\mu$m)는 평균 전자 간격($\sim$0.2 nm)보다 *수천 배* 크다 — 수백만 쌍이 서로 겹쳐 있다. 점입자 분자가 아니라 *겹친 거시 응축* 이다.

**함정 3 — "약한 인력이면 효과도 약하겠지."** 정반대. 쿠퍼 문제는 *임의로 작은* 인력에도 *항상* 묶임을 준다 — 결합 에너지가 $e^{-1/N(0)g}$ 로 *비섭동적* 이다. 섭동론으로는 절대 못 잡는다. 이것이 페르미면의 특수성(상태밀도가 유한)이 만든 로그 발산의 위력이다.

**함정 4 — "갭 $\Delta$ 는 그냥 단일입자 에너지 간격이다."** $\Delta$ 는 *응축의 질서변수* 다 — 크기 $|\Delta|$ 와 위상 $\varphi$ 를 갖는 복소량으로, 위상이 초전류를 낳는다(다음 문서). 단순한 띠틈이 아니라 거시 결맞음의 척도.

## ⚙️ 제1원리 유도

### 유도 1 — 쿠퍼 문제: 로그 발산과 묶임

채워진 페르미 바다($|k|<k_F$) 위에 전자 둘만 추가하자(운동량 $+\mathbf k,-\mathbf k$, 총운동량 0). 상대 파동함수를 $\psi=\sum_{k>k_F}a_k\,|{\bf k},-{\bf k}\rangle$ 로 쓰고, 인력 $V_{kk'}=-g$ (단, $\xi_F<\xi_k<\hbar\omega_D$ 인 얇은 껍질에서만, $\xi_k=\epsilon_k-E_F$)를 넣는다. 슈뢰딩거 방정식 $(2\xi_k - E)a_k=-g\sum_{k'}a_{k'}\equiv -gC$ 에서

$$
a_k=\frac{gC}{2\xi_k-E},\qquad C=\sum_k a_k \;\Rightarrow\; 1=g\sum_{k}\frac{1}{2\xi_k-E}.
$$

합을 에너지 적분으로($\sum_k\to N(0)\int_0^{\hbar\omega_D}d\xi$, $N(0)$=페르미면 상태밀도):

$$
1=N(0)g\int_0^{\hbar\omega_D}\frac{d\xi}{2\xi-E}=\frac{N(0)g}{2}\ln\frac{2\hbar\omega_D-E}{-E}.
$$

묶인 상태 $E=-|E_b|<0$ 에 대해 약결합 $N(0)g\ll1$ 극한:

$$
\boxed{\;E_b\approx 2\hbar\omega_D\,e^{-2/N(0)g}\;}\qquad\square
$$

핵심: $g\to0^+$ 라도 $E_b>0$ — **임의 약한 인력이 항상 묶인 쌍을 만든다.** 이는 적분의 *로그 발산*($\int d\xi/\xi$)과 페르미면의 유한 상태밀도 때문이다. 1·2·3차원 자유공간이라면 약한 인력은 묶임을 못 주지만, *페르미 바다 위* 에서는 다르다. 페르미 바다는 짝짓기에 불안정하다.

### 유도 2 — BCS 바닥상태와 보골류보프 변환

쿠퍼 문제는 "두 전자" 만 다뤘다. 모든 전자가 동시에 짝지으면? BCS 시도파동함수

$$
|\text{BCS}\rangle=\prod_k\left(u_k+v_k\,c^\dagger_{k\uparrow}c^\dagger_{-k\downarrow}\right)|0\rangle,\qquad |u_k|^2+|v_k|^2=1,
$$

$|v_k|^2$ 은 쌍 $(k\uparrow,-k\downarrow)$ 이 점유될 확률. 축약 해밀토니안

$$
H=\sum_{k\sigma}\xi_k c^\dagger_{k\sigma}c_{k\sigma}-g\sum_{kk'}c^\dagger_{k\uparrow}c^\dagger_{-k\downarrow}c_{-k'\downarrow}c_{k'\uparrow}.
$$

평균장 $\Delta=g\sum_k\langle c_{-k\downarrow}c_{k\uparrow}\rangle$ 로 풀면, **보골류보프 변환** $\gamma_{k}=u_k c_{k\uparrow}-v_k c^\dagger_{-k\downarrow}$ 이 해밀토니안을 대각화한다. 준입자(보골류본) 에너지

$$
\boxed{\;E_k=\sqrt{\xi_k^2+\Delta^2}\;}\qquad\square
$$

페르미면($\xi_k=0$)에서도 최소 에너지 $|\Delta|$ 가 필요 — *에너지 갭* 이 창발한다. 변분 계수는 $v_k^2=\frac12\!\left(1-\frac{\xi_k}{E_k}\right)$, $u_k^2=\frac12\!\left(1+\frac{\xi_k}{E_k}\right)$.

### 유도 3 — 갭 방정식과 자기일관성

자기일관 조건 $\Delta=g\sum_k\langle c_{-k\downarrow}c_{k\uparrow}\rangle=g\sum_k u_k v_k\,(1-2f(E_k))$ 에 $u_k v_k=\frac{\Delta}{2E_k}$, 페르미 분포 $f(E)=1/(e^{E/k_BT}+1)$, 그리고 $1-2f(E)=\tanh\frac{E}{2k_BT}$ 를 넣으면

$$
\boxed{\;1=g\sum_k\frac{1}{2E_k}\tanh\frac{E_k}{2k_BT},\qquad E_k=\sqrt{\xi_k^2+\Delta^2}\;}\qquad\square
$$

**$T=0$ 갭**: $\tanh\to1$, 적분 $1=N(0)g\int_0^{\hbar\omega_D}\frac{d\xi}{\sqrt{\xi^2+\Delta^2}}=N(0)g\,\text{arcsinh}\frac{\hbar\omega_D}{\Delta}$. 약결합에서

$$
\Delta(0)=2\hbar\omega_D\,e^{-1/N(0)g}.
$$

**$T_c$**: $\Delta\to0$ 이므로 $E_k\to|\xi_k|$, $1=N(0)g\int_0^{\hbar\omega_D}\frac{\tanh(\xi/2k_BT_c)}{\xi}d\xi$. 표준 적분으로

$$
k_BT_c=\frac{2e^\gamma}{\pi}\hbar\omega_D\,e^{-1/N(0)g}\approx1.13\,\hbar\omega_D\,e^{-1/N(0)g},
$$

($\gamma\approx0.577$ 오일러 상수). 두 결과의 비:

$$
\boxed{\;\frac{\Delta(0)}{k_BT_c}=\frac{2}{2e^\gamma/\pi}=\frac{\pi}{e^\gamma}\approx1.764\;}\qquad\square
$$

*재료에 무관한 보편 상수* — 모든 약결합 BCS 초전도체에 성립하는 강력한 예측이다.

### 실험 1 — 갭 방정식 자기일관 풀이로 $\Delta(T)$ 와 보편비

```python
import numpy as np
from scipy.optimize import brentq

# 갭 방정식 1 = N0*g ∫_0^wD dξ/E * tanh(E/2T), E=√(ξ²+Δ²) 를 Δ(T) 에 대해 풀기
# (자연단위: ħ=k_B=1).  ωD, N0*g 를 입력으로 자기일관 해 탐색
wD   = 1.0          # 드바이 컷오프 (에너지 단위)
lam  = 0.3          # N(0)*g 결합상수

xi = np.linspace(1e-6, wD, 4000)   # 0~ωD 의 ξ 격자
dxi = xi[1]-xi[0]

def gap_residual(Delta, T):
    E = np.sqrt(xi**2 + Delta**2)
    integ = np.tanh(E/(2*T)) / E
    return lam * np.trapz(integ, xi) - 1.0   # = 0 이면 자기일관

# T=0 갭 (tanh≈1): brentq 로 Δ 탐색
Delta0 = brentq(lambda D: gap_residual(D, 1e-6), 1e-4, wD)

# Tc: Δ→0 극한에서 residual(Δ→0, T)=0 의 T
def res_Tc(T):
    E = xi  # Δ=0
    return lam*np.trapz(np.tanh(E/(2*T))/E, xi) - 1.0
Tc = brentq(res_Tc, 1e-4, wD)

# Δ(T) 곡선
Ts = np.linspace(1e-3, Tc*0.999, 25)
Delta_T = []
for T in Ts:
    try:
        D = brentq(lambda D: gap_residual(D, T), 1e-6, Delta0*1.5)
    except ValueError:
        D = 0.0
    Delta_T.append(D)

print(f"Δ(0)      = {Delta0:.4f}")
print(f"Tc        = {Tc:.4f}")
print(f"Δ(0)/Tc   = {Delta0/Tc:.3f}   (BCS 보편비 ≈ 1.764)")
print(f"Δ(T) 가 Tc 에서 0 으로 연속 소멸:", 
      np.round(np.array(Delta_T[-4:])/Delta0, 3))
```

자기일관 풀이가 보편비 $\approx1.76$ 을 *재현* 하고, $\Delta(T)$ 가 $T_c$ 에서 0 으로 부드럽게 소멸함을 확인한다.

### 실험 2 — 쿠퍼 결합 에너지의 비섭동성

```python
import numpy as np

# 쿠퍼 묶임 에너지 E_b ≈ 2ωD exp(-2/(N0 g)) 의 비섭동적 의존성
wD = 1.0
N0g = np.linspace(0.05, 0.5, 10)
Eb  = 2*wD*np.exp(-2.0/N0g)

print("N0*g     E_b/ωD        (섭동론 g^n 으로는 절대 못 잡는 형태)")
for x, e in zip(N0g, Eb):
    print(f"{x:.2f}     {e:.3e}")
# g→0 에서 E_b→0 이지만 모든 g>0 에서 E_b>0: 페르미 바다는 항상 불안정
print("\nexp(-2/N0g) 는 g=0 에서 모든 차수 미분이 0 → 본질적 특이점(비섭동)")
```

결합 에너지가 $g$ 의 멱급수가 아니라 본질적 특이점임을 보여, "약해도 항상 묶인다" 의 수학적 근거를 드러낸다.

## 🧪 실험·관측 증거

- **동위원소 효과**: $T_c\propto M^{-\alpha}$, $\alpha\approx0.5$ — 격자 질량이 $T_c$ 를 정하므로 *포논 매개* 임을 직접 입증(BCS 의 결정적 확증).
- **터널링 갭**(Giaever 1960, 노벨상): NIS·SIS 접합에서 $eV=\Delta$(또는 $2\Delta$)의 전류 문턱으로 $\Delta$ 직접 측정 — Al 에서 $2\Delta/k_BT_c\approx3.5$ 확인($=2\times1.76$).
- **비열 점프와 지수 꼬리**: $T_c$ 에서 비열 점프 $\Delta C/C_n\approx1.43$(BCS 예측), $T\ll T_c$ 에서 $\propto e^{-\Delta/k_BT}$ — 갭의 존재 증거.
- **초음파 흡수·NMR 코히어런스 피크**(Hebel–Slichter): 갭과 결맞음 인자(coherence factor)의 정량적 확인 — BCS 의 비자명한 예측 검증.
- **냉원자 BEC–BCS 크로스오버**: 갭·쌍 크기가 상호작용에 따라 연속 변함을 직접 관측.

## 🔬 경계

- **약결합 가정**: 보편비 1.76·3.5·1.43 은 *약결합* BCS 예측이다. Pb·Hg 같은 강결합(엘리아슈베르크) 초전도체는 $2\Delta/k_BT_c\approx4.3$ 까지 벗어난다 — 지연·감쇠 효과를 다루는 엘리아슈베르크 이론이 필요.
- **평균장 한계**: BCS 는 평균장(쌍 요동 무시)이다. 저차원·강상관에서 위상 요동이 평균장 $T_c$ 를 크게 낮춘다(Ch2-05 의 경계). 2D 에서는 BKT 전이가 진짜 $T_c$ 를 정한다.
- **s-파 가정**: 표준 BCS 는 등방 s-파 갭. 고온 구리산화물은 d-파(노드 존재), He-3 은 p-파 — 갭 함수의 *대칭성* 이 다르면 보편비·저온 거동이 달라진다.
- **메커니즘의 미해결**: 고온 초전도는 *무엇이 쌍을 매개하는가*(스핀 요동? 다른 것?)가 미해결이다. BCS 의 *형식*(쌍 응축·갭)은 살아남되 *포논 매개* 가정은 깨진다. (→ ch6-quantum-phase-correlation/04-high-tc-superconductivity.md)

## 🧬 횡단 원리

- **자발 대칭 깨짐**: 갭 $\Delta=|\Delta|e^{i\varphi}$ 의 위상이 $U(1)$ 대칭을 깨뜨린다 — 초유체·강자성과 같은 SSB 구조. 위상이 골드스톤(앤더슨–보골류보프 모드). (→ ch1-more-is-different/04-symmetry-breaking-order.md)
- **평균장과 그 너머**: BCS 는 평균장의 성공 사례지만 그 한계도 함께 보여준다. (→ ch2-many-body-quasiparticle/05-mean-field-beyond.md)
- **준입자의 창발**: 보골류본은 입자–구멍 중첩 준입자 — 마요라나·위상 초전도체의 토대. (→ ch4-topological-matter/06-majorana-anyon.md)
- **포논 매개**: 인력의 매개자가 포논이라는 점은 Ch2 포논과 직접 연결. (→ ch2-many-body-quasiparticle/03-phonon.md)

## 🪜 창발

- **거시 결맞음의 미시 기원**: BCS 는 런던이 *가정* 한 $n_s$·위상 강성을 *유도* 한다 — 다음 문서(GL)가 이 위상을 질서변수로 들어올린다. 위 레이어에서 "미시 짝짓기 → 거시 질서" 는 창발의 원형. (→ L6 emergence)
- **위상 초전도와 마요라나**: 보골류본의 입자–구멍 구조에 위상을 더하면 자기켤레 준입자(마요라나)가 나와, 위상 양자컴퓨팅 자원이 된다. (→ ch4-topological-matter/06-majorana-anyon.md, → quantum-information-distilled)

## 📐 예측·반증

- **보편비** $\Delta(0)/k_BT_c\approx1.76$, $2\Delta/k_BT_c\approx3.53$ — 약결합 BCS. 측정이 크게 벗어나면(예: 4.3) 강결합/비BCS.
- **비열 점프** $\Delta C/\gamma T_c\approx1.43$ — $T_c$ 에서의 보편 도약.
- **동위원소 지수** $\alpha\approx0.5$ — 0 에 가까우면 포논 매개가 아님(반증적).
- **갭의 온도 의존** $\Delta(T)\approx\Delta(0)\sqrt{1-T/T_c}$ ($T\to T_c$), $T_c$ 에서 연속 소멸 — 2차 상전이.

## 🤔 다음 질문

BCS 는 갭 $\Delta=|\Delta|e^{i\varphi}$ 라는 *질서변수* 가 창발함을 보였다. 그런데 미시 BCS 는 균일계에 강하지만, 공간적으로 변하는 자기장·경계·소용돌이를 다루려면 *질서변수의 장이론* 이 필요하다. $\Delta(\mathbf r)$ 가 공간에 따라 변할 때의 자유에너지는? 위상 $\varphi$ 의 *강성* 이 어떻게 초전류와 마이스너를 낳는가? 다음 문서에서 긴즈부르크–란다우 자유에너지로, 결맞음 길이 $\xi$·침투 깊이 $\lambda$·GL 매개변수 $\kappa$ 를 유도하고 1·2종 구분을 완성한다.

---

🧩 **Principle** — 페르미 바다의 짝짓기 불안정(쿠퍼 로그 발산)이 포논 매개 쿠퍼 쌍을 응축시켜 갭 $E_k=\sqrt{\xi_k^2+\Delta^2}$ 을 창발시키고, 자기일관 갭 방정식이 보편비 $\Delta(0)/k_BT_c\approx1.76$ 을 낳는다.
🔬 **Boundary** — 약결합·평균장·s-파 가정은 강결합(엘리아슈베르크)·저차원 위상 요동·d/p-파·고온 메커니즘 미해결에서 깨진다.
🪜 **Emergence** — 미시 짝짓기에서 거시 질서변수가 나오는 구조는 위 레이어의 창발 원리(L6 emergence)로, 보골류본의 입자–구멍 구조는 마요라나·위상 양자컴퓨팅(L3 quantum-information)으로 회수되며, 동위원소 효과·터널링 갭으로 검증된다.

## 📝 연습문제

**1. (기초)** 약결합 BCS 에서 $\Delta(0)=2\hbar\omega_D e^{-1/N(0)g}$, $k_BT_c=1.13\hbar\omega_D e^{-1/N(0)g}$ 이다. 만약 $\hbar\omega_D=300$ K, $N(0)g=0.3$ 이라면 $\Delta(0)$, $T_c$, 그리고 둘의 비를 구하라.

<details><summary>해설</summary>

$e^{-1/0.3}=e^{-3.33}=0.0357$. $\Delta(0)=2\times300\times0.0357\approx21.4$ K(에너지를 K 단위로). $k_BT_c=1.13\times300\times0.0357\approx12.1$ K. 비 $\Delta(0)/k_BT_c=21.4/12.1\approx1.77\approx\pi/e^\gamma$. 보편비가 $\omega_D,g$ 에 *무관* 하게 나옴이 핵심 — 지수 인자가 상쇄된다.
</details>

**2. (심화)** $T=0$ 갭 방정식 $1=N(0)g\int_0^{\hbar\omega_D}\frac{d\xi}{\sqrt{\xi^2+\Delta^2}}$ 를 적분해 $\Delta(0)$ 를 닫힌 형으로 구하고, 약결합 극한에서 $\Delta(0)\approx2\hbar\omega_D e^{-1/N(0)g}$ 임을 보여라.

<details><summary>해설</summary>

$\int_0^{\omega_D}\frac{d\xi}{\sqrt{\xi^2+\Delta^2}}=\text{arcsinh}\frac{\omega_D}{\Delta}=\ln\!\left(\frac{\omega_D}{\Delta}+\sqrt{1+\omega_D^2/\Delta^2}\right)$. 따라서 $1=N(0)g\,\text{arcsinh}(\omega_D/\Delta)$, 즉 $\text{arcsinh}(\omega_D/\Delta)=1/N(0)g$. 약결합 $\Delta\ll\omega_D$ 면 $\text{arcsinh}(\omega_D/\Delta)\approx\ln(2\omega_D/\Delta)$, 그래서 $\ln(2\omega_D/\Delta)=1/N(0)g$, $\Delta=2\hbar\omega_D e^{-1/N(0)g}$. $\square$ 비섭동적 지수 형태가 로그 발산에서 직접 나온다.
</details>

**3. (논문 비평)** 고온 구리산화물은 d-파 갭(노드 존재)이고 $2\Delta/k_BT_c$ 가 BCS 값 3.53 을 크게 벗어난다. 그럼에도 자속 양자는 여전히 $h/2e$ 다. 이 사실들을 종합해 "고온 초전도는 BCS 인가 아닌가" 라는 질문을 비판적으로 분석하라.

<details><summary>해설</summary>

BCS 를 *두 층위* 로 구분해야 한다. (1) **형식적 구조**: 전하 $2e$ 의 쌍 응축, 갭 질서변수, 거시 위상 결맞음 — 고온도 이 구조를 *공유* 한다(자속 양자 $h/2e$ 가 증거). (2) **미시 메커니즘**: 약결합 포논 매개, 등방 s-파, 보편비 3.53 — 고온은 이를 *깬다*(d-파 노드, 큰 비, 의사갭, 비페르미 액체 정상상태). 따라서 답은 "쌍 응축이라는 BCS *패러다임* 은 살아있으나, 포논 매개·약결합·s파라는 *오리지널 BCS 가정* 은 틀렸다." 비판의 핵심: $2\Delta/T_c$ 가 큰 것이 강결합 때문인지, 갭이 $T_c$ 와 무관한 의사갭의 잔재인지, 짝짓기와 위상 결맞음이 분리되는지(전임자 BKT-유사)가 미해결이다. 즉 고온 초전도는 BCS 의 *언어* 로 기술되나 BCS 의 *답* 을 가지지 않는, 정직한 미해결 영역이다.
</details>

---

<div align="center">

[◀ 이전: 초전도 현상 — 거시 양자 상태](02-superconductivity.md)  ·  [📚 README](../README.md)  ·  [다음: 거시적 양자 결맞음 — 질서변수·위상 강성 ▶](04-macroscopic-coherence.md)

</div>
