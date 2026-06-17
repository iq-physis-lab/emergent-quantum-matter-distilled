# 조셉슨 효과 — 양자 위상의 관측

> *두 초전도체를 얇은 절벽으로 약하게 이으면 위상 차 $\varphi$ 가 전류로($I=I_c\sin\varphi$), 전압으로($\hbar\dot\varphi=2eV$) 드러난다 — 거시 양자 위상이 *측정 가능한 물리량* 임을, 그리고 자속 양자 $\Phi_0=h/2e$ 가 자연의 척도임을 증명한다.*

## 🎯 핵심 질문

- 게이지 의존이라 "측정 불가능" 해 보이는 거시 위상 $\varphi$ 를 — 어떻게 *직접 관측* 하는가? 두 초전도체의 위상 차가 전류·전압에 드러나는 메커니즘은?
- DC 조셉슨 $I=I_c\sin\varphi$(전압 없이 흐르는 초전류)과 AC 조셉슨 $\hbar\dot\varphi=2eV$(전압이 위상을 *감는다*)은 어떤 결합 해밀토니안에서 동시에 나오는가?
- SQUID 가 어떻게 자속을 $\Phi_0=h/2e$ 단위로 *간섭계처럼* 재고, 그것이 왜 양자 전압 표준·세계 최고 자기장 측정기를 가능케 하는가?

## 🌍 어디서 나타나나

- **조셉슨 접합**: 두 초전도체(예: Nb) 사이에 수 nm 절연막(또는 약한 금속) — 거시 양자 위상 차가 전류로 드러나는 가장 기본 소자.
- **SQUID**(초전도 양자 간섭 소자): 조셉슨 접합 2개를 고리에 넣어, 고리를 지나는 자속을 $\Phi_0$ 분해능으로 측정 — 뇌자도(MEG)·지질 탐사·세계 최고감도 자력계.
- **양자 전압 표준**: AC 조셉슨 $V=\frac{h}{2e}f$ 로, 마이크로파 진동수 $f$ 만 알면 전압을 *기본상수로* 정의. 1990년 이래 국제 전압 표준의 기반.
- **초전도 양자비트(트랜스몬)**: 조셉슨 접합의 비선형 인덕턴스가 인공원자의 비조화 준위를 만든다 — 초전도 양자컴퓨터의 핵심 소자.
- **샤피로 계단**: 마이크로파를 쪼인 접합의 I–V 곡선에 $V=n\frac{h}{2e}f$ 의 양자화 전압 계단 — AC 조셉슨의 직접 증거이자 표준의 토대.

## 🔍 직관의 함정

**함정 1 — "절연막을 사이에 두면 초전류가 못 흐른다."** 고전적으론 맞지만, 거시 파동함수가 *터널링* 으로 약하게 결합한다. 단일 전자 터널링이 아니라 *쿠퍼 쌍 전체* 가 결맞음을 유지한 채 건너간다 — 위상 차가 흐름을 정하는 거시 양자 터널링.

**함정 2 — "위상은 게이지 자유도라 물리적이지 않다."** 절대 위상은 그렇지만, 두 초전도체의 위상 *차* 는 게이지 불변(정확히는 $\varphi=\varphi_2-\varphi_1-\frac{2e}{\hbar}\int\mathbf A\cdot d\boldsymbol\ell$)이고 *측정된다*. 조셉슨 효과가 바로 위상이 실재함을 증명하는 실험이다.

**함정 3 — "전압을 걸면 그냥 일정한 전류가 흐른다."** AC 조셉슨에서 *일정* 전압은 위상을 *일정 속도로 감아*($\dot\varphi=2eV/\hbar$) 진동수 $f=2eV/h$ 의 *교류* 초전류를 만든다. DC 전압이 AC 전류를 낳는다 — 직관에 반하는 양자 효과.

**함정 4 — "자속 양자 $h/2e$ 의 $2e$ 는 우연이다."** 아니다. $2e$ 는 응축하는 객체가 *전자 쌍* 임을 직접 가리킨다. SQUID 간섭 주기가 $\Phi_0=h/2e$ 인 것이 쿠퍼 쌍의 거시적 증거.

## ⚙️ 제1원리 유도

### 유도 1 — 조셉슨 결합 방정식 (파인만 2준위 모형)

두 초전도체를 거시 파동함수 $\psi_1=\sqrt{n_1}e^{i\varphi_1}$, $\psi_2=\sqrt{n_2}e^{i\varphi_2}$ 로 보고, 약한 터널 결합 $K$ 의 2준위 슈뢰딩거 방정식을 쓴다($eV$ 만큼의 전위차):

$$
i\hbar\dot\psi_1=\mu_1\psi_1+K\psi_2,\qquad i\hbar\dot\psi_2=\mu_2\psi_2+K\psi_1,
$$

$\mu_2-\mu_1=2eV$(쿠퍼 쌍 전하 $2e$ 의 전위차 에너지). $\psi_j=\sqrt{n_j}e^{i\varphi_j}$ 를 넣고 실수·허수부 분리, $\varphi\equiv\varphi_2-\varphi_1$ 로 놓으면

$$
\dot n_1=\frac{2K}{\hbar}\sqrt{n_1 n_2}\sin\varphi=-\dot n_2,\qquad
\dot\varphi=\dot\varphi_2-\dot\varphi_1=\frac{\mu_1-\mu_2}{\hbar}=-\frac{2eV}{\hbar}.
$$

전류 $I\propto\dot n_2$ 이므로 **DC 조셉슨 관계**:

$$
\boxed{\;I=I_c\sin\varphi\;}\qquad\square
$$

(여기 $I_c=\frac{2K\sqrt{n_1 n_2}}{\hbar}\times(\text{전하})$, 임계전류). 전압 없이($V=0$) 위상 차 $\varphi$ 만으로 초전류가 흐른다 — $\varphi$ 가 곧 전류로 *드러난다*.

### 유도 2 — AC 조셉슨 관계

위 둘째 식이 **AC 조셉슨 관계**다(부호 관례에 따라):

$$
\boxed{\;\hbar\dot\varphi=2eV\;}\qquad\square
$$

*일정 전압* $V$ 에서 $\varphi(t)=\varphi_0+\frac{2eV}{\hbar}t$ — 위상이 선형으로 감긴다. 이를 DC 관계에 넣으면

$$
I(t)=I_c\sin\!\left(\varphi_0+\frac{2eV}{\hbar}t\right),
$$

진동수 $f=\frac{2eV}{h}$ 의 *교류* 초전류! DC 전압이 AC 전류를 낳는 것이다. 비율

$$
\frac{f}{V}=\frac{2e}{h}=483.6\ \text{THz/V}\quad(\text{조셉슨 상수 }K_J),
$$

는 *순수 기본상수* — 이것이 양자 전압 표준의 근거다. 역으로, 진동수 $f$ 의 마이크로파를 쪼이면 $V=n\frac{h}{2e}f$ 의 **샤피로 계단** 이 I–V 곡선에 나타난다.

### 유도 3 — 자속 양자와 SQUID 간섭

게이지 불변 위상 차는 벡터퍼텐셜을 포함한다:

$$
\gamma=\varphi_2-\varphi_1-\frac{2e}{\hbar}\int_1^2\mathbf A\cdot d\boldsymbol\ell.
$$

DC SQUID(고리에 접합 2개, a·b)에서 두 접합의 위상 차 합을 고리 한 바퀴로 계산하면, 고리 내부를 *완전히 차폐* 한 초전도체 안에서 $\mathbf j_s=0$ 경로를 따라

$$
\gamma_b-\gamma_a=\frac{2e}{\hbar}\oint\mathbf A\cdot d\boldsymbol\ell=\frac{2e}{\hbar}\Phi=2\pi\frac{\Phi}{\Phi_0},
$$

여기서

$$
\boxed{\;\Phi_0=\frac{h}{2e}=2.07\times10^{-15}\ \text{Wb}\;}\qquad\square
$$

총 초전류는 두 접합 기여의 합으로, 간섭 무늬

$$
I_{\max}(\Phi)=2I_c\left|\cos\!\frac{\pi\Phi}{\Phi_0}\right|.
$$

자속 $\Phi$ 가 $\Phi_0$ 만큼 변할 때마다 임계전류가 *한 주기* 진동한다 — 광학 이중슬릿 간섭의 자기적 판본. 이 $\Phi_0$ 분해능이 SQUID 를 세계 최고감도 자력계로 만든다. 응축체의 위상이 *간섭한다* 는 것이, 위상이 실재함을 가장 직접적으로 증명한다. $\square$

### 실험 1 — DC/AC 조셉슨과 샤피로 계단

```python
import numpy as np
from scipy.integrate import odeint

# RCSJ(저항·용량 션트 접합) 모형으로 I-V 곡선과 샤피로 계단을 시뮬레이션
# C φ'' + (1/R)φ' + Ic sinφ = I(t),  V = (ħ/2e) φ'  (자연단위 ħ=2e=1)
Ic = 1.0
R  = 1.0
C  = 0.1

def deriv(y, t, Idc, Iac, wrf):
    phi, phidot = y
    I = Idc + Iac*np.cos(wrf*t)
    phiddot = (I - phidot/R - Ic*np.sin(phi)) / C
    return [phidot, phiddot]

def mean_voltage(Idc, Iac=0.0, wrf=0.0, t_max=400.0):
    t = np.linspace(0, t_max, 40000)
    sol = odeint(deriv, [0.0, 0.0], t, args=(Idc, Iac, wrf))
    phidot = sol[:, 1]
    half = len(t)//2
    return np.mean(phidot[half:])   # 시간평균 전압 ⟨V⟩=⟨φ'⟩

# (1) DC: I<Ic 면 V=0 (초전류), I>Ic 면 유한 전압
print("DC 조셉슨 — I<Ic 에서 V=0, I>Ic 에서 전압 발생")
for Idc in [0.5, 0.9, 1.0, 1.5, 2.0]:
    V = mean_voltage(Idc)
    print(f"  I/Ic={Idc:.1f}   ⟨V⟩={V:+.3f}")

# (2) 샤피로 계단: 마이크로파(wrf) 인가 시 ⟨V⟩ 가 n·wrf 에 고정(양자화 계단)
print("\n샤피로 계단 — ⟨V⟩ 가 wrf 의 정수배 근방에 평탄역(계단) 형성")
wrf = 2.0
for Idc in np.linspace(0.0, 3.0, 13):
    V = mean_voltage(Idc, Iac=1.2, wrf=wrf)
    n = V/wrf
    print(f"  Idc={Idc:.2f}   ⟨V⟩={V:+.3f}   V/wrf={n:+.2f}")
# ⟨V⟩/wrf 가 0,1,2,... 근방에 머무는 평탄역 = V=n(h/2e)f 의 양자화
```

DC 조셉슨(임계전류 아래 V=0)과 AC 조셉슨이 만든 샤피로 전압 계단을 수치로 재현한다.

### 실험 2 — SQUID 자속 간섭

```python
import numpy as np

# DC SQUID 의 최대 초전류 I_max(Φ) = 2 Ic |cos(πΦ/Φ0)| — 자속 간섭
Ic = 1.0
Phi = np.linspace(-3, 3, 601)          # Φ/Φ0 단위
Imax = 2*Ic*np.abs(np.cos(np.pi*Phi))

# 간섭 주기가 정확히 Φ0(=1 단위)임을 확인: 극대 위치
peaks = Phi[(np.r_[Imax[1:],0] < Imax) & (np.r_[0,Imax[:-1]] < Imax)]
print("I_max 극대(=완전 보강간섭) 위치 Φ/Φ0:", np.round(peaks, 2))
print("→ 인접 극대 간격 =", round(np.diff(peaks).mean(), 3), "Φ0  (주기 = 자속 양자)")

Phi0 = 6.62607015e-34 / (2*1.602176634e-19)
print(f"\nΦ0 = h/2e = {Phi0:.3e} Wb")
print("자속이 Φ0 만큼 변할 때마다 임계전류가 한 주기 → 위상이 간섭한다(실재 증거)")
```

자속이 $\Phi_0$ 변할 때마다 임계전류가 한 주기 진동함을 확인 — 위상 간섭의 직접 시연.

## 🧪 실험·관측 증거

- **DC 조셉슨**(Anderson–Rowell 1963): 전압 없이 흐르는 초전류와 그 임계전류의 자기장 의존(프라운호퍼 무늬) 관측 — 조셉슨(1962, 노벨상)의 예측 확증.
- **샤피로 계단**(1963): 마이크로파 인가 접합의 I–V 에서 $V=n\frac{h}{2e}f$ 양자화 전압 계단 — AC 조셉슨의 직접 증거.
- **양자 전압 표준**: 수천 개 접합 어레이로 $V=n\frac{h}{2e}f$ 를 1V 규모로 합성 — $10^{-10}$ 정밀도의 국제 전압 표준(SI 재정의의 기반).
- **SQUID 자력계**: $\sim10^{-15}$ T 분해능 — 뇌·심장의 자기장(MEG/MCG) 측정, 기초 자속 양자 $\Phi_0$ 직접 확인.
- **거시 양자 터널링·트랜스몬**: 접합의 위상이 *양자화된 준위* 를 가짐을 관측(레겟) — 거시 자유도의 양자성 입증, 초전도 큐비트로 발전.

## 🔬 경계

- **터널 결합 약결합 가정**: $I=I_c\sin\varphi$ 의 순수 사인 형태는 약결합·s파에서 성립. 강한 결합·점접촉·d파에서는 고차 고조파($\sin2\varphi$ 등)와 비정상 전류–위상 관계가 나타난다.
- **양자 요동과 위상 확산**: 작은 접합(큰 충전 에너지 $E_C=\frac{(2e)^2}{2C}$)에서는 위상과 전하가 켤레라 위상이 *요동* 한다 — 쿨롱 봉쇄·위상 확산이 단순 조셉슨 그림을 수정.
- **유한 온도·잡음**: 열잡음이 임계전류 아래에서도 위상 미끄러짐을 일으켜 I–V 를 둥글게 만든다(앰비고카르–할페린).
- **위상 일관성의 한계**: 매우 긴 접합·비균질 시료에서 단일 위상 차 기술이 무너지고 자속선 동역학이 지배한다.

## 🧬 횡단 원리

- **위상 = 측정 가능한 거시 자유도**: 조셉슨 효과는 GL 의 위상 $\varphi$ 가 실재함을 증명한다 — 자발 대칭 깨짐의 골드스톤 위상이 *관측* 된다. (→ ch3-superconductivity-superfluid/04-macroscopic-coherence.md, → ch1-more-is-different/04-symmetry-breaking-order.md)
- **위상–전하 켤레**: $[\hat\varphi,\hat N]=i$ — 위상과 쿠퍼 쌍 수가 정준 켤레. 이 양자 불확정성이 트랜스몬 큐비트·거시 양자 터널링의 기반. (→ quantum-mechanics-distilled L3, → quantum-information-distilled)
- **간섭의 보편성**: SQUID 자속 간섭은 아하로노프–봄 효과의 초전도 판본 — 위상이 기하·자속을 통해 관측 가능. (→ ch4-topological-matter, 베리 위상)
- **자속 양자 $\Phi_0=h/2e$**: 2종 자속선·양자홀과 같은 양자화 척도. (→ ch3-superconductivity-superfluid/02-superconductivity.md)

## 🪜 창발

- **거시 양자성의 관측 가능성**: 조셉슨은 "거시 자유도도 양자적이고 측정 가능" 임을 증명 — 위 레이어에서 양자–고전 경계·측정 문제·거시 얽힘으로 회수된다. (→ quantum-information-distilled, → L6 emergence)
- **양자 표준의 보편성**: $V=\frac{h}{2e}f$, $R_K=\frac{h}{e^2}$(양자홀)이 *순수 상수로* 단위를 정의 — 자연 상수가 측정 표준이 되는 것은 위상·위상수학적 보호의 거시적 발현. (→ ch4-topological-matter/01-quantum-hall.md)
- **초전도 큐비트**: 조셉슨 비선형성이 인공원자를 만들어, 위 레이어의 양자 정보 처리·오류정정의 물리적 플랫폼이 된다. (→ quantum-information-distilled L3)

## 📐 예측·반증

- **DC 조셉슨**: $I=I_c\sin\varphi$ — 전압 없이 흐르는 임계전류, 자기장 의존 프라운호퍼 무늬 $I_c(B)\propto|\text{sinc}(\pi\Phi/\Phi_0)|$.
- **AC 조셉슨**: $f/V=2e/h=483.6$ THz/V — 진동수–전압 비가 *순수 상수*. 측정이 벗어나면 $2e$ 짝짓기가 틀린 것(반증적).
- **샤피로 계단**: $V=n\frac{h}{2e}f$ — 양자화 전압 계단. 정밀도 $10^{-10}$.
- **SQUID 주기**: 임계전류가 $\Phi_0=h/2e$ 주기로 진동 — 주기가 $h/e$ 라면 단일 전자 응축(틀림).

## 🤔 다음 질문

조셉슨 효과는 초전도의 위상 $\varphi$ 가 *측정 가능* 함을, 그리고 자속·전압이 $h/2e$ 단위로 *정밀하게 양자화* 됨을 증명했다. 그런데 이 정밀 양자화 — 자연 상수가 측정 표준이 되는 일 — 는 초전도만의 특권일까? 자기장 속 2차원 전자계에서는 *홀 전도도* 가 $\sigma_{xy}=C\,e^2/h$ 로, 불순물·시료 모양과 *무관* 하게 정수로 양자화된다. 그 정밀함의 기원은 위상(topology)이다. 다음 챕터에서 양자홀 효과와 천 수로, 대칭이 아니라 *위상* 이 물질을 분류하는 새 질서를 연다.

---

🧩 **Principle** — 두 초전도체의 약한 터널 결합에서 거시 위상 차가 DC($I=I_c\sin\varphi$)·AC($\hbar\dot\varphi=2eV$)로 드러나고, SQUID 간섭이 자속을 $\Phi_0=h/2e$ 주기로 재어 위상이 측정 가능함을 증명한다.
🔬 **Boundary** — 순수 사인 전류–위상 관계는 약결합·s파에서만 성립하고, 강결합·작은 접합의 위상–전하 요동·열잡음·자속선 동역학에서 수정된다.
🪜 **Emergence** — 거시 양자 위상의 관측 가능성과 $V=\frac{h}{2e}f$ 의 상수-기반 표준은 위 레이어에서 양자–고전 경계·양자 정보 플랫폼(L3 quantum-information)으로, 자연 상수가 측정 표준이 되는 정밀성은 위상 양자화(L6 emergence)로 회수되며, 샤피로 계단·SQUID 주기로 검증된다.

## 📝 연습문제

**1. (기초)** AC 조셉슨 관계 $f=\frac{2e}{h}V$ 로, 진동수 $f=483.6$ GHz 의 마이크로파에 대응하는 샤피로 첫 계단 전압 $V$ 를 구하라. ($2e/h=483.6$ THz/V)

<details><summary>해설</summary>

$V=\frac{h}{2e}f=\frac{f}{2e/h}=\frac{483.6\times10^{9}\ \text{Hz}}{483.6\times10^{12}\ \text{Hz/V}}=10^{-3}$ V $=1$ mV. 즉 483.6 GHz ↔ 1 mV. $n$번째 계단은 $n$ mV. 진동수만으로 전압이 *정확히* 정의됨 — 이것이 양자 전압 표준의 원리다.
</details>

**2. (심화)** DC SQUID 의 두 접합이 각각 $I=I_c\sin\gamma_a$, $I=I_c\sin\gamma_b$ 를 따르고, 고리를 한 바퀴 돌 때 $\gamma_b-\gamma_a=2\pi\Phi/\Phi_0$ 라 하자. 총 초전류의 *최대값* 이 $I_{\max}(\Phi)=2I_c|\cos(\pi\Phi/\Phi_0)|$ 임을 유도하라.

<details><summary>해설</summary>

총 전류 $I=I_c\sin\gamma_a+I_c\sin\gamma_b$. $\gamma_b=\gamma_a+2\pi\Phi/\Phi_0\equiv\gamma_a+\delta$ 로 놓고 합차공식:

$$I=I_c[\sin\gamma_a+\sin(\gamma_a+\delta)]=2I_c\cos\frac{\delta}{2}\sin\!\left(\gamma_a+\frac{\delta}{2}\right).$$

외부에서 $\gamma_a$ 는 자유(전체 위상 오프셋)로 조절되므로, $\sin(\cdots)$ 의 최대 1 을 취하면

$$I_{\max}=2I_c\left|\cos\frac{\delta}{2}\right|=2I_c\left|\cos\frac{\pi\Phi}{\Phi_0}\right|.\qquad\square$$

자속 $\Phi$ 가 $\Phi_0$ 변하면 한 주기 — 이중슬릿 간섭과 정확히 같은 구조. 주기가 $\Phi_0=h/2e$ 인 것이 쿠퍼 쌍($2e$)의 증거다.
</details>

**3. (논문 비평)** 양자 전압 표준은 $V=n\frac{h}{2e}f$ 로 전압을 *기본상수* 로 정의한다. 이 표준이 "정확하다" 는 주장의 근거는 무엇이며, 만약 조셉슨 관계가 $2e$ 가 아니라 약간 다른 유효전하 $q^*$ 를 가진다면 표준이 무너지는가? 정밀 측정이 *기초물리* 를 어떻게 검증하는지 비판적으로 논하라.

<details><summary>해설</summary>

근거: AC 조셉슨 $f=\frac{q^*}{h}V$ 는 *위상 진화* 라는 매우 일반적 원리(에너지–위상 켤레)에서 나오므로, 접합의 미시 세부(재료·온도·기하)에 *무관* 하다 — 이 보편성이 표준의 정밀성($10^{-10}$ 이상)을 보장한다. 만약 유효전하가 $2e$ 가 아니면 *모든* 조셉슨 측정이 그 값으로 일관되게 이동할 것이고, 양자홀의 $R_K=h/e^2$ 와의 *교차 비교*(양자 계측 삼각형: 조셉슨 $K_J=2e/h$, 양자홀 $R_K=h/e^2$, 단전자 펌프 $e$)에서 불일치가 드러난다. 실제로 이 삼각형의 무모순성이 $10^{-7}$ 수준에서 검증되어 $K_J R_K=4/e\cdot$… 관계의 일관성을 확인했다. 비판적 관점: 표준의 "정확함" 은 *절대* 정확이 아니라 *재현성·보편성* 이다 — 자연 상수가 정의값이 되면(2019 SI 재정의) $h,e$ 가 고정되어 표준은 정의상 정확해지나, 그 *물리적 일관성* 은 여전히 실험적 검증 대상이다. 따라서 조셉슨·양자홀 정밀 측정은 단순 계측을 넘어, $h,e,\Phi_0,R_K$ 의 *상호 무모순성* 을 통해 양자전기역학과 응집물질 위상 양자화를 동시에 검증하는 기초물리 실험이다.
</details>

---

<div align="center">

[◀ 이전: 거시적 양자 결맞음 — 질서변수·위상 강성](04-macroscopic-coherence.md)  ·  [📚 README](../README.md)  ·  [다음: 양자홀 효과 ▶](../ch4-topological-matter/01-quantum-hall.md)

</div>
