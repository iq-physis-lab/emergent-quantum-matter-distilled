# 초유체 — 거시 양자성

> *수백억 개의 보손이 *하나의 파동함수* $\psi=\sqrt{n}\,e^{i\varphi}$ 로 응축하면, 양자역학이 손가락 굵기의 규모로 올라온다 — 점성 없는 흐름과 양자화된 소용돌이는 그 거시 위상 $\varphi$ 의 직접적 귀결이다.*

## 🎯 핵심 질문

- 액체 헬륨이 2.17 K 아래에서 *점성 없이* 흐르고, 가는 모세관을 저항 없이 통과하는 초유체가 되는 일은 — 어떤 다체 원리에서 나오는가? "점성 0" 은 외울 게 아니라 **유도** 해야 한다.
- 보스–아인슈타인 응축(BEC)이 만든 **거시적 파동함수** $\psi=\sqrt{n}\,e^{i\varphi}$ 가 왜 *하나의 양자상태가 거시 규모로 올라온* 것인지, 그리고 그 위상 $\varphi$ 가 어떻게 *흐름* 을 규정하는지?
- 왜 초유체의 소용돌이는 연속적이지 않고 $\oint \mathbf{v}\cdot d\boldsymbol{\ell}=n\,h/m$ 으로 **양자화** 되는가? 왜 느린 흐름은 마찰을 못 일으키는가(란다우 임계속도)?

## 🌍 어디서 나타나나

- **He-4 초유체**: 액체 $^4$He 를 람다점 $T_\lambda \approx 2.17$ K 아래로 식히면 He-II 상이 된다. 비커 벽을 타고 **롤린 필름** 으로 기어오르고, 분수 직경의 모세관을 저항 없이 빠져나가며(superleak), 가열하면 **분수 효과(fountain effect)** 로 솟구친다.
- **회전 양동이의 소용돌이 격자**: 초유체를 담은 용기를 회전시키면 매끈하게 같이 돌지 않고, **양자화된 소용돌이** 의 삼각 격자(아브리코소프-차일 격자)가 생긴다 — 각 소용돌이가 정확히 $h/m$ 의 순환을 나른다.
- **He-3 초유체**(1.7 mK 이하): 페르미온 $^3$He 가 *쌍* 을 이뤄 BCS-형 초유체가 된다 — 초전도와의 직접 다리. p-파 스핀-삼중항 응축으로 A·B 상이라는 풍부한 질서변수 구조를 보인다.
- **냉원자 BEC**: $^{87}$Rb·$^{23}$Na 기체를 nK 로 식혀 만든 순수 BEC. 간섭 무늬·양자 소용돌이를 *직접 촬영* 할 수 있어, 거시 양자성의 교과서적 실험실이 되었다.
- **중성자별 내부**: 중성자가 짝을 이뤄 초유체가 되고, 회전 글리치(pulsar glitch)가 소용돌이 격자의 풀림으로 설명된다.

## 🔍 직관의 함정

**함정 1 — "초유체는 점성이 아주 작은 보통 액체다."** 아니다. 점성이 *작은* 게 아니라, 들뜸을 만들 *경로 자체가 닫혀* 있다(란다우 기준). 보통 액체는 아무리 느려도 마찰을 주지만, 초유체는 임계속도 아래에서는 에너지·운동량 보존이 산란을 *금지* 한다. 정성이 아니라 정량적 문턱이 있다.

**함정 2 — "거시적 파동함수는 비유다."** 아니다. $\psi=\sqrt{n}\,e^{i\varphi}$ 의 위상 $\varphi$ 는 *측정 가능* 하다. 두 BEC 을 겹치면 $\varphi_1-\varphi_2$ 에 의한 실제 간섭 무늬가 카메라에 찍힌다. 소용돌이의 양자화 순환도 $\varphi$ 가 진짜 물리량임을 증명한다.

**함정 3 — "BEC 만 되면 곧바로 초유체다."** 거의 맞지만 미묘하다. 이상기체 BEC 은 사실 임계속도가 0 이라 *진짜 초유체가 아니다*. **상호작용** 이 분산을 선형(포논)으로 만들어줘야 란다우 임계속도가 유한해진다 — 초유성은 응축 + 상호작용의 합작이다.

**함정 4 — "소용돌이는 물이 빙빙 도는 것처럼 연속적으로 강해질 수 있다."** 아니다. $\varphi$ 가 단일값이어야 한다는 위상학적 조건이 순환을 $h/m$ 의 정수배로 **양자화** 한다. 회전을 키우면 소용돌이의 *개수* 가 늘 뿐, 각 소용돌이의 세기는 고정이다.

## ⚙️ 제1원리 유도

### 유도 1 — 거시적 파동함수와 초유체 속도장

BEC 에서는 단일 입자 바닥상태가 거시적으로 점유된다($N_0\sim N$). 이 응축체를 하나의 **질서변수**(복소장)로 기술한다:

$$
\psi(\mathbf{r},t)=\sqrt{n(\mathbf{r},t)}\;e^{i\varphi(\mathbf{r},t)},
$$

여기서 $n=|\psi|^2$ 은 응축 밀도, $\varphi$ 는 거시 위상이다. 약하게 상호작용하는 보손은 **그로스–피타옙스키 방정식**(평균장)을 따른다:

$$
i\hbar\,\partial_t \psi = \left(-\frac{\hbar^2}{2m}\nabla^2 + V_{\text{ext}} + g|\psi|^2\right)\psi,\qquad g=\frac{4\pi\hbar^2 a_s}{m}.
$$

$\psi=\sqrt{n}\,e^{i\varphi}$ 를 대입하고 실수·허수부로 분리한다(마델룽 변환). 확률 흐름 $\mathbf{j}=\frac{\hbar}{2mi}(\psi^*\nabla\psi-\psi\nabla\psi^*)=n\,\frac{\hbar}{m}\nabla\varphi$ 에서 흐름 $\mathbf{j}=n\mathbf{v}_s$ 로 정의하면 **초유체 속도장** 이 나온다:

$$
\boxed{\;\mathbf{v}_s=\frac{\hbar}{m}\nabla\varphi\;}
$$

흐름이 위상의 기울기다. 속도장이 위상의 그래디언트이므로 **무회전**(irrotational)이다:

$$
\nabla\times\mathbf{v}_s=\frac{\hbar}{m}\nabla\times\nabla\varphi=0\quad(\text{단일값 } \varphi \text{ 영역에서}).\qquad\square
$$

즉 초유체는 *위상에 의해 강제된* 흐름이다. 이게 초유체의 모든 거시 거동의 씨앗이다.

### 유도 2 — 순환의 양자화와 양자 소용돌이

$\psi$ 가 단일값이려면 닫힌 경로 $C$ 를 한 바퀴 돌 때 위상이 $2\pi$ 의 정수배만큼 변해야 한다:

$$
\oint_C \nabla\varphi\cdot d\boldsymbol{\ell}=2\pi n,\qquad n\in\mathbb{Z}.
$$

이를 속도장으로 옮기면 **순환의 양자화**:

$$
\Gamma\equiv\oint_C \mathbf{v}_s\cdot d\boldsymbol{\ell}=\frac{\hbar}{m}\oint_C \nabla\varphi\cdot d\boldsymbol{\ell}=\frac{\hbar}{m}\,2\pi n=n\,\frac{h}{m}.
$$

$$
\boxed{\;\oint \mathbf{v}_s\cdot d\boldsymbol{\ell}=n\,\frac{h}{m},\qquad n\in\mathbb{Z}\;}\qquad\square
$$

$^4$He 의 양자 순환은 $\kappa=h/m_4\approx 9.97\times10^{-8}\ \text{m}^2/\text{s}$ 이다. 무회전 조건과 양자화가 양립하려면 소용돌이 *심(core)* 에서 $n\to0$ 이어 $\psi$ 가 사라져야 한다 — 이게 **양자 소용돌이** 다. 단일 소용돌이 주위로 $v_s(r)=\frac{\hbar}{m}\frac{1}{r}$ (n=1), 코어 반지름은 응결 길이 $\xi$ 규모다. 회전하는 용기는 강체 회전 $\mathbf{v}=\boldsymbol{\Omega}\times\mathbf{r}$ 을 흉내내기 위해 소용돌이 밀도 $n_v=\frac{2\Omega}{\kappa}$ 의 격자를 형성한다($\oint\mathbf{v}\cdot d\boldsymbol\ell=2\Omega A=n_v A\kappa$).

### 유도 3 — 란다우 임계속도

왜 느린 초유체는 마찰을 못 받는가? 속도 $\mathbf{V}$ 로 움직이는 초유체가 벽과 마찰하려면 들뜸(분산 $\varepsilon(\mathbf{p})$) 하나를 만들어야 한다. 정지계로 갈릴레이 변환하면, 운동량 $\mathbf{p}$ 의 들뜸 한 개를 만들 때 에너지 변화는

$$
\Delta E=\varepsilon(\mathbf{p})+\mathbf{p}\cdot\mathbf{V}.
$$

$\Delta E<0$ 이라야 자발적 산란(마찰)이 일어난다. 최저 비용은 $\mathbf{p}\parallel(-\mathbf{V})$ 일 때 $\varepsilon(p)-pV<0$, 즉 $V>\varepsilon(p)/p$. 어떤 $\mathbf{p}$ 라도 이를 만족하지 못하게 하는 문턱이 **란다우 임계속도** 다:

$$
\boxed{\;v_c=\min_{p}\frac{\varepsilon(p)}{p}\;}\qquad\square
$$

자유입자 분산 $\varepsilon=p^2/2m$ 이면 $\min(p/2m)=0$ — *임계속도가 0* 이라 진짜 초유체가 못 된다. He-4 의 실제 스펙트럼은 작은 $p$ 에서 **포논** $\varepsilon=c\,p$(선형), 큰 $p$ 에서 **롯온**(roton) 최소 $\varepsilon\approx\Delta_r+\frac{(p-p_0)^2}{2\mu}$ 을 갖는다. 이 경우 $v_c=\min(\varepsilon/p)$ 는 롯온 골에서 결정되어 $v_c\approx\Delta_r/p_0\approx 60$ m/s — 유한하다. 상호작용이 분산을 선형화해야 초유성이 산다.

### 실험 1 — 란다우 임계속도를 분산에서 구하기

```python
import numpy as np

# He-4 의 단순화된 들뜸 분산: 작은 p 에서 포논(선형), p0 근처에 롯온 골
hbar = 1.0545718e-34      # J·s
m4   = 6.6446e-27         # kg (He-4 원자 질량)
kB   = 1.380649e-23

c      = 238.0            # 포논 속도 m/s (1차 소리)
p0     = 1.9e10 * hbar    # 롯온 운동량 (k0 ≈ 1.9e10 1/m)
Delta_r= 8.6 * kB         # 롯온 갭 ≈ 8.6 K
mu     = 0.16 * m4        # 롯온 유효질량

def eps(p):
    # 포논 + 롯온 을 부드럽게 합성한 모형 분산 (정성적)
    e_ph  = c * p
    e_rot = Delta_r + (p - p0)**2 / (2*mu)
    return np.minimum(e_ph, e_rot)   # 두 가지 중 낮은 가지

p = np.linspace(1e-26, 4*p0, 200000)
ratio = eps(p) / p
vc = ratio.min()
p_at = p[np.argmin(ratio)]

print(f"란다우 임계속도 v_c = min(eps/p) ≈ {vc:.1f} m/s")
print(f"  최소를 주는 운동량 p ≈ {p_at/hbar:.2e} 1/m (롯온 근처면 정상)")
print(f"  Delta_r/p0 ≈ {Delta_r/p0:.1f} m/s  (롯온이 v_c 를 지배)")
# v_c 가 유한 → 그 속도 아래에서는 들뜸 생성이 금지(점성 0)
```

이 코드는 *왜 임계속도가 0 이 아닌지* — 롯온 골이 $\min(\varepsilon/p)$ 를 유한하게 만든다는 것을 보여준다.

### 실험 2 — 두 BEC 의 위상 간섭

```python
import numpy as np

# 거시 파동함수 ψ=√n e^{iφ} 의 위상이 측정 가능함을 간섭으로 시연
x = np.linspace(-50e-6, 50e-6, 2000)   # 50 µm 영역
d = 30e-6                               # 두 응축체 중심 간격
sigma = 8e-6

# 두 가우시안 응축체, 상대 위상 dphi 를 부여
def cloud(x0, phase, k):
    amp = np.exp(-(x-x0)**2/(2*sigma**2))
    return np.sqrt(amp) * np.exp(1j*(phase + k*x))

# 팽창 후 운동량 k ∝ 중심으로부터의 거리 (자유 팽창 흉내)
k_scale = 4e5
for dphi in [0.0, np.pi/2, np.pi]:
    psi = cloud(-d/2, 0.0, +k_scale) + cloud(+d/2, dphi, -k_scale)
    n = np.abs(psi)**2
    # 간섭 무늬의 대비(가시도)
    contrast = (n.max()-n.min())/(n.max()+n.min())
    print(f"상대위상 Δφ={dphi:5.2f}  무늬 대비={contrast:.3f}")
# 상대 위상이 무늬를 이동/변조 → φ 는 실재하는 측정 가능한 양
```

거시 위상 $\varphi$ 가 비유가 아니라 카메라에 찍히는 실재임을 보여준다.

## 🧪 실험·관측 증거

- **점성 측정**: 안드로니카쉬빌리의 회전 진자 실험은 초유체 성분이 *진자를 따라 돌지 않음* 을 보여, 정상/초유체 두 성분의 밀도비 $\rho_s/\rho$ 의 온도 의존성을 측정했다($T\to0$ 에서 $\rho_s\to\rho$).
- **양자화 순환의 직접 측정**: Vinen(1961)이 진동하는 가는 줄 주위의 순환을 측정해 $h/m_4$ 의 양자값을 확인했다.
- **롯온 분산**: 중성자 비탄성 산란이 $^4$He 의 포논–롯온 스펙트럼을 직접 측정, 란다우가 *임계속도를 설명하려고 가정한* 분산이 실재함을 입증했다.
- **소용돌이 격자 촬영**: 회전하는 BEC($^{87}$Rb, JILA·MIT)에서 양자 소용돌이의 삼각 격자가 흡수영상으로 직접 찍혔고, 소용돌이 수가 $\Omega$ 에 선형 비례함이 확인됐다.
- **He-3 초유체**(Osheroff–Richardson–Lee, 1972, 노벨상): 페르미온 $^3$He 의 쌍 응축, BCS 와 같은 메커니즘이 중성 페르미온에도 작동함을 보였다.

## 🔬 경계

- **평균장(그로스–피타옙스키)의 한계**: GP 는 약상호작용·저온의 응축체에 유효하다. 강상호작용 He-4 에서는 응축 분율이 $T\to0$ 에서도 약 8 %에 불과하다 — "거시 점유" 가 *100 % 점유* 를 뜻하지 않으며, 양자 고갈(quantum depletion)을 정량화하려면 보골류보프 이론·QMC 가 필요하다.
- **두 성분 모형의 정성성**: 정상/초유체 2-유체 모형은 현상론이다. 미시적으로 "초유체 성분" 은 별개의 입자 집단이 아니라 위상 결맞음을 가진 응축의 거시적 표현이다.
- **임계속도의 비란다우 붕괴**: 실제 He-4 의 임계속도는 종종 란다우 값(60 m/s)보다 훨씬 낮다 — 소용돌이 핵형성·재연결이 더 낮은 속도에서 산일을 일으키기 때문이다. 란다우 기준은 *상한* 일 뿐이다.
- **차원의 함정**: 2D 에서는 진짜 장거리 BEC 질서가 없고(머민–바그너), 초유성은 BKT 전이로 *위상 결함(소용돌이) 쌍의 결합/해리* 를 통해 나타난다 — 응축이 아니라 위상 강성으로 정의되는 다른 메커니즘이다.

## 🧬 횡단 원리

- **자발 대칭 깨짐(SSB)**: 초유체 상은 $U(1)$ 위상 대칭의 자발적 깨짐이다 — 바닥상태가 특정 $\varphi$ 를 고르고, 그 **골드스톤 모드** 가 바로 포논(2차 소리)이다. (→ symmetry-conservation-distilled L0, → ch1-more-is-different/04-symmetry-breaking-order.md)
- **질서변수와 위상 강성**: $\psi=|\psi|e^{i\varphi}$ 와 위상의 강성이 초전류를 낳는 구조는 초전도(긴즈부르크–란다우)와 *동일* 하다. (→ ch3-superconductivity-superfluid/04-macroscopic-coherence.md)
- **통계역학의 BEC**: 임계온도 $T_c\propto n^{2/3}\hbar^2/m k_B$ 의 유도는 statmech 의 보스 분포에서 직접 온다. (→ statistical-mechanics-distilled L2)
- **위상 결함**: 양자 소용돌이는 위상 결함의 원형이다 — 같은 위상수학이 초전도 자속선·우주끈에서 반복된다(킵블–주렉). (→ ch4-topological-matter)

## 🪜 창발

- **거시 위상 = 거시 양자 자유도**: 하나의 위상 $\varphi$ 가 $10^{22}$ 개 입자를 지휘한다는 사실은, 상위 레이어에서 "미시 자유도의 얽힘이 거시 질서를 낳는다" 는 일반 원리의 가장 깨끗한 사례다. (→ L6 emergence)
- **얽힘과 응축**: BEC 의 거시 점유는 입자 간 1체 밀도행렬의 비대각 장거리 질서(ODLRO, $\langle\psi^\dagger(\mathbf{r})\psi(\mathbf{r}')\rangle\to$ 상수)로 정의된다 — 이 양자 정보적 정의가 위상 질서·홀로그래피로 이어진다. (→ L5 holographic-principle)
- **창발 시공간 비유**: 음향 메트릭(analogue gravity) — 초유체 흐름 위의 포논이 *곡률 있는 시공간* 의 장을 흉내내, 호킹 복사의 실험실 모형이 된다. (→ L5 emergent-spacetime-multiverse)

## 📐 예측·반증

- **순환 양자**: $\kappa=h/m_4=9.97\times10^{-8}\ \text{m}^2/\text{s}$ — 측정된 순환은 이 값의 정수배여야 한다. 반증: 연속적 순환이 관측되면 거시 위상의 단일값성이 깨진 것.
- **소용돌이 밀도**: 회전수 $\Omega$ 에서 $n_v=2\Omega/\kappa$ — 소용돌이 개수가 $\Omega$ 에 선형이어야 한다.
- **란다우 임계속도**: $v_c=\min_p\varepsilon(p)/p$ — He-4 의 롯온 분산에서 약 60 m/s(상한). 측정 임계속도는 이 이하.
- **2-유체 비열·2차 소리**: 초유체 성분의 존재가 *온도파*(2차 소리)를 예측 — 보통 액체엔 없는 모드. 관측되면 확증.

## 🤔 다음 질문

초유체는 *중성* 보손의 거시 양자성이다. 그런데 금속 안의 전자는 *전하를 띤 페르미온* 이다. 같은 거시 양자성이 전하를 가지면 무슨 일이 벌어질까? 위상의 기울기가 흐름을 낳는 그 구조에 전자기장을 결합하면, 저항 0 과 자기장 배제(마이스너)가 나온다 — 바로 **초전도** 다. 다음 문서에서 런던 방정식과 침투 깊이로 초전도를 현상론적으로 세운 뒤, 그 미시 기원(BCS)으로 내려간다.

---

🧩 **Principle** — BEC 이 만든 거시 파동함수 $\psi=\sqrt n\,e^{i\varphi}$ 의 위상 $\varphi$ 가 흐름 $\mathbf v_s=\frac\hbar m\nabla\varphi$ 를 강제하고, 단일값 조건이 순환을 $n h/m$ 으로 양자화하며 란다우 기준 $v_c=\min_p\varepsilon(p)/p$ 이 점성 0 을 낳는다.
🔬 **Boundary** — 평균장(GP)은 약상호작용에 유효하고, 강상호작용 He-4 의 양자 고갈·소용돌이 핵형성·2D 의 BKT 전이에서 단순 BEC 그림이 수정된다.
🪜 **Emergence** — 하나의 위상이 거시를 지휘하는 ODLRO 구조는 위 레이어에서 얽힘이 상을 규정하는 원리(L5 holography)와 음향 호킹 복사(L5 emergent-spacetime)로 회수되며, 양자화 순환·롯온 임계속도로 검증된다.

## 📝 연습문제

**1. (기초)** 회전수 $\Omega=1\ \text{rad/s}$ 로 회전하는 He-4 초유체에서 단위면적당 양자 소용돌이 개수 $n_v$ 를 구하라. 순환 양자 $\kappa=h/m_4=9.97\times10^{-8}\ \text{m}^2/\text{s}$ 를 쓰라.

<details><summary>해설</summary>

강체 회전을 흉내내려면 임의 면적 $A$ 의 닫힌 경로에서 $\oint\mathbf v\cdot d\boldsymbol\ell=2\Omega A$ (강체 $\nabla\times\mathbf v=2\boldsymbol\Omega$). 각 소용돌이는 $\kappa$ 를 나르므로 $N$ 개면 $N\kappa=2\Omega A$. 따라서

$$n_v=\frac{N}{A}=\frac{2\Omega}{\kappa}=\frac{2\times1}{9.97\times10^{-8}}\approx 2.0\times10^{7}\ \text{개/m}^2.$$

즉 1 cm$^2$ 당 약 2000 개. 회전수에 선형 비례함이 핵심이다.
</details>

**2. (심화)** 들뜸 분산이 작은 $p$ 에서 $\varepsilon=cp$, 큰 $p$ 에서 롯온 최소 $\varepsilon=\Delta_r+\frac{(p-p_0)^2}{2\mu}$ 라 하자. 란다우 임계속도 $v_c=\min_p\varepsilon(p)/p$ 를 롯온 가지에서 해석적으로 구하고, 최소를 주는 운동량이 $p_0$ 와 어떻게 다른지 보여라.

<details><summary>해설</summary>

롯온 가지에서 $f(p)=\frac{\Delta_r+(p-p_0)^2/2\mu}{p}$. $f'(p)=0$ 조건:

$$f'(p)=\frac{(p-p_0)/\mu}{p}-\frac{\Delta_r+(p-p_0)^2/2\mu}{p^2}=0.$$

정리하면 $p(p-p_0)/\mu=\Delta_r+(p-p_0)^2/2\mu$, 즉 $\frac{p^2-p_0^2}{2\mu}=\Delta_r-\frac{p_0(p-p_0)}{\mu}$ … 대수적으로 풀면 최소점 $p_*$ 는 $p_0$ 보다 *약간 작다*(롯온 골과 원점을 잇는 직선의 접점이므로). 깊은 골 근사 $\Delta_r$ 가 클 때 $p_*\approx p_0$, $v_c\approx \Delta_r/p_0$. He-4 수치($\Delta_r\approx8.6$ K, $p_0/\hbar\approx1.9\times10^{10}$/m)로 $v_c\approx60$ m/s.

핵심: 임계속도는 *원점에서 분산곡선에 그은 접선의 기울기* 의 최솟값 — 기하학적으로 롯온 골이 지배한다.
</details>

**3. (논문 비평)** 안드로니카쉬빌리 회전 진자 실험은 "초유체 성분이 진자를 따라 돌지 않는다" 로 $\rho_s/\rho$ 를 측정한다. 이 측정이 *"별개의 초유체 입자 집단이 존재한다"* 를 증명하는가? 2-유체 모형의 존재론적 한계를 비판적으로 논하라.

<details><summary>해설</summary>

2-유체 모형은 *현상론* 이다. 진자 실험은 "정상 성분만 점성으로 끌려온다" 는 *수송 거동* 을 측정할 뿐, 미시적으로 입자가 두 종류로 갈라진 것이 아니다. 같은 헬륨 원자가 응축의 위상 결맞음을 공유하느냐(초유체 채널) 아니냐(열적 들뜸 = 정상 성분)의 문제다. $\rho_s$ 는 *위상 강성*(superfluid stiffness)의 척도이지 입자 수가 아니다 — 그 증거로 응축 분율(약 8 %)과 $\rho_s/\rho$(저온에서 거의 1)는 *다른 값* 이다. 따라서 이 실험은 위상 결맞음 흐름의 존재는 증명하나, "별개 입자 집단" 이라는 소박한 이중유체 그림은 미시적으로 정당화되지 않는다. 강상호작용계에서 $\rho_s$ 와 응축 분율을 구분하는 것이 핵심 교훈이다.
</details>

---

<div align="center">

[◀ 이전: 평균장과 그 너머](../ch2-many-body-quasiparticle/05-mean-field-beyond.md)  ·  [📚 README](../README.md)  ·  [다음: 초전도 현상 — 거시 양자 상태 ▶](02-superconductivity.md)

</div>
