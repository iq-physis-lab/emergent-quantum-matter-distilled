# 마그논·플라스몬 — 집단 들뜸

> *깨진 대칭은 골드스톤 모드를 낳는다. 강자성에서 스핀 회전 대칭이 깨지면 마그논(스핀파)이, 금속의 전하 밀도가 진동하면 플라스몬이 창발한다 — 같은 "집단 들뜸" 의 두 얼굴이다.*

## 🎯 핵심 질문

- 강자성체에서 모든 스핀이 한 방향으로 정렬했을 때, *왜* 그 정렬을 살짝 흔드는 들뜸(마그논)이 입자처럼 행동하고 분산 $\omega\propto k^2$ 를 가지는가?
- 마그논이 *깨진 회전 대칭의 골드스톤 모드* 라면, 강자성($\omega\propto k^2$)과 반강자성($\omega\propto k$)의 분산이 *왜* 다른가?
- 금속의 전자 기체에서 전하 밀도가 진동할 때, 플라스몬 진동수 $\omega_p=\sqrt{ne^2/m\varepsilon_0}$ 가 *왜* 유한한 갭을 가지고 $k\to0$ 에서 0으로 가지 않는가 — 골드스톤 정리의 예외인가?

## 🌍 어디서 나타나나

- **스핀파 공명·마그노닉스**: 강자성 박막에서 마그논을 마이크로파로 들뜨게 해 정보를 나르는 "마그노닉스" 소자. 마그논은 전하 없이 스핀(각운동량)만 나르므로 줄 손실(Joule heating) 없는 정보 전송의 후보다.
- **중성자 산란으로 본 스핀파**: 비탄성 중성자 산란이 마그논 분산 $\omega(\mathbf k)$ 를 직접 측정 — 강자성에서 $\propto k^2$, 반강자성에서 $\propto k$ 인 것이 정량 확인된다.
- **금속의 플라스몬·플라스모닉스**: 금속 표면의 전자 기체가 빛과 결합해 표면 플라스몬을 만든다. 나노 광학·SERS(표면증강 라만)·메타물질의 핵심. 알루미늄의 벌크 플라스몬 에너지 $\hbar\omega_p\approx15\,\text{eV}$ 는 전자 에너지 손실 분광(EELS)으로 측정된다.
- **별·반도체의 플라스마**: 같은 $\omega_p$ 공식이 이온화 기체(플라스마)와 반도체의 도핑 전하 진동에도 적용된다 — 도핑 농도 $n$ 의 직접 측정 수단.

## 🔍 직관의 함정

**오해 1: "마그논은 한 스핀이 뒤집힌 것이다."**
한 스핀만 국소적으로 뒤집은 상태는 해밀토니안의 고유상태가 *아니다* — 그것은 여러 마그논의 중첩이다. 진짜 마그논(고유상태)은 스핀 뒤집힘이 *모든* 격자점에 평면파 위상 $e^{i\mathbf k\cdot\mathbf R}$ 로 퍼진 *집단* 상태다. 들뜸 하나가 격자 전체에 비국소적으로 분포한다 — 이것이 "집단 들뜸" 의 본질이다.

**오해 2: "골드스톤 모드는 언제나 $\omega\to0$ 인 무질량 모드다."**
골드스톤 정리는 *연속 대칭이 자발적으로 깨지면* 무질량(갭 없는) 모드가 나온다고 말한다. 하지만 두 가지 예외가 있다. (i) 강자성 마그논은 깨진 대칭의 생성자(스핀 $S^x, S^y$)가 서로 *켤레* 라서, 두 개의 갭 없는 모드 대신 *하나* 의 $\omega\propto k^2$ 모드가 나온다(type-II 골드스톤). (ii) 플라스몬은 장거리 쿨롱 상호작용이 골드스톤 모드를 "잡아먹어"(앤더슨–힉스 메커니즘의 응집물질 원형) 유한 갭 $\omega_p$ 를 준다. 골드스톤 정리는 *단거리* 상호작용을 전제하기 때문이다.

**오해 3: "플라스몬은 그냥 빛이다."**
플라스몬은 전하 밀도의 *세로*(longitudinal) 진동 — 전기장이 진동 방향과 *나란* 하다. 빛(광자)은 *가로*(transverse) 모드다. 둘은 다른 들뜸이지만, 금속 표면에서 결합해 "플라스몬–폴라리톤" 이라는 혼합 모드를 만든다. 벌크 플라스몬 자체는 빛이 아니라 전자 기체의 집단 진동이다.

## ⚙️ 제1원리 유도

### 1. 하이젠베르크 강자성과 스핀 정렬

강자성의 미시 모형은 하이젠베르크 해밀토니안이다. 최근접 격자점 스핀이 교환 상호작용 $J>0$ 로 정렬을 선호한다:

$$
\hat H = -J\sum_{\langle ij\rangle}\hat{\mathbf S}_i\cdot\hat{\mathbf S}_j
= -J\sum_{\langle ij\rangle}\Big[\hat S_i^z\hat S_j^z + \tfrac12(\hat S_i^+\hat S_j^- + \hat S_i^-\hat S_j^+)\Big].
$$

$J>0$ 이므로 모든 스핀이 같은 방향(예: $+z$)으로 정렬한 상태 $|0\rangle=|\!\uparrow\uparrow\cdots\uparrow\rangle$ 가 바닥상태다. 이 상태는 해밀토니안의 연속 회전 대칭 $SU(2)$ 를 *자발적으로 깬다* — 바닥상태가 특정 방향($z$)을 골랐기 때문이다. 깨진 대칭이 두 개($S^x, S^y$ 방향 회전)이므로 골드스톤 모드를 기대한다. $\square$

### 2. 홀스타인–프리마코프 변환

스핀 연산자를 보존 생성·소멸 연산자로 바꾸는 것이 **홀스타인–프리마코프(HP) 변환** 이다. 정렬 방향 $+z$ 에서 스핀 뒤집힘을 보존(마그논) 하나로 센다:

$$
\hat S_i^z = S - \hat a_i^\dagger \hat a_i,\qquad
\hat S_i^+ = \sqrt{2S}\,\sqrt{1-\frac{\hat a_i^\dagger \hat a_i}{2S}}\;\hat a_i,\qquad
\hat S_i^- = \sqrt{2S}\,\hat a_i^\dagger\sqrt{1-\frac{\hat a_i^\dagger \hat a_i}{2S}}.
$$

$\hat a_i^\dagger \hat a_i$ 는 격자점 $i$ 의 스핀 뒤집힘 수(마그논 수)다. $[\hat a_i,\hat a_j^\dagger]=\delta_{ij}$ 인 보존 대수를 만족한다(스핀 교환 관계를 정확히 재현하도록 설계). 들뜸이 약할 때($\langle \hat a^\dagger\hat a\rangle\ll S$) 제곱근을 전개한다:

$$
\hat S_i^+ \approx \sqrt{2S}\,\hat a_i,\qquad \hat S_i^-\approx\sqrt{2S}\,\hat a_i^\dagger.
$$

이것이 **선형 스핀파 근사** 다. 마그논 수가 적을 때(저온·긴 파장) 정확하다. $\square$

### 3. 강자성 마그논 분산 $\omega\propto k^2$

HP 변환을 해밀토니안에 넣고 $\hat a^\dagger\hat a\hat a^\dagger\hat a$ 같은 4차(상호작용) 항을 버리면, 2차 항만 남는다. 푸리에 변환 $\hat a_i=\frac{1}{\sqrt N}\sum_{\mathbf k}e^{i\mathbf k\cdot\mathbf R_i}\hat a_{\mathbf k}$ 로 대각화하면:

$$
\hat H \approx E_0 + \sum_{\mathbf k}\hbar\omega(\mathbf k)\,\hat a_{\mathbf k}^\dagger \hat a_{\mathbf k},\qquad
\hbar\omega(\mathbf k) = 2JSz\big[1-\gamma(\mathbf k)\big],
$$

여기서 $z$ 는 최근접 수, $\gamma(\mathbf k)=\frac1z\sum_{\boldsymbol\delta}e^{i\mathbf k\cdot\boldsymbol\delta}$ 는 격자 인자다($\boldsymbol\delta$: 최근접 벡터). 1차원 사슬($z=2$, 간격 $a$)에서 $\gamma(k)=\cos ka$ 이므로

$$
\hbar\omega(k) = 4JS(1-\cos ka) = 8JS\sin^2\frac{ka}{2}.
$$

긴 파장 극한 $k\to0$ 에서 $\cos ka\approx 1-\tfrac12(ka)^2$ 를 쓰면

$$
\boxed{\;\hbar\omega(\mathbf k)\xrightarrow{k\to0} 2JS a^2\,k^2 \;\propto\; k^2\;}
$$

강자성 마그논의 분산은 *2차* — $k\to0$ 에서 $\omega\to0$(갭 없음, 골드스톤)이지만 *선형이 아니라 제곱* 이다. 깨진 대칭 생성자 $S^x, S^y$ 가 서로 켤레(정준 짝)이기 때문에 두 골드스톤 모드가 하나의 $\omega\propto k^2$ 모드로 합쳐진다 — type-II 골드스톤 보존이다. $\square$

### 4. 반강자성 마그논 분산 $\omega\propto k$

반강자성($J<0$, 또는 $J>0$ 의 반대 부호 모형)에서는 이웃 스핀이 *반대* 방향으로 정렬한다(네엘 상태). 두 부격자 A($\uparrow$)·B($\downarrow$)를 각각 HP 변환하면, 부격자 B의 정렬 방향이 $-z$ 라서 변환이 다르다. 결과 해밀토니안은 $\hat a_{\mathbf k}^\dagger \hat b_{-\mathbf k}^\dagger$ 같은 *비대각* 항(쌍 생성)을 포함한다:

$$
\hat H \approx \sum_{\mathbf k}\Big[A_{\mathbf k}(\hat a_{\mathbf k}^\dagger \hat a_{\mathbf k}+\hat b_{\mathbf k}^\dagger \hat b_{\mathbf k}) + B_{\mathbf k}(\hat a_{\mathbf k}^\dagger \hat b_{-\mathbf k}^\dagger + \text{h.c.})\Big],
$$

여기서 $A_{\mathbf k}=2|J|Sz$, $B_{\mathbf k}=2|J|Sz\,\gamma(\mathbf k)$. 이런 형태는 **보골류보프 변환** 으로 대각화한다. 새 보존 $\hat\alpha,\hat\beta$ 를 $\hat a=\cosh\theta_{\mathbf k}\,\hat\alpha - \sinh\theta_{\mathbf k}\,\hat\beta^\dagger$ 꼴로 잡아 비대각 항을 없애면, 마그논 에너지는

$$
\hbar\omega(\mathbf k) = \sqrt{A_{\mathbf k}^2 - B_{\mathbf k}^2} = 2|J|Sz\sqrt{1-\gamma(\mathbf k)^2}.
$$

긴 파장에서 $\gamma(\mathbf k)\approx 1-\tfrac12(ka)^2$ 이므로 $1-\gamma^2\approx (ka)^2$, 따라서

$$
\boxed{\;\hbar\omega(\mathbf k)\xrightarrow{k\to0} 2|J|Sz\,a\,|k|\;=\;v_s|k|\;\propto\; k\;}
$$

반강자성 마그논은 *선형* 분산(스핀파 "음속" $v_s$)을 가진다. 강자성과 결정적으로 다르다! 그 이유는 반강자성 질서변수(네엘 벡터)가 *각운동량 자체를 보존* 하지 않아, 깨진 두 대칭 생성자가 정준 짝을 이루지 못하고 두 개의 독립 선형 골드스톤 모드(type-I)로 나타나기 때문이다. *같은* 회전 대칭 깨짐이라도 질서의 종류가 골드스톤 분산을 바꾼다. $\square$

### 5. 골드스톤 정리와 마그논

음향 포논이 *병진* 대칭 깨짐의 골드스톤이었듯(→ [03-phonon.md](03-phonon.md)), 마그논은 *회전(스핀)* 대칭 깨짐의 골드스톤이다. 골드스톤 정리: 연속 대칭 $G$ 가 부분군 $H$ 로 자발 깨지면, $\dim(G/H)$ 개의 무질량 모드가 나온다. 그러나 *세는 법* 이 미묘하다:

- **type-I**(반강자성·초유체): 깨진 생성자마다 하나씩, $\omega\propto k$.
- **type-II**(강자성): 켤레 생성자 쌍이 *하나* 의 모드를 주고, $\omega\propto k^2$.

니엘센–치누마(Nielsen–Chinowsky) 정리: $N_{\text{I}}+2N_{\text{II}} = \dim(G/H)$. 강자성은 $\dim(G/H)=2$($S^x,S^y$)이고 $N_{\text{II}}=1$ — 단 하나의 $k^2$ 마그논. 이것이 강자성과 반강자성 분산 차이의 *대칭적* 기원이다. $\square$

### 실험 1 — 마그논 분산: 강자성 $k^2$ vs 반강자성 $k$ (numpy)

```python
import numpy as np

# 1D 스핀 사슬의 마그논 분산을 강자성/반강자성 두 경우로 계산해 비교.
# 강자성(FM):   ħω = 4JS(1 - cos ka)            → k→0 에서 ∝ k^2
# 반강자성(AF): ħω = 2|J|Sz √(1 - γ(k)^2),  z=2, γ=cos ka  → k→0 에서 ∝ k
# 핵심: 같은 회전대칭 깨짐인데 골드스톤 분산 지수가 다르다(type-II vs type-I).

a, J, S, z = 1.0, 1.0, 0.5, 2
k = np.linspace(-np.pi/a, np.pi/a, 800)
gamma = np.cos(k*a)                      # 1D 최근접 격자 인자

w_FM = 4*J*S*(1 - np.cos(k*a))           # 강자성
w_AF = 2*abs(J)*S*z*np.sqrt(np.clip(1 - gamma**2, 0, None))  # 반강자성

# k→0 에서 분산의 멱지수를 로그-로그 기울기로 추출
mask = (k > 1e-3) & (k < 0.3)            # 작은 양의 k 창
slope_FM = np.polyfit(np.log(k[mask]), np.log(w_FM[mask]), 1)[0]
slope_AF = np.polyfit(np.log(k[mask]), np.log(w_AF[mask]), 1)[0]

print(f"강자성  ω∝k^p,  수치 p = {slope_FM:.3f}  (이론 2.000 → k^2, type-II 골드스톤)")
print(f"반강자성 ω∝k^p, 수치 p = {slope_AF:.3f}  (이론 1.000 → k,   type-I 골드스톤)")

# 두 분산 모두 k→0 에서 ω→0 (골드스톤, 갭 없음) 인지 확인
i0 = np.argmin(np.abs(k))
print(f"\nk=0 에서: ω_FM = {w_FM[i0]:.3e},  ω_AF = {w_AF[i0]:.3e}  (둘 다 → 0)")
print(f"AF 긴파장 음속 v_s ≈ {(w_AF[i0+1]-w_AF[i0])/(k[i0+1]-k[i0]):.4f}  (이론 2|J|Sz·a = {2*abs(J)*S*z*a:.4f})")
```

이 코드는 강자성에서 멱지수 $p\approx2$($\omega\propto k^2$), 반강자성에서 $p\approx1$($\omega\propto k$)을 수치로 확인한다 — 같은 회전 대칭 깨짐이 질서의 종류(FM/AF)에 따라 다른 골드스톤을 낳음을 눈으로 본다.

### 6. 전자 기체의 플라스몬 — 드루드 그림

이제 *전하* 자유도로 간다. 균일 전자 기체(밀도 $n$, 질량 $m$, 전하 $-e$)가 평형에서 살짝 변위 $\mathbf u$ 하면, 전하 밀도 요동 $\delta\rho = -e\,\delta n$ 이 생기고, 그것이 복원하는 전기장을 만든다. 연속 방정식과 가우스 법칙을 결합한다. 전자 한 덩어리가 거리 $u$ 만큼 변위하면 양 끝에 면전하 $\sigma=\pm n e u$ 가 생기고, 그 사이 전기장 $E=\sigma/\varepsilon_0 = neu/\varepsilon_0$ 이 복원력으로 작용한다. 뉴턴 방정식:

$$
m\ddot u = -eE = -\frac{ne^2}{\varepsilon_0}u.
$$

이것은 진동수

$$
\boxed{\;\omega_p = \sqrt{\dfrac{ne^2}{m\varepsilon_0}}\;}
$$

의 단순 조화 진동이다 — **플라스몬 진동수**. 전체 전자 기체가 한 덩어리로 진동하는 집단 모드다. 중요한 점: 이 진동수는 파수 $k$ 에 *의존하지 않는다*($k\to0$ 에서 유한!) — 갭이 있는 집단 모드다. $\square$

### 7. 왜 플라스몬은 갭을 가지는가 — RPA와 앤더슨–힉스

드루드 그림은 $k\to0$ 의 유한 갭을 보였지만, *왜* 골드스톤 정리를 어기는지는 더 깊은 이유가 있다. 무작위 위상 근사(RPA)에서 유전함수는

$$
\varepsilon(\mathbf q,\omega) = 1 - V(\mathbf q)\,\chi_0(\mathbf q,\omega),\qquad V(\mathbf q)=\frac{e^2}{\varepsilon_0 q^2}\ (\text{3D 쿨롱}).
$$

플라스몬은 $\varepsilon(\mathbf q,\omega)=0$ 의 영점(전하 진동이 스스로 유지되는 조건)이다. 자유 전자 기체의 응답 $\chi_0\sim n q^2/m\omega^2$ 를 넣으면

$$
1 - \frac{e^2}{\varepsilon_0 q^2}\cdot\frac{nq^2}{m\omega^2}=0 \;\Longrightarrow\; \omega^2 = \frac{ne^2}{\varepsilon_0 m}=\omega_p^2.
$$

핵심은 쿨롱 $V(\mathbf q)\propto 1/q^2$ 의 *발산* 이 $\chi_0\propto q^2$ 를 정확히 상쇄해, $q\to0$ 에서도 유한한 $\omega_p$ 를 남긴다는 것이다. 만약 상호작용이 단거리($V\to$ 상수)였다면 $\omega\propto q$ 인 무질량 골드스톤(영음, zero sound)이 나왔을 것이다. **장거리 쿨롱이 골드스톤 모드를 "잡아먹어" 유한 질량을 준다** — 이것이 앤더슨–힉스 메커니즘의 응집물질 원형이다(초전도의 마이스너 효과도 같은 구조). $\square$

### 실험 2 — 플라스몬 진동수와 RPA 유전함수 영점 (numpy/scipy)

```python
import numpy as np
from scipy.optimize import brentq

# (A) 실제 금속의 플라스몬 에너지 ħω_p = ħ√(n e²/mε₀) 를 계산하고 측정값과 비교.
# (B) RPA 유전함수 ε(q,ω)=1 - (ω_p²/ω²)(고전 극한)의 영점이 ω_p 임을 수치로 확인.

# --- 물리 상수 (SI) ---
e   = 1.602176634e-19    # C
me  = 9.1093837015e-31   # kg
eps0= 8.8541878128e-12   # F/m
hbar= 1.054571817e-34    # J·s
eV  = 1.602176634e-19    # J

def plasmon_eV(n):                       # n: 전자 밀도 [1/m^3]
    wp = np.sqrt(n*e**2/(me*eps0))       # rad/s
    return hbar*wp/eV                    # eV

# 대표 금속 자유전자 밀도(대략): Al(3e29 보다 큼), Na, Cu
metals = {"Na": 2.65e28, "Al": 1.81e29, "Cu": 8.47e28}
print("금속  n[1/m^3]      ħω_p[eV] (계산)   실측[eV](대략)")
ref = {"Na": 5.9, "Al": 15.0, "Cu": 10.8}   # 알려진 벌크 플라스몬 에너지
for name, n in metals.items():
    print(f"{name:>3}  {n:.3e}   {plasmon_eV(n):>10.2f}        {ref[name]:>6.1f}")

# --- (B) 유전함수 영점이 ω_p 인지 brentq 로 확인 ---
n_test = 1.81e29
wp_true = np.sqrt(n_test*e**2/(me*eps0))
def eps_re(w):                            # 고전(긴파장) RPA: ε = 1 - ω_p²/ω²
    return 1 - wp_true**2/w**2
root = brentq(eps_re, 0.5*wp_true, 2*wp_true)
print(f"\nε(ω)=0 의 수치 영점 ω = {root:.4e} rad/s")
print(f"이론 ω_p             = {wp_true:.4e} rad/s   (일치)")
```

이 코드는 자유전자 밀도로 계산한 $\hbar\omega_p$ 가 실측 벌크 플라스몬 에너지(Al $\approx15\,\text{eV}$, Na $\approx5.9\,\text{eV}$)와 잘 맞음을 보이고, 유전함수 $\varepsilon(\omega)=0$ 의 영점이 정확히 $\omega_p$ 임을 확인한다 — 플라스몬이 "유전함수 영점=집단 모드" 라는 일반 원리의 사례임을 보인다.

### 8. 집단 들뜸의 일반론

포논·마그논·플라스몬을 한 틀로 보면, 모두 **응답 함수의 극(pole)** 이다. 일반 감수율 $\chi(\mathbf q,\omega)$ 가 어떤 $\omega=\omega(\mathbf q)$ 에서 발산하면(또는 $\varepsilon=0$ 이면), 그 진동수에서 계가 외부 자극 없이 스스로 진동한다 — 그것이 집단 들뜸이다. 이 들뜸이 (i) 잘 정의된 분산 $\omega(\mathbf q)$ 와 (ii) 긴 수명(좁은 폭)을 가지면 "준입자" 로 셀 수 있다. 단일 입자–구멍 연속체와 겹치는 영역(란다우 감쇠)에서는 집단 모드가 단일 들뜸으로 *붕괴* 해 폭이 넓어진다 — 준입자성이 흐려지는 곳이다. $\square$

## 🧪 실험·관측 증거

- **중성자 비탄성 산란(마그논)**: 강자성체(예: EuO, Fe)에서 $\omega\propto k^2$, 반강자성체(예: MnF₂, RbMnF₃)에서 $\omega\propto k$ 인 마그논 분산이 직접 측정되어 이론과 정량 일치. 스핀파 강성 $D$($\hbar\omega=Dk^2$)는 교환 $J$ 와 직결.
- **마그논 비열·자화의 블로흐 $T^{3/2}$ 법칙**: 강자성 마그논($\omega\propto k^2$)의 보스 통계로부터 저온 자화 감소 $\Delta M\propto T^{3/2}$ — 측정값이 정확히 따른다. 포논의 $T^3$ 와 지수가 다른 것이 분산 지수 차이의 직접 증거.
- **전자 에너지 손실 분광(EELS, 플라스몬)**: 빠른 전자가 시료를 지나며 플라스몬을 들뜨게 해 잃는 에너지가 $\hbar\omega_p$ 의 정수배로 나타남(Al $\approx15.0\,\text{eV}$, 다중 플라스몬 봉우리). 자유전자 모형 예측과 잘 맞는다.
- **표면 플라스몬 공명(SPR)**: 금·은 나노입자의 색·바이오센서. 빛과 결합한 표면 플라스몬의 공명 진동수가 입자 크기·환경에 민감.

## 🔬 경계

집단 들뜸 그림이 깨지는 곳:

- **란다우 감쇠**: 집단 모드의 분산이 단일 입자–구멍 들뜸 연속체와 겹치면, 마그논·플라스몬이 단일 들뜸으로 붕괴해 수명이 짧아진다. 큰 $\mathbf q$ 의 플라스몬은 입자–구멍 연속체에 진입해 넓은 봉우리가 된다 — 준입자성이 사라진다.
- **선형 스핀파의 한계**: HP 변환의 4차(마그논–마그논 상호작용) 항을 버린 것이 선형 근사다. 저차원(1D·2D)·고온·작은 $S$ 에서는 상호작용·열요동이 커서 정렬 자체가 무너진다 — 1D에서는 머민–바그너 정리로 유한 온도 자발 자화가 *불가능* 하다.
- **강상관·모트**: 전자가 강하게 묶이면(모트 절연체) 단순 전자 기체 플라스몬 그림이 무너지고, 스핀과 전하가 분리되는 새 들뜸(스피논·홀론)이 나올 수 있다(→ [Ch5-02](../ch5-emergent-gauge/02-fractionalization.md)).
- **비조화·비선형**: 큰 진폭에서 마그논·플라스몬이 비선형적으로 결합(스핀파 불안정·고조파 생성).

## 🧬 횡단 원리

- **(→ L0 symmetry)**: 마그논은 *연속 회전(스핀) 대칭의 자발 깨짐* 의 골드스톤 모드다. 음향 포논(병진 대칭)·초유체 음향 모드(게이지 대칭)와 *같은* 골드스톤 정리의 사례 — 깨진 대칭이 있으면 갭 없는 모드가 따라온다. type-I/type-II 의 구분(니엘센–치누마)이 분산 지수를 결정한다.
- **(→ standard-model, L3)**: 플라스몬의 갭 생성(장거리 쿨롱이 골드스톤을 잡아먹음)은 **앤더슨–힉스 메커니즘** 의 원형이다 — 입자물리의 힉스 메커니즘과 *같은 수학*. 게이지장이 골드스톤 모드를 흡수해 질량을 얻는다. 응집물질이 입자물리를 앞질러 발견했다(Anderson 1962).
- **(→ Ch3)**: 초전도의 마이스너 효과(광자가 초전도체 안에서 질량을 얻어 자기장 배제)도 같은 앤더슨–힉스 구조다 — 깨진 $U(1)$ 게이지 대칭 + 골드스톤 흡수.

## 🪜 창발

- **창발 게이지장(→ Ch5)**: 마그논을 넘어, 좌절된 자성체(스핀 액체)에서는 스핀 들뜸이 *분수화* 되어 스피논과 *창발 게이지장* 으로 쪼개진다 — 집단 들뜸의 극단. 마그논이 "정렬된 질서의 골드스톤" 이라면, 스피논은 "질서 없는 양자 액체의 창발 입자" 다.
- **L6 emergence**: 마그논·플라스몬은 포논과 함께 "집단 들뜸의 동물원" 을 이룬다 — 근본 자유도(스핀·전하)에 없던 *입자성* 이 다수의 결합에서 창발한다. 깨진 대칭마다 고유한 골드스톤이 나온다는 보편 구조가 응집물질·입자물리·우주론을 관통한다.

## 📐 예측·반증

- **마그논 분산 지수**: 강자성 $\hbar\omega=Dk^2$(스핀 강성 $D=2JSa^2$), 반강자성 $\hbar\omega=v_s|k|$. 중성자 산란으로 검증 — 지수가 다르면 질서의 종류(FM/AF/페리)를 잘못 본 것.
- **블로흐 $T^{3/2}$ 법칙**: 강자성 저온 자화 $M(T)=M_0(1-cT^{3/2})$. 지수가 $3/2$ 가 아니면 마그논 분산이 $k^2$ 가 아니라는 신호(갭·이방성).
- **플라스몬 진동수**: $\hbar\omega_p=\hbar\sqrt{ne^2/m^*\varepsilon_0}$ — 도핑 농도 $n$ 으로 검증. EELS·광학 반사 가장자리(plasma edge)가 예측과 일치해야 한다. 유효질량 $m^*$ 의 측정 수단.
- **골드스톤 갭 부재(마그논)**: 등방 강자성에서 $k\to0$ 마그논 갭은 0이어야 한다(회전 대칭). 갭이 측정되면 이방성·외부 자기장이 대칭을 명시적으로 깬 것.

## 🤔 다음 질문

포논·마그논·플라스몬은 모두 *약한 들뜸* 을 다루는 그림 — 평형 정렬 주위의 작은 진동이다. 그런데 정렬(질서) 자체는 *어떻게* 기술하는가? 강자성의 자화, 초전도의 갭, 결정의 질서변수는 모두 "평균장" 으로 자기일관하게 결정된다. 평균장 $\langle s_i s_j\rangle\approx\langle s_i\rangle\langle s_j\rangle$ 은 *언제* 정확하고, *언제* 요동에 무너지는가? 상부 임계차원과 긴즈부르크 기준이 그 경계를 긋는다. 다음 문서에서 유도한다.

---

🧩 **Principle** — 깨진 연속 대칭은 골드스톤 집단 들뜸을 낳는다: 강자성 회전 대칭 깨짐은 $\omega\propto k^2$ 마그논(type-II), 반강자성은 $\omega\propto k$ 마그논(type-I)을, 전하 진동은 갭 있는 플라스몬 $\omega_p=\sqrt{ne^2/m\varepsilon_0}$ 을 창발시킨다.
🔬 **Boundary** — 집단 모드는 란다우 감쇠(입자–구멍 연속체)·강상관·저차원 요동(머민–바그너)·비선형 결합에서 준입자성을 잃는다.
🪜 **Emergence** — 플라스몬의 갭 생성은 앤더슨–힉스 메커니즘의 원형으로 입자물리 힉스·초전도 마이스너로 이어지고, 좌절된 자성에서는 마그논이 스피논·창발 게이지장으로 분수화되며, 마그논 $k^2$ 는 블로흐 $T^{3/2}$ 법칙·중성자 산란으로 검증된다.

## 📝 연습문제

**1. (기초)** 1차원 강자성 하이젠베르크 사슬($S=1/2$, 최근접 $J>0$)에서 마그논 분산 $\hbar\omega(k)=4JS(1-\cos ka)$ 를 출발점으로, 긴 파장 극한($k\to0$)의 분산이 $\hbar\omega\approx 2JSa^2 k^2$ 임을 보이고, 스핀 강성 $D=2JSa^2$ 를 명시하라. 영역 경계 $k=\pi/a$ 에서의 마그논 에너지는 얼마인가?

<details>
<summary>해설</summary>

$\cos ka$ 를 테일러 전개하면 $\cos ka\approx 1-\tfrac12(ka)^2+\cdots$ 이므로 $1-\cos ka\approx \tfrac12(ka)^2$. 따라서

$$
\hbar\omega(k)\approx 4JS\cdot\tfrac12 a^2k^2 = 2JSa^2 k^2 \equiv Dk^2,\qquad D=2JSa^2.
$$

이것이 강자성 스핀파의 $k^2$ 분산이고, $D$ 가 스핀 강성이다($S=1/2$ 면 $D=Ja^2$). 영역 경계 $k=\pi/a$ 에서 $\cos(\pi)= -1$ 이므로

$$
\hbar\omega(\pi/a)=4JS(1-(-1))=8JS.
$$

($S=1/2$ 면 $4J$.) 이 지점에서 군속도 $d\omega/dk=4JSa\sin ka$ 는 $\sin\pi=0$ 이라 0 — 정상파(이웃 스핀 뒤집힘이 정반대 위상)다. 포논의 영역 경계와 같은 구조다.

</details>

**2. (심화)** 반강자성 마그논 분산 $\hbar\omega(\mathbf k)=2|J|Sz\sqrt{1-\gamma(\mathbf k)^2}$($\gamma=\cos ka$, 1D)에서, (a) $k\to0$ 극한이 선형 $\hbar\omega=v_s|k|$ 임을 보이고 음속 $v_s$ 를 $J,S,z,a$ 로 표현하라. (b) 강자성이 $k^2$, 반강자성이 $k$ 인 차이가 *대칭적으로* 왜 생기는지(type-I vs type-II) 니엘센–치누마 세는 법으로 설명하라.

<details>
<summary>해설</summary>

(a) $\gamma=\cos ka\approx 1-\tfrac12(ka)^2$ 이므로 $\gamma^2\approx 1-(ka)^2$, 즉 $1-\gamma^2\approx (ka)^2$. 따라서

$$
\hbar\omega\approx 2|J|Sz\sqrt{(ka)^2}=2|J|Sz\,a\,|k| = v_s|k|,\qquad v_s=2|J|Sz\,a.
$$

선형 분산(스핀파 음속)이다. (b) 깨진 대칭은 두 경우 모두 $SU(2)\to U(1)$ 로 $\dim(G/H)=2$($S^x,S^y$ 회전). 니엘센–치누마: $N_{\text{I}}+2N_{\text{II}}=2$.

- **강자성**: 질서변수가 *총 스핀(각운동량)* — 깨진 생성자 $S^x,S^y$ 가 보존량 $S^z$ 를 통해 서로 켤레(정준 짝). 두 생성자가 하나의 type-II 모드로 묶임: $N_{\text{II}}=1, N_{\text{I}}=0$. type-II 골드스톤은 $\omega\propto k^2$.
- **반강자성**: 질서변수(네엘 벡터)가 총 각운동량을 보존하지 않음 — 깨진 생성자가 정준 짝을 이루지 못함. 두 독립 type-I 모드: $N_{\text{I}}=2, N_{\text{II}}=0$. type-I 골드스톤은 $\omega\propto k$.

따라서 *같은* 회전 대칭 깨짐이라도 질서변수가 보존량인지 아닌지가 골드스톤의 종류와 분산 지수를 결정한다. 이것이 강자성/반강자성 분산 차이의 깊은 대칭적 기원이다.

</details>

**3. (논문 비평)** 고온 초전도체(구리 산화물)에서 관측되는 "패러마그논(paramagnon)"·스핀 요동이 쿠퍼 쌍의 매개자(포논 대신)일 수 있다는 주장이 있다. (a) 포논 매개 BCS와 비교해, 마그논/스핀 요동 매개 쌍짓기가 *왜* d-파 갭(부호 바뀌는 갭)을 선호하는지 직관적으로 논하라. (b) 마그논이 잘 정의된 준입자가 아닌(반강자성 질서가 도핑으로 무너진) 영역에서 "마그논 매개" 라는 표현이 가지는 한계를 비판적으로 평가하라.

<details>
<summary>해설</summary>

(a) 포논 매개 인력은 모든 $\mathbf q$ 에서 *인력*(부호 일정)이라 등방(s-파) 갭을 선호한다($V_{\text{eff}}<0$, → [03-phonon.md](03-phonon.md)). 반면 반강자성 스핀 요동의 감수율 $\chi(\mathbf q)$ 는 반강자성 파수 $\mathbf Q=(\pi,\pi)$ 에서 강하게 피크를 가진다. 이 상호작용은 $\mathbf Q$ 만큼 떨어진 페르미면 점들을 연결하며 *척력* 적이다 — 그런데 갭 함수 $\Delta(\mathbf k)$ 가 $\mathbf k$ 와 $\mathbf k+\mathbf Q$ 에서 *부호가 반대* 이면(d-파: $\Delta\propto\cos k_x-\cos k_y$), 척력적 상호작용이 오히려 쌍짓기를 *돕는다*(갭 방정식에서 $-V\cdot\Delta(\mathbf k+\mathbf Q)$ 가 양의 기여). 그래서 스핀 요동 매개는 d-파를 선호한다. 실제 구리 산화물에서 d-파 대칭이 관측되는 것이 이 시나리오의 정황 증거다.

(b) 한계: "마그논 매개" 는 마그논이 잘 정의된 준입자(좁은 분산·긴 수명)일 때 의미가 명확하다. 그러나 초전도가 나타나는 도핑 영역에서는 반강자성 장거리 질서가 이미 무너져 마그논 대신 *넓은* 스핀 요동(패러마그논, 큰 폭의 연속체)만 남는다 — 잘 정의된 골드스톤 마그논이 아니다. 따라서 "마그논 매개" 는 비유에 가깝고, 엄밀히는 "스핀 요동 매개" 라 해야 한다. 더 근본적으로, 강상관 영역(모트 근방)에서는 페르미 액체 준입자 자체가 의심스러워(이상 금속) 약결합 BCS 틀(매개자 + 잘 정의된 페르미면)의 적용이 정당한지가 미해결이다(→ [Ch6-04](../ch6-quantum-phase-correlation/04-high-tc-superconductivity.md)). "매개자가 무엇인가" 라는 질문 자체가 약결합 그림을 전제하므로, 강상관에서는 질문의 틀을 바꿔야 할 수 있다.

</details>

---

<div align="center">

[◀ 이전: 포논](03-phonon.md)  ·  [📚 README](../README.md)  ·  [다음: 평균장과 그 너머 ▶](05-mean-field-beyond.md)

</div>
