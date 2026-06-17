# 천(Chern) 수와 위상 불변량

> *밴드 파동함수가 브릴루앙 영역 위에서 만드는 위상의 "감긴 횟수" — 그것이 정수이기 때문에 홀 전도도가 정수배가 된다. 위상은 모양이 아니라 다발의 불변량이다.*

## 🎯 핵심 질문

- 매개변수(파수 $\mathbf{k}$)가 단열적으로 변할 때 양자상태가 쌓는 기하적 위상 — 베리 위상 — 은 무엇이며, 어떻게 측정 가능한 곡률 $\Omega(\mathbf{k})$ 로 표현되나?
- 브릴루앙 영역 전체에 걸친 베리 곡률의 적분 $C=\frac{1}{2\pi}\int_{\text{BZ}}\Omega\,d^2k$ 가 *왜 반드시 정수* 인가?
- TKNN 공식 $\sigma_{xy}=C\,e^2/h$ 는 어떻게 [01](./01-quantum-hall.md) 의 게이지 논변이 옮긴 정수 전하를 밴드 위상으로 환원하나?

## 🌍 어디서 나타나나

- **정수 양자홀**: 채워진 각 란다우 준위가 천 수 $C=1$ 을 기여 — 총 $\sigma_{xy}=\nu e^2/h$ 의 미시적 근거.
- **천 절연체(Chern insulator) / 양자 변칙홀 효과**: 자기장 *없이도* 자기 밴드 구조만으로 $C\neq 0$. Haldane 모형(1988, 노벨상 2016)이 이론적 원형. 자성 위상 절연체(예: $\text{MnBi}_2\text{Te}_4$, 자기 도핑 $(\text{Bi,Sb})_2\text{Te}_3$)에서 2013년 실험 관측.
- **냉원자 광격자**: 인공 게이지장으로 천 밴드를 만들고 천 수를 직접 측정(반홀 변위, Bloch 진동).
- **광자 결정·메타물질**: 빛의 천 밴드 → 일방향 가장자리 전파(위상 광자학).

## 🔍 직관의 함정

**함정 1 — "위상(topology)은 시료의 모양이다."** 응집물질의 위상은 *실공간 모양* 이 아니라 **파동함수가 운동량 공간에서 만드는 다발의 위상** 이다. 도넛과 컵이 같은 위상인 것처럼, $C$ 는 밴드를 연속 변형해도 변하지 않는 정수 — 단, 갭이 닫히지 않는 한.

**함정 2 — "베리 위상은 게이지 의존이라 물리적이지 않다."** 베리 *접속* $\mathbf{A}(\mathbf{k})$ 는 게이지 의존이지만, 닫힌 경로의 베리 *위상* 과 그 곡률 $\Omega=\nabla\times\mathbf{A}$ 는 게이지 불변이다. 천 수는 곡률의 전체 적분이라 완전히 물리적이고 측정 가능하다.

**함정 3 — "$C$ 가 정수인 건 정의상 당연하다."** 전혀 당연하지 않다. $\Omega(\mathbf{k})$ 자체는 임의의 실수값 함수다. 그것의 BZ 전체 적분이 *반드시* $2\pi$ 의 정수배가 되는 것은 — 토러스(BZ) 위 $U(1)$ 다발의 천 정리라는 깊은 위상수학적 사실이다. 아래에서 윈딩 수로 직접 보인다.

## ⚙️ 제1원리 유도

### 1) 베리 위상 — 단열 변화가 남기는 기하적 흔적

매개변수 $\mathbf{R}$ 에 의존하는 해밀토니안 $H(\mathbf{R})$ 의 순간 고유상태 $|u(\mathbf{R})\rangle$. 매개변수를 단열적으로 닫힌 경로 $\mathcal{C}$ 를 따라 천천히 돌리면, 상태는 동역학적 위상 외에 추가 위상을 쌓는다. 슈뢰딩거 방정식에 $|\psi(t)\rangle=e^{i\gamma(t)}e^{-\frac{i}{\hbar}\int E\,dt}|u(\mathbf{R}(t))\rangle$ 를 넣고 정리하면

$$
\dot\gamma=i\langle u|\nabla_{\mathbf{R}}u\rangle\cdot\dot{\mathbf{R}}.
$$

닫힌 경로를 한 바퀴 돌면

$$
\gamma=\oint_{\mathcal{C}}\mathbf{A}\cdot d\mathbf{R},\qquad
\boxed{\mathbf{A}(\mathbf{R})=i\langle u(\mathbf{R})|\nabla_{\mathbf{R}}u(\mathbf{R})\rangle}\quad\square
$$

여기서 $\mathbf{A}$ 가 **베리 접속**. 결정에서는 매개변수가 블로흐 파수 $\mathbf{k}$ 이고, $|u(\mathbf{k})\rangle$ 는 주기적 블로흐 함수다.

### 2) 베리 곡률 — 게이지 불변 장세기

게이지 변환 $|u\rangle\to e^{i\phi(\mathbf{k})}|u\rangle$ 하에서 $\mathbf{A}\to\mathbf{A}-\nabla\phi$ (벡터 퍼텐셜처럼). 따라서 접속 자체는 게이지 의존. 그러나 스토크스 정리로 닫힌 경로 적분을 면적분으로 바꾸면 게이지 불변 양이 나온다:

$$
\gamma=\oint_{\mathcal{C}}\mathbf{A}\cdot d\mathbf{k}=\int_{S}\Omega\,d^2k,\qquad
\boxed{\Omega(\mathbf{k})=\nabla_{\mathbf{k}}\times\mathbf{A}(\mathbf{k})}\quad\square
$$

2차원에서 $\Omega=\partial_{k_x}A_y-\partial_{k_y}A_x$ 는 스칼라. 게이지 변환의 $\nabla\phi$ 는 회전을 취하면 사라지므로 $\Omega$ 는 게이지 불변 — 측정 가능한 "운동량 공간의 자기장" 이다.

### 3) 천 수 — BZ 토러스 위 곡률의 전체 선속

브릴루앙 영역은 위상적으로 토러스($T^2$). 그 위에서 베리 곡률을 전부 적분한 것이 **천 수**:

$$
\boxed{C=\frac{1}{2\pi}\int_{\text{BZ}}\Omega(\mathbf{k})\,d^2k.}
$$

**왜 정수인가.** BZ 를 두 패치로 덮고 각 패치에서 베리 접속 $\mathbf{A}_1,\mathbf{A}_2$ 를 매끄럽게 잡는다. 겹치는 경계에서 둘은 게이지 변환으로 연결: $\mathbf{A}_2=\mathbf{A}_1-\nabla\chi$. 스토크스 정리를 각 패치에 적용하면

$$
\int_{\text{BZ}}\Omega\,d^2k=\oint_{\partial}(\mathbf{A}_1-\mathbf{A}_2)\cdot d\mathbf{k}=\oint_{\partial}\nabla\chi\cdot d\mathbf{k}.
$$

파동함수가 단일값이려면 $e^{i\chi}$ 가 경계를 한 바퀴 돌 때 자기 자신으로 돌아와야 하므로, $\chi$ 의 총 변화는 $2\pi$ 의 정수배:

$$
\oint\nabla\chi\cdot d\mathbf{k}=2\pi n,\quad n\in\mathbb{Z}
\;\Longrightarrow\; C=n\in\mathbb{Z}.\quad\square
$$

천 수는 두 패치를 이어붙이는 전이함수의 **윈딩 수** — 위상수학적으로 정수일 수밖에 없다.

### 4) 2밴드 모형 — $C$ 가 $\hat{\mathbf d}(\mathbf k)$ 의 감김 수

가장 깨끗한 예: 임의의 2밴드 해밀토니안은 파울리 행렬로

$$
H(\mathbf{k})=\mathbf{d}(\mathbf{k})\cdot\boldsymbol\sigma=d_x\sigma_x+d_y\sigma_y+d_z\sigma_z,
$$

고유값 $\pm|\mathbf{d}|$. 아래(채워진) 밴드의 베리 곡률을 계산하면 아름다운 결과:

$$
\Omega(\mathbf{k})=-\frac{1}{2}\,\hat{\mathbf{d}}\cdot\left(\partial_{k_x}\hat{\mathbf{d}}\times\partial_{k_y}\hat{\mathbf{d}}\right),\qquad \hat{\mathbf{d}}=\frac{\mathbf{d}}{|\mathbf{d}|}.
$$

따라서 천 수는

$$
C=\frac{1}{4\pi}\int_{\text{BZ}}\hat{\mathbf{d}}\cdot\left(\partial_{k_x}\hat{\mathbf{d}}\times\partial_{k_y}\hat{\mathbf{d}}\right)d^2k.\quad\square
$$

이것은 정확히 사상 $\hat{\mathbf{d}}:T^2\to S^2$ 가 **단위 구를 몇 번 감싸는지(degree)** 를 세는 적분 — 그래서 정수다. $\hat{\mathbf d}$ 가 구 전체를 $C$ 번 덮으면 천 수는 $C$.

### 5) TKNN — 천 수가 곧 홀 전도도

Thouless–Kohmoto–Nightingale–den Nijs(1982)는 쿠보(Kubo) 선형응답 공식에서 홀 전도도를 유도했다. 채워진 밴드들에 대해

$$
\sigma_{xy}=\frac{e^2}{h}\sum_{\text{채워진 밴드}\,n}\frac{1}{2\pi}\int_{\text{BZ}}\Omega_n(\mathbf{k})\,d^2k
=\frac{e^2}{h}\sum_n C_n.
$$

따라서 총 천 수 $C=\sum_n C_n$ 으로

$$
\boxed{\sigma_{xy}=C\,\frac{e^2}{h},\qquad C\in\mathbb{Z}.}\quad\square
$$

이로써 [01](./01-quantum-hall.md) 의 게이지 논변이 옮긴 "정수 전하" 의 정체가 밝혀진다 — 그것은 채워진 밴드들의 천 수다. 무질서·모양에 무관한 정밀 양자화의 근원이 바로 이 위상 불변량의 정수성이다.

### 실험 1 — Qi-Wu-Zhang 모형의 천 수를 직접 적분

```python
import numpy as np

def d_vector(kx, ky, m):
    """Qi-Wu-Zhang 2밴드 모형: d = (sin kx, sin ky, m + cos kx + cos ky)"""
    return np.array([np.sin(kx), np.sin(ky), m + np.cos(kx) + np.cos(ky)])

def chern_number(m, N=200):
    """C = (1/4π) ∫ d̂·(∂x d̂ × ∂y d̂) d²k — d̂ 의 구 감김 수"""
    ks = np.linspace(-np.pi, np.pi, N, endpoint=False)
    dk = ks[1] - ks[0]
    C = 0.0
    for kx in ks:
        for ky in ks:
            d  = d_vector(kx, ky, m)
            dx = (d_vector(kx+dk, ky, m) - d) / dk      # ∂x d
            dy = (d_vector(kx, ky+dk, m) - d) / dk      # ∂y d
            norm = np.linalg.norm(d)
            dhat = d / norm
            # 곡률 = d̂·(∂x d̂ × ∂y d̂); ∂ d̂ 는 d/|d| 미분이지만
            # d̂·(∂d × ∂d) 형태에서 |d| 인자가 정리되어 아래와 등가
            C += np.dot(dhat, np.cross(dx, dy)) / norm**2
    return C * dk*dk / (4*np.pi)

# m 별 천 수: 위상 상전이가 정수 점프로 나타나는지 확인
for m in [-3.0, -1.0, 1.0, 3.0]:
    print(f"m={m:+.1f}  →  C ≈ {chern_number(m):+.3f}")
# 기대: m=-3 → 0,  m=-1 → +1,  m=+1 → -1,  m=+3 → 0
# |m|>2 (자명),  -2<m<0 → C=+1,  0<m<2 → C=-1 (위상 상전이는 갭이 닫히는 m=0,±2)
```

### 실험 2 — 격자 위 게이지 불변 천 수 (Fukui-Hatsugai-Suzuki)

```python
import numpy as np

def H_qwz(kx, ky, m):
    sx = np.array([[0,1],[1,0]], complex)
    sy = np.array([[0,-1j],[1j,0]], complex)
    sz = np.array([[1,0],[0,-1]], complex)
    return np.sin(kx)*sx + np.sin(ky)*sy + (m+np.cos(kx)+np.cos(ky))*sz

def lower_band(kx, ky, m):
    w, v = np.linalg.eigh(H_qwz(kx, ky, m))
    return v[:, 0]   # 낮은 에너지 고유벡터(채워진 밴드)

def chern_fhs(m, N=60):
    """링크 변수 기반 — 격자에서 정확히 정수가 나오는 게이지 불변 방법"""
    ks = np.linspace(-np.pi, np.pi, N, endpoint=False)
    # 모든 격자점 고유벡터 미리 계산
    U = np.empty((N, N, 2), complex)
    for i, kx in enumerate(ks):
        for j, ky in enumerate(ks):
            U[i, j] = lower_band(kx, ky, m)
    F_total = 0.0
    for i in range(N):
        for j in range(N):
            ip, jp = (i+1)%N, (j+1)%N
            # 작은 사각형 주위의 링크 변수 곱 → 베리 위상(플라켓)
            U1 = np.vdot(U[i,j],  U[ip,j])
            U2 = np.vdot(U[ip,j], U[ip,jp])
            U3 = np.vdot(U[ip,jp],U[i,jp])
            U4 = np.vdot(U[i,jp], U[i,j])
            F = np.angle(U1*U2*U3*U4)   # 플라켓당 베리 곡률 (게이지 불변)
            F_total += F
    return F_total / (2*np.pi)

for m in [-1.0, 1.0, 3.0]:
    print(f"m={m:+.1f}  →  C (FHS) = {chern_fhs(m):+.4f}")
# FHS 방법은 거친 격자에서도 거의 정확히 정수를 준다 (위상 불변량의 견고함)
```

## 🧪 실험·관측 증거

- **양자 변칙홀 효과(QAHE)**: $\text{Cr}$ 도핑 $(\text{Bi,Sb})_2\text{Te}_3$ 박막에서 $B=0$ 일 때 $\sigma_{xy}=e^2/h$ ($C=1$) 관측(Chang 외, *Science* 2013) — 천 수가 자기장 없이도 양자화를 만든다는 직접 증거.
- **냉원자 천 수 측정**: 광격자에서 반홀(anomalous) 변위로 $C=1$ 을 직접 측정(Jotzu 외, 2014; Aidelsburger 외, 2015).
- **광자/음향 위상 절연체**: 천 밴드의 일방향 가장자리 모드가 결함을 우회해 전파 — 천 수의 벌크–경계 대응 시연.
- **TKNN 이후**: 양자홀 고원의 정수가 채워진 밴드 천 수의 합과 모든 알려진 사례에서 일치.

## 🔬 경계

- **갭 닫힘에서 정의 불가**: 밴드 갭이 닫히는 점($m=0,\pm2$ 등)에서 천 수는 정의되지 않고, 그 지점을 가로지를 때만 정수가 점프한다(위상 상전이).
- **시간역전 대칭 보존계**: $C$ 는 시간역전을 깨야 0이 아닐 수 있다. 시간역전 보존계에서는 항상 $C=0$ 이고, 대신 $\mathbb{Z}_2$ 불변량이 필요(→ [04](./04-topological-insulator.md)).
- **상호작용 강한 경우**: 단일입자 밴드 천 수는 약상관에서만 유효. 분수 양자홀에서는 다체 천 수(많은입자 바닥상태의 위상)가 분수가 될 수 있다(→ [03](./03-fractional-quantum-hall.md)).
- **수치 함정**: 거친 격자에서 직접 미분으로 천 수를 구하면 게이지 임의성 때문에 정수에서 벗어난다. FHS 링크 변수 방법이 게이지 불변이라 안정적.

## 🧬 횡단 원리

- **(→ standard-model)**: 천 수는 게이지장의 위상 전하($\int F$)와 같은 수학 — 자기 단극·인스탄톤의 위상 양자화와 동일 구조. 응집물질의 $\hat{\mathbf d}$ 감김 수는 비선형 시그마 모형의 위상 항.
- **(→ quantum-information)**: 천 수의 정수성·견고함은 위상 양자 메모리가 국소 잡음에 견디는 이유(→ [05](./05-topological-protection.md)).
- **(→ symmetry-conservation)**: 베리 위상은 단열 불변량 — 대칭과 보존량의 기하학적 일반화. 아하로노프–봄 위상의 운동량 공간판.

## 🪜 창발

- **(L5 holography)**: 벌크 천 수 = 가장자리 카이럴 CFT 의 중심전하라는 벌크–경계 대응은, 벌크 위상이 경계 자유도를 강제한다는 점에서 홀로그래피의 응집물질 원형.
- **(L6 emergence)**: 실수값 곡률 $\Omega(\mathbf k)$ 에서 *정수* $C$ 가 창발하는 구조 — 연속에서 이산이, 국소에서 전역이 나오는 창발의 수학적 정수.

## 📐 예측·반증

- **정량 예측**: QWZ 모형에서 $-2<m<0$ 이면 $C=+1$, $0<m<2$ 면 $C=-1$, $|m|>2$ 면 $C=0$. 천 수가 바뀌는 $m=0,\pm2$ 에서만 갭이 닫힌다.
- **반증 가능성**: 만약 $\sigma_{xy}$ 가 밴드 천 수의 합이 아니라면, 천 절연체에서 $B=0$ 양자화가 정수 $e^2/h$ 의 배수가 아니어야 한다. 실측은 정확히 정수배 — TKNN 을 지지.
- **수치 검증**: FHS 방법이 거친 격자($N=20$)에서도 $C$ 를 정수 $\pm 1$ 로 재현해야 한다(위 실험 2).

## 🤔 다음 질문

천 수는 단일입자 밴드의 위상이었다. 그런데 강한 자기장 속 *상호작용하는* 전자들은 단일입자 밴드가 아예 없는 곳($\nu=1/3$)에서도 새 위상 상태를 만든다. 거기서 전하는 *분수* $e/3$ 가 되고 통계는 페르미온도 보손도 아닌 **애니온** 이 된다. 다음 문서에서 라플린 파동함수로 분수 전하와 분수 통계를 유도한다.

---

🧩 **Principle** — 밴드 파동함수가 BZ 토러스 위에서 만드는 베리 곡률의 전체 선속(천 수)은 다발의 전이함수 윈딩이라 정수이고, 그 정수가 홀 전도도 $\sigma_{xy}=Ce^2/h$ 를 양자화한다.
🔬 **Boundary** — 갭이 닫히는 점에서만 천 수가 점프하며, 시간역전 보존계에서는 $C=0$ 이고 상호작용이 강하면 다체 천 수가 분수가 될 수 있다.
🪜 **Emergence** — 실수 곡률에서 정수가 창발하는 이 구조는 위 레이어에서 벌크–경계 홀로그래피·위상 양자 메모리로 재등장하고, 천 절연체의 $B=0$ 양자화 $\sigma_{xy}=e^2/h$ 로 검증된다.

## 📝 연습문제

**1. (기초)** 2밴드 모형 $H=\mathbf{d}\cdot\boldsymbol\sigma$ 에서 채워진(낮은) 밴드의 고유벡터를 $\hat{\mathbf d}=(\sin\theta\cos\phi,\sin\theta\sin\phi,\cos\theta)$ 로 매개화할 때, 베리 곡률이 $\Omega=-\tfrac12\sin\theta\,(\partial_x\theta\,\partial_y\phi-\partial_y\theta\,\partial_x\phi)$ 임을 이용해 $\hat{\mathbf d}$ 가 구를 한 번 덮으면 $C=\pm1$ 임을 보여라.

<details><summary>해설</summary>

$\hat{\mathbf d}\cdot(\partial_x\hat{\mathbf d}\times\partial_y\hat{\mathbf d})=\sin\theta(\partial_x\theta\,\partial_y\phi-\partial_y\theta\,\partial_x\phi)$ 는 구면 좌표의 야코비안(입체각 요소 $\sin\theta\,d\theta\,d\phi$)이다. 따라서 $C=\frac{1}{4\pi}\int\sin\theta\,d\theta\,d\phi$. $\hat{\mathbf d}$ 가 구 전체($\int\sin\theta\,d\theta\,d\phi=4\pi$)를 한 번 덮으면 $C=1$, 반대 방향이면 $-1$. 곧 천 수는 $T^2\to S^2$ 사상의 감김 수(degree)다.
</details>

**2. (심화)** QWZ 모형에서 $m$ 을 $+3$ 에서 $-3$ 으로 연속적으로 줄일 때, 천 수가 $0\to -1\to +1\to 0$ 으로 바뀐다. 각 전이($m=2,0,-2$)에서 $\mathbf{d}(\mathbf{k})$ 의 어느 점에서 갭 $|\mathbf d|$ 이 닫히는지 찾고, 갭 닫힘이 천 수 점프의 필요조건임을 설명하라.

<details><summary>해설</summary>

$|\mathbf d|=0$ 은 $\sin k_x=\sin k_y=0$ 이고 $m+\cos k_x+\cos k_y=0$ 일 때. 고대칭점: $(0,0)\to m+2=0$ 즉 $m=-2$; $(\pi,\pi)\to m-2=0$ 즉 $m=2$; $(\pi,0),(0,\pi)\to m=0$. 각 점에서 디랙 콘이 닫혔다 열리며 곡률 한 단위($\pm1$)가 생성/소멸 → 천 수가 정수만큼 점프. 갭이 닫히지 않으면 $C$ 는 연속 변형 불변량이라 바뀔 수 없으므로, 갭 닫힘은 위상 상전이의 필요조건이다.
</details>

**3. (논문 비평)** TKNN(1982)은 자기 단위격자(magnetic unit cell)의 디오판토스 방정식으로 천 수를 구했다. 실제 시료에는 무리수 선속 비(無理수 $\Phi/\Phi_0$)가 흔한데, 이 경우 호프스태터 나비(Hofstadter butterfly)의 밴드 구조는 프랙탈이 된다. 무리수 선속에서도 홀 전도도가 잘 정의된 정수로 양자화될 수 있는가? 위상 불변량 관점에서 논하라.

<details><summary>해설</summary>

무리수 선속에서는 자기 단위격자가 정의되지 않아 밴드별 천 수를 단순히 셀 수 없고, 스펙트럼은 칸토어 집합(프랙탈)이 된다. 그러나 *페르미 준위가 갭 안에 있는 한* 그 갭 아래 채워진 상태들의 총 천 수(또는 동치로 스트레다 공식 $\sigma_{xy}=e\,\partial n/\partial B$)는 여전히 잘 정의된 정수다. 핵심은 천 수가 개별 밴드가 아니라 *페르미 준위 아래 채워진 부분공간 전체* 의 위상이라는 점 — 갭만 열려 있으면 무리수 선속에서도 위상 불변량은 정수로 보호된다. 실험적으로 그래핀/hBN 초격자의 호프스태터 갭에서 분수 양자화된 천 수(Wannier 도표)가 관측되어 이를 확증한다.
</details>

---

<div align="center">

[◀ 이전: 양자홀 효과](./01-quantum-hall.md)  ·  [📚 README](../README.md)  ·  [다음: 분수 양자홀 ▶](./03-fractional-quantum-hall.md)

</div>
