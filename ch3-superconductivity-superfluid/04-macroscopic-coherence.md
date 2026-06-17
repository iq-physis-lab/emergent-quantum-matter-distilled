# 거시적 양자 결맞음 — 질서변수·위상 강성

> *초전도의 모든 거시 현상은 하나의 복소 질서변수 $\psi=|\psi|e^{i\varphi}$ 에 담긴다 — 위상 $\varphi$ 의 *강성* 이 초전류를 강제하고 마이스너를 낳으며, 두 길이 $\xi,\lambda$ 의 비 $\kappa$ 가 1·2종을 가른다.*

## 🎯 핵심 질문

- 미시 BCS 의 갭 $\Delta$ 를 *공간의 장* $\psi(\mathbf r)$ 으로 들어올리면, 그 자유에너지는 어떤 형태인가? 긴즈부르크–란다우 $F=\alpha|\psi|^2+\frac\beta2|\psi|^4+\frac1{2m^*}|(-i\hbar\nabla-q^*\mathbf A)\psi|^2$ 는 어디서 정당화되는가?
- **위상 강성**(phase rigidity)이란 무엇이며, 왜 위상의 기울기 $\nabla\varphi$ 가 *초전류* 와 *마이스너* 를 동시에 낳는가? 런던이 가정한 제2 방정식이 여기서 어떻게 유도되는가?
- 결맞음 길이 $\xi$ 와 침투 깊이 $\lambda$ 는 GL 자유에너지의 어떤 항에서 나오며, 그 비 $\kappa=\lambda/\xi$ 가 왜 1·2종을 가르는 위상학적 척도인가?

## 🌍 어디서 나타나나

- **초전도/정상 경계와 자속선**: $\psi(\mathbf r)$ 가 경계에서 $\xi$ 규모로 회복하고, 2종 자속선 코어에서 $\psi\to0$ — GL 이 직접 기술하는 공간 구조.
- **마이스너 차폐 전류**: 표면 $\lambda$ 안의 초전류가 GL 의 위상 강성에서 나온다. MRI·가속기 자석이 손실 없이 자기장을 차폐·유지하는 원리.
- **아브리코소프 소용돌이 격자**(2종): $B_{c1}<B<B_{c2}$ 에서 자속선이 삼각 격자로 침투 — GL 방정식의 직접 예측(아브리코소프 1957, 노벨상).
- **상전이 근방**: $T_c$ 바로 아래에서 $\psi$ 가 작아 GL 전개가 정량적으로 유효 — 비열 점프·임계 거동을 기술.
- **냉원자·초유체**: 같은 GL/그로스–피타옙스키 구조가 중성 초유체의 소용돌이·경계도 기술 — 보편적 질서변수 장이론.

## 🔍 직관의 함정

**함정 1 — "질서변수 $\psi$ 는 한 입자의 파동함수다."** 아니다. $\psi$ 는 *쿠퍼 쌍 응축의 거시 파동함수* 로, $|\psi|^2$ 은 응축한 쌍의 밀도($n_s/2$)에 비례한다. $10^{20}$ 개 쌍이 공유하는 *단일* 복소장이다 — 거시 양자성의 화신.

**함정 2 — "위상 $\varphi$ 는 측정 불가능한 게이지 자유도라 무의미하다."** 위상의 *절대값* 은 게이지 의존이지만, *위상의 기울기*(게이지 불변 조합 $\nabla\varphi-\frac{q^*}{\hbar}\mathbf A$)는 물리적 초전류를 낳고, 위상 *차이* 는 조셉슨 효과로 측정된다(다음 문서). 위상은 실재한다.

**함정 3 — "위상 강성은 비유적 표현이다."** 아니다. 강성은 정량적이다 — 위상을 비틀면 에너지가 $\frac{\rho_s}{2}|\nabla\varphi|^2$ 만큼 든다. 이 $\rho_s$(초유체 강성)가 0 이 아니어야 초전류가 흐른다. 강성이 사라지면($T>T_c$) 저항이 살아난다.

**함정 4 — "1종·2종은 $\xi$ 나 $\lambda$ 하나의 크기로 정해진다."** 아니다. *둘의 비* $\kappa=\lambda/\xi$ 가 결정한다 — 경계 에너지의 부호가 $\kappa=1/\sqrt2$ 에서 바뀐다. 절대 크기가 아니라 무차원 비율의 위상학적 임계값이 핵심.

## ⚙️ 제1원리 유도

### 유도 1 — 긴즈부르크–란다우 자유에너지

$T_c$ 근방에서 질서변수 $\psi$ 가 작으므로, 자유에너지를 $|\psi|$ 의 멱으로 전개한다(란다우의 처방). $U(1)$ 대칭상 $\psi\to\psi e^{i\theta}$ 불변이려면 $|\psi|$ 의 짝수승만:

$$
F=F_n+\int d^3r\left[\alpha|\psi|^2+\frac{\beta}{2}|\psi|^4+\frac{1}{2m^*}\left|\left(-i\hbar\nabla-q^*\mathbf A\right)\psi\right|^2+\frac{B^2}{2\mu_0}\right].
$$

$q^*=2e$, $m^*=2m$(쿠퍼 쌍). $\beta>0$(안정), $\alpha=\alpha_0(T-T_c)$ — $T<T_c$ 면 $\alpha<0$ 이라 $\psi=0$ 이 불안정. 균일계 최소화 $\partial F/\partial|\psi|^2=0$:

$$
\alpha+\beta|\psi|^2=0\;\Rightarrow\;|\psi_0|^2=-\frac{\alpha}{\beta}=\frac{\alpha_0(T_c-T)}{\beta}.
$$

$$
\boxed{\;|\psi_0|\propto\sqrt{T_c-T}\;}\qquad\square
$$

2차 상전이의 질서변수가 $T_c$ 에서 연속적으로 켜진다 — BCS 의 $\Delta(T)\propto\sqrt{T_c-T}$ 와 일치(고르코프가 BCS→GL 을 미시적으로 유도).

### 유도 2 — 위상 강성과 초전류

$\psi=|\psi|e^{i\varphi}$ 를 운동 항에 넣자. $|\psi|$ 가 거의 균일하면

$$
\frac{1}{2m^*}\left|(-i\hbar\nabla-q^*\mathbf A)\psi\right|^2=\frac{\hbar^2}{2m^*}(\nabla|\psi|)^2+\frac{|\psi|^2}{2m^*}\left(\hbar\nabla\varphi-q^*\mathbf A\right)^2.
$$

둘째 항이 **위상 강성** 항이다 — 위상을 비틀거나($\nabla\varphi\ne0$) 게이지장을 걸면 에너지가 든다. 자유에너지를 $\mathbf A$ 로 변분($\delta F/\delta\mathbf A$)하면 **초전류**:

$$
\boxed{\;\mathbf j_s=\frac{q^*|\psi|^2}{m^*}\left(\hbar\nabla\varphi-q^*\mathbf A\right)\;}\qquad\square
$$

게이지 불변 조합 $\hbar\nabla\varphi-q^*\mathbf A$ 가 흐름을 정한다. 위상이 균일($\nabla\varphi=0$)이면 $\mathbf j_s=-\frac{q^{*2}|\psi|^2}{m^*}\mathbf A$ — 이것이 **런던 방정식** 의 미시적 유도다! 회전을 취하면

$$
\nabla\times\mathbf j_s=-\frac{q^{*2}|\psi|^2}{m^*}\mathbf B=-\frac{n_s e^2}{m}\mathbf B,
$$

($n_s=2|\psi|^2$, $q^*=2e$, $m^*=2m$ 대입 시 정확히 런던 형태). 런던이 *가정* 한 제2 방정식이 GL 위상 강성에서 *유도* 됐다. 위상 강성 = 마이스너의 기원. $\square$

### 유도 3 — 두 길이: 결맞음 길이 $\xi$ 와 침투 깊이 $\lambda$

**결맞음 길이**: $\mathbf A=0$, 위상 균일에서 GL 방정식 $\alpha\psi+\beta|\psi|^2\psi-\frac{\hbar^2}{2m^*}\nabla^2\psi=0$. $\psi=\psi_0+\delta\psi$ 로 선형화하면 회복 길이

$$
\boxed{\;\xi=\sqrt{\frac{\hbar^2}{2m^*|\alpha|}}\;}\qquad\square
$$

$\psi$ 가 교란(경계·소용돌이 코어)에서 $\xi$ 규모로 회복한다. **침투 깊이**: 위상 강성 항에서 $\lambda^2=\frac{m^*}{\mu_0 q^{*2}|\psi_0|^2}$, 즉

$$
\boxed{\;\lambda=\sqrt{\frac{m^*}{\mu_0 q^{*2}|\psi_0|^2}}\;}\qquad\square
$$

$|\psi_0|^2\propto(T_c-T)$ 이므로 $\xi,\lambda\propto(T_c-T)^{-1/2}$ — 둘 다 $T_c$ 에서 발산하나 *비는 일정*.

### 유도 4 — GL 매개변수 $\kappa$ 와 1·2종

무차원 비

$$
\boxed{\;\kappa=\frac{\lambda}{\xi}\;}
$$

는 온도 무관(둘 다 $(T_c-T)^{-1/2}$). 초전도/정상 경계의 표면 에너지를 계산하면, $\psi$ 회복으로 응축 에너지를 *잃는* 영역($\sim\xi$)과 자기장 배제로 *버는* 영역($\sim\lambda$)이 경쟁한다. 표면 에너지가

$$
\sigma\propto(\xi-\lambda)\propto\left(1-\kappa\right)\quad(\text{대략}),\qquad \text{정확히 }\sigma=0\text{ at }\kappa=\frac{1}{\sqrt2}.
$$

- $\kappa<1/\sqrt2$ (**1종**): $\sigma>0$ — 경계 만들기 비싸므로 자속이 *전부* 배제되다 $B_c$ 에서 한꺼번에 정상화.
- $\kappa>1/\sqrt2$ (**2종**): $\sigma<0$ — 경계 만들기가 *이득* 이라, 자속이 양자화 자속선($\Phi_0=h/2e$)으로 *최대한 잘게* 쪼개져 침투. $B_{c1}$ 부터 혼합상태.

$\kappa=1/\sqrt2$ 가 *위상학적 임계값* — 경계 에너지 부호 전환점. $\square$

### 실험 1 — GL 자유에너지 최소화와 $|\psi(T)|$

```python
import numpy as np

# GL 자유에너지 밀도 f(|ψ|²) = α|ψ|² + (β/2)|ψ|⁴ 의 최소가 |ψ0|²=-α/β
alpha0 = 1.0     # α = α0 (T - Tc)
beta   = 1.0
Tc     = 1.0

T = np.linspace(0.0, 1.5, 16)
psi2 = np.where(T < Tc, alpha0*(Tc - T)/beta, 0.0)   # T>Tc 면 ψ=0

print("T/Tc   |ψ0|²(=-α/β)   |ψ0| ∝ √(Tc-T)")
for t, p in zip(T, psi2):
    print(f"{t:4.2f}   {p:8.4f}      {np.sqrt(p):.4f}")

# Tc 근방에서 |ψ| ∝ (Tc-T)^{1/2} (2차 상전이) 확인
mask = (T < Tc) & (T > 0.7*Tc)
slope = np.polyfit(np.log(Tc - T[mask]), np.log(np.sqrt(psi2[mask])), 1)[0]
print(f"\nlog|ψ| vs log(Tc-T) 기울기 ≈ {slope:.3f}  (이론 0.5)")
```

질서변수가 $T_c$ 에서 $\sqrt{T_c-T}$ 로 켜지는 2차 상전이 거동을 확인한다.

### 실험 2 — 두 길이와 $\kappa$, 1·2종 판정

```python
import numpy as np

# 1D GL: 경계(x=0)에서 ψ=0, 깊은 곳에서 ψ→ψ0 로 회복하는 프로파일
# 해석해 ψ(x)=ψ0 tanh(x/(√2 ξ)) 로 회복 길이 ξ 확인 + κ 로 1·2종 판정
hbar = 1.0; mstar = 1.0; mu0 = 1.0; qstar = 1.0

def lengths(alpha_abs, psi0_2):
    xi  = np.sqrt(hbar**2/(2*mstar*alpha_abs))
    lam = np.sqrt(mstar/(mu0*qstar**2*psi0_2))
    return xi, lam

for (a, p2) in [(1.0, 4.0), (1.0, 0.25), (1.0, 1.0)]:
    xi, lam = lengths(a, p2)
    kappa = lam/xi
    kind = "2종 (자속선 침투)" if kappa > 1/np.sqrt(2) else "1종 (완전 배제)"
    print(f"|ψ0|²={p2:4.2f}  ξ={xi:.3f}  λ={lam:.3f}  κ={kappa:.3f}  → {kind}")

# ψ(x)=ψ0 tanh(x/(√2 ξ)) 가 GL 방정식의 경계 해임을 수치로 검증
xi = 1.0
x  = np.linspace(0, 8*xi, 800)
psi = np.tanh(x/(np.sqrt(2)*xi))            # ψ0=1 규격화
# GL: -ξ² ψ'' - ψ + ψ³ = 0 을 만족하는지 잔차
d2 = np.gradient(np.gradient(psi, x), x)
res = -xi**2*d2 - psi + psi**3
print(f"\ntanh 프로파일의 GL 방정식 잔차 max = {np.nanmax(np.abs(res[5:-5])):.2e} (≈0)")
print("→ ψ 가 경계에서 √2 ξ 규모로 회복함을 확인")
```

$\kappa=\lambda/\xi$ 로 1·2종을 판정하고, GL 경계 해 $\psi\propto\tanh(x/\sqrt2\xi)$ 가 회복 길이 $\xi$ 를 줌을 검증한다.

## 🧪 실험·관측 증거

- **아브리코소프 격자**: 2종 초전도체의 자속선 삼각 격자를 비터 무늬·중성자 산란·STM 으로 직접 관측 — GL 의 정량 예측 확인.
- **임계장의 온도 의존**: $B_{c}(T),B_{c2}(T)\propto(T_c-T)$ 가 GL 의 $|\psi_0|^2,\xi^{-2}\propto(T_c-T)$ 와 일치.
- **비열 점프**: $T_c$ 에서 비열의 유한 도약 $\Delta C\propto\alpha_0^2/\beta$ — GL 의 2차 상전이 예측.
- **고르코프 유도**: GL 이 BCS 에서 *미시적으로 유도* 됨(고르코프 1959) — $T_c$ 근방에서 $\alpha,\beta,\xi,\lambda$ 를 BCS 매개변수로 표현. GL 이 임의 가정이 아님을 입증.
- **소용돌이 코어 분광**: STM 으로 자속선 코어에서 $\psi\to0$, 코어 크기 $\sim\xi$ 확인.

## 🔬 경계

- **$T_c$ 근방 전개의 한계**: GL 은 $|\psi|$ 가 작은 $T_c$ 근방에서만 멱전개가 정당하다. 저온($T\ll T_c$)에서는 더 높은 차수가 필요하거나 미시론(BCS)으로 직접 가야 한다.
- **평균장 가정**: GL 은 평균장 — 임계 요동을 무시한다. 초전도는 $\xi$ 가 매우 커서 평균장이 잘 맞지만(긴즈부르크 기준), 고온·저차원에서는 요동이 GL 평균장을 깨뜨린다.
- **국소 vs 비국소**: GL 의 $|\nabla\psi|^2$ 항은 *국소* 근사. $\xi$ 가 평균자유행로보다 큰 깨끗한 1종에서 피파드 비국소성이 필요.
- **s-파 등방 가정**: 표준 GL 은 스칼라 $\psi$. d-파·p-파·다밴드(MgB$_2$)는 다성분 질서변수가 필요하다.

## 🧬 횡단 원리

- **자발 대칭 깨짐과 골드스톤**: $\psi=|\psi|e^{i\varphi}$ 의 위상 선택이 $U(1)$ SSB. 위상의 강성이 곧 골드스톤 모드의 강성 — 초유체·강자성과 같은 언어. (→ ch1-more-is-different/04-symmetry-breaking-order.md, → L2 phase-transitions)
- **앤더슨–힉스**: 게이지장 $\mathbf A$ 와 결합하면 골드스톤 위상이 *흡수* 되어 광자가 질량($\lambda^{-1}$)을 얻는다 — 힉스 메커니즘의 응집물질 원형. (→ standard-model-distilled L3)
- **위상 결함**: 자속선($\psi=0$ 코어 + $2\pi$ 위상 감김)은 초유체 양자 소용돌이의 전하 버전. 같은 위상수학. (→ ch3-superconductivity-superfluid/01-superfluid.md, → ch4-topological-matter)
- **초유체와 같은 뿌리**: GL = 그로스–피타옙스키의 전하 버전. (→ ch3-superconductivity-superfluid/01-superfluid.md)

## 🪜 창발

- **위상 강성 = 저항 0 의 기원**: 위 레이어에서 "거시 위상의 강성이 산일 없는 흐름을 보호한다" 는 원리는 위상 질서·위상 보호의 정신과 통한다. (→ ch4-topological-matter/05-topological-protection.md, → L6 emergence)
- **질서변수 장이론의 보편성**: GL 형식은 초전도를 넘어 액정·자성·우주론적 상전이(킵블–주렉)로 회수되는 보편 틀. (→ L5 emergent-spacetime-multiverse)
- **얽힘과 상**: 위상 강성(장거리 위상 결맞음)은 비대각 장거리 질서(ODLRO)의 한 형태로, 얽힘으로 상을 규정하는 그림과 이어진다. (→ ch5-emergent-gauge/04-entanglement-phases.md, → L5 holography)

## 📐 예측·반증

- **질서변수** $|\psi(T)|\propto\sqrt{T_c-T}$, 두 길이 $\xi,\lambda\propto(T_c-T)^{-1/2}$ — $T_c$ 근방 보편 거동.
- **GL 매개변수** $\kappa=\lambda/\xi$: $\kappa<1/\sqrt2$ 1종, $>1/\sqrt2$ 2종. 경계 에너지 부호 전환을 자속 침투 거동으로 검증.
- **상부 임계장** $B_{c2}=\frac{\Phi_0}{2\pi\xi^2}$ — $\xi$ 측정과 교차검증.
- **소용돌이 코어 크기** $\sim\xi$, 자속선당 자속 $\Phi_0=h/2e$ — STM 으로 직접 측정.

## 🤔 다음 질문

GL 은 위상 $\varphi$ 의 *강성* 이 거시 결맞음을 보호함을 보였다. 그런데 위상 $\varphi$ 자체는 게이지 의존이라 "측정 불가능" 해 보인다. 정말 위상은 실재하는가 — *직접 관측* 할 수 있는가? 두 초전도체를 얇은 절연막으로 약하게 이으면, 위상 *차이* $\varphi_1-\varphi_2$ 가 전류와 전압으로 *드러난다*. 다음 문서에서 조셉슨 효과($I=I_c\sin\varphi$, $\hbar\dot\varphi=2eV$)와 SQUID·자속 양자로, 거시 양자 위상이 측정 가능함을 증명한다.

---

🧩 **Principle** — 쿠퍼 쌍 응축의 질서변수 $\psi=|\psi|e^{i\varphi}$ 에 대한 긴즈부르크–란다우 자유에너지에서, 위상 강성 항이 초전류 $\mathbf j_s\propto(\hbar\nabla\varphi-q^*\mathbf A)$ 와 마이스너(런던 방정식)를 유도하고, 두 길이의 비 $\kappa=\lambda/\xi$ 가 1·2종을 가른다.
🔬 **Boundary** — GL 멱전개는 $T_c$ 근방·평균장·국소·s파에서만 정당하고, 저온·강요동·비국소·다성분 갭에서 미시론을 요구한다.
🪜 **Emergence** — 위상 강성이 흐름을 보호하는 구조는 위 레이어의 위상 보호·창발 원리(L6 emergence)와 ODLRO→얽힘으로 상을 규정하는 그림(L5 holography)으로 회수되며, 아브리코소프 격자·$B_{c2}=\Phi_0/2\pi\xi^2$ 로 검증된다.

## 📝 연습문제

**1. (기초)** $T_c=10$ K 인 초전도체에서 $\xi(0)=5$ nm, $\lambda(0)=200$ nm 라 하자. GL 매개변수 $\kappa$ 를 구하고 1종인지 2종인지 판정하라. 또 상부 임계장 $B_{c2}=\Phi_0/2\pi\xi^2$ 를 계산하라($\Phi_0=2.07\times10^{-15}$ Wb).

<details><summary>해설</summary>

$\kappa=\lambda/\xi=200/5=40\gg1/\sqrt2\approx0.707$ → 강한 **2종**. $B_{c2}=\frac{2.07\times10^{-15}}{2\pi(5\times10^{-9})^2}=\frac{2.07\times10^{-15}}{1.571\times10^{-16}}\approx13.2$ T. 짧은 $\xi$ 가 매우 높은 임계장을 줌 — NbTi·고온 초전도가 강한 2종이라 강자장 자석에 쓰이는 이유.
</details>

**2. (심화)** GL 방정식 $-\xi^2\psi''-\psi+\psi^3=0$($\psi$ 를 $\psi_0$ 로 규격화)의 경계 해를 구하라. 경계조건 $\psi(0)=0$, $\psi(\infty)=1$ 에서 $\psi(x)=\tanh(x/\sqrt2\xi)$ 임을 보이고, 이로부터 회복 길이가 $\xi$ 규모임을 확인하라.

<details><summary>해설</summary>

$\psi=\tanh(x/\sqrt2\xi)$ 를 대입. $\psi'=\frac{1}{\sqrt2\xi}\text{sech}^2(u)$, $\psi''=\frac{1}{2\xi^2}\cdot(-2)\text{sech}^2 u\tanh u=-\frac{1}{\xi^2}\text{sech}^2u\tanh u$ ($u=x/\sqrt2\xi$). 그러면 $-\xi^2\psi''=\text{sech}^2u\tanh u=(1-\tanh^2u)\tanh u=\tanh u-\tanh^3u=\psi-\psi^3$. 따라서 $-\xi^2\psi''-\psi+\psi^3=(\psi-\psi^3)-\psi+\psi^3=0$. $\square$ 경계조건 $\psi(0)=\tanh0=0$, $\psi(\infty)=1$ 도 만족. 특성 회복 폭이 $\sqrt2\xi$ — 즉 $\psi$ 는 표면에서 $\xi$ 규모로 회복한다. 이 길이가 소용돌이 코어 크기·경계 에너지를 정한다.
</details>

**3. (논문 비평)** 고르코프(1959)는 GL 을 BCS 에서 미시적으로 유도해 $\alpha,\beta,\xi,\lambda$ 를 BCS 매개변수로 표현했다. 그렇다면 "GL 은 BCS 에 종속된 근사일 뿐, 독립적 가치가 없는가?" 라는 주장을 비판적으로 평가하라.

<details><summary>해설</summary>

부분적으로만 옳다. (1) **종속성**: 고르코프 유도는 GL 이 $T_c$ 근방에서 BCS 의 *유효이론* 임을 보였다 — 계수들이 미시적 의미를 가지므로 GL 은 "임의 가정" 이 아니다. (2) **그러나 독립적 가치**: GL 은 BCS *보다 일반적* 이다. ㄱ) 질서변수 $\psi$ 의 *대칭성* 만 알면 메커니즘을 몰라도 적용된다 — 고온·중유체 등 BCS 가 안 통하는 계에도 GL 형식은 산다(란다우 보편성). ㄴ) 공간 비균질·소용돌이·경계처럼 미시 BCS 로 풀기 힘든 문제를 GL 이 우아하게 푼다(아브리코소프 격자는 GL 의 승리). ㄷ) GL 은 *유효장론* 의 원형으로, "낮은 에너지에서는 질서변수의 대칭·차원만 중요" 라는 깊은 원리(보편성류)를 담는다. 따라서 비판: "GL=BCS 의 근사" 는 *미시적 정당화* 의 측면만 본 것이고, *유효이론으로서의 보편성·예측력* 을 간과한다. 진짜 교훈은 미시론과 유효론이 *상보적* 이라는 것 — BCS 가 계수를 주고, GL 이 거시 현상을 조직한다.
</details>

---

<div align="center">

[◀ 이전: BCS 이론 — 쿠퍼 쌍의 창발](03-bcs-theory.md)  ·  [📚 README](../README.md)  ·  [다음: 조셉슨 효과 — 양자 위상의 관측 ▶](05-josephson.md)

</div>
