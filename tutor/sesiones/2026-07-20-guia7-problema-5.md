# Guía 7 EMI — Mapeo + Problema 5 (ZERO TO HERO)

## Temas que cubre la guía

Magnetostática: corrientes equivalentes de cargas en rotación, Ampère + superposición, solenoides y potencial vector, discos rotantes (dipolo), **cáscara esférica cargada en rotación**, campos dentro/fuera de cáscaras, materiales magnéticos (μ), imanes permanentes, energía magnetostática.

## Orden recomendado

### Obligatorio
1. Prob. 1 (K de cargas rotantes) — base del 4 y del 5
2. Prob. 2 (Ampère + agujero)
3. Prob. 4 (disco rotante → B en eje y lejos)
4. **Prob. 5 (cáscara esférica rotante → A y B)** ← estamos acá
5. Prob. 3 (solenoide finito / A)

### Importante
6. Prob. 6 (B interior dado → Maxwell + exterior + K)
7. Prob. 8 (cilindro magnetizado: H y B)
8. Prob. 10 (identidades de energía)

### Si sobra tiempo
9. Prob. 7 (cáscara de permeabilidad μ, Jackson 5.12)
10. Prob. 9 (M raro + energía con espira)

---

# Problema 5

**Enunciado (reformulado):** Un cascarón esférico tiene carga superficial uniforme σ₀ y gira con velocidad angular constante ω alrededor de un eje que pasa por su centro.

- **(a)** Calcular el potencial vector **A** en un punto arbitrario del espacio.
- **(b)** Calcular el campo de inducción **B** en un punto arbitrario del espacio.

La guía no escribe el radio; lo llamamos **R** (radio del cascarón).

---

## 1. Qué pide

Queremos, en **todo el espacio** (adentro y afuera del cascarón):

- el potencial vector **A(r)**,
- el campo magnético **B(r) = ∇ × A**.

No pide energía ni fuerzas: solo el mapa de **A** y **B** producido por esa carga que gira.

## 2. Idea central

Una carga superficial que gira **no es una corriente de volumen**: es una **corriente superficial** **K**.

Esa **K** sobre la esfera es *exactamente la misma* que la de una esfera con magnetización uniforme **M**. Entonces:

1. Identificamos **K → M**.
2. Usamos el resultado estándar de la esfera magnetizada uniforme (adentro campo uniforme, afuera dipolo).
3. De ahí leemos **A** y **B** en todas partes.

Importante: el cascarón **no “es”** una esfera magnetizada; es una **estrategia de equivalencia** porque producen la misma **K** en la superficie (y adentro **J = 0** en ambos casos).

## 3. Herramientas previas

### 3.1 Corriente superficial de una carga que se mueve

Si hay densidad superficial de carga σ y la superficie se mueve con velocidad **v**, la corriente superficial es

\[
\mathbf{K} = \sigma\,\mathbf{v}.
\]

Significado: carga por unidad de tiempo que cruza un segmento unitario dibujado sobre la superficie.

### 3.2 Velocidad de rotación rígida

Si el cuerpo gira con **ω** (vector), en el punto de posición **r**:

\[
\mathbf{v} = \boldsymbol{\omega}\times\mathbf{r}.
\]

### 3.3 Potencial vector magnetostático

Para corrientes estacionarias, en gauge de Coulomb,

\[
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0}{4\pi}
\int
\frac{\mathbf{J}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,dV'
\quad\text{o, si solo hay K,}\quad
\frac{\mu_0}{4\pi}
\int
\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

Y siempre

\[
\mathbf{B}=\nabla\times\mathbf{A}.
\]

### 3.4 Corrientes de magnetización (por qué aparece M)

Si un material tiene magnetización **M**:

- corriente de volumen: \(\mathbf{J}_m=\nabla\times\mathbf{M}\)
- corriente de superficie: \(\mathbf{K}_m=\mathbf{M}\times\hat{\mathbf{n}}\)

Para **M uniforme** dentro de una esfera: \(\nabla\times\mathbf{M}=0\), y solo sobrevive **K_m** en la superficie. Por eso puede imitar un cascarón con **K**.

### 3.5 Resultado de la esfera con M uniforme (lo vamos a usar y chequear)

Si \(\mathbf{M}=M\,\hat{\mathbf{z}}\) uniforme en \(r<R\) (y 0 afuera):

- **Adentro:** \(\mathbf{B}=\dfrac{2}{3}\mu_0\mathbf{M}\) (uniforme),  
  \(\mathbf{A}=\dfrac{\mu_0}{3}\mathbf{M}\times\mathbf{r}\).
- **Afuera:** campo de un dipolo con momento

\[
\mathbf{m}=\frac{4\pi}{3}R^3\mathbf{M},
\]

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\hat{\mathbf{r}}}{r^2},
\qquad
\mathbf{B}(\mathbf{r})=\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}.
\]

Más abajo **motivamos** de dónde salen **A** interior y el momento **m**.

## 4. Setup

| Símbolo | Significado |
|--------|-------------|
| \(R\) | radio del cascarón |
| \(\sigma_0\) | densidad superficial de carga (uniforme, constante) |
| \(\boldsymbol{\omega}=\omega\,\hat{\mathbf{z}}\) | velocidad angular (eje \(z\)) |
| \(\mathbf{r}\) | punto de observación |
| \(\mathbf{r}'\) | punto sobre el cascarón (\(|\mathbf{r}'|=R\)) |
| \(\mathbf{K}\) | corriente superficial |
| \(\mathbf{A},\mathbf{B}\) | potencial vector e inducción |

**Hipótesis:** magnetostática (ω constante, régimen estacionario), vacío (μ₀), cascarón idealmente delgado.

**Diagrama mental:** esfera; gira alrededor de \(z\); en el ecuador la velocidad es máxima; cerca de los polos, casi nula. Eso ya anticipa que **K ∝ sinθ**.

## 5. Pasos numerados

1. Escribir **v** y **K** sobre el cascarón.
2. Identificar el **M** equivalente (\(\mathbf{K}=\mathbf{M}\times\hat{\mathbf{r}}\)).
3. Construir **A** adentro y afuera (esfera magnetizada equivalente).
4. Calcular **B = ∇×A** (o usar los resultados equivalentes de **B**).
5. Chequear continuidad / casos límite / unidades.

## 6. Desarrollo completo

### Paso 1 — Velocidad y corriente superficial

Sobre el cascarón, \(\mathbf{r}'=R\,\hat{\mathbf{r}}\). Entonces

\[
\mathbf{v}(\mathbf{r}')
=
\boldsymbol{\omega}\times\mathbf{r}'
=
\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

(En esféricas, \(\boldsymbol{\omega}\times\mathbf{r}\) apunta en \(\hat{\boldsymbol{\varphi}}\) y su módulo es \(\omega r\sin\theta\).)

Por lo tanto

\[
\mathbf{K}(\theta)
=
\sigma_0\mathbf{v}
=
\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

Definimos la constante

\[
K_0\equiv\sigma_0\omega R
\qquad\Rightarrow\qquad
\mathbf{K}=K_0\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

### Paso 2 — Magnetización equivalente

Buscamos un **M** uniforme (solo dentro de la esfera imaginaria \(r<R\)) tal que

\[
\mathbf{K}_m=\mathbf{M}\times\hat{\mathbf{r}}
\]
coincida con **K**.

Si \(\mathbf{M}=M\,\hat{\mathbf{z}}\), entonces

\[
\mathbf{M}\times\hat{\mathbf{r}}=M\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

Igualando a \(\mathbf{K}\):

\[
M=K_0=\sigma_0\omega R
\qquad\Rightarrow\qquad
\boxed{\mathbf{M}=\sigma_0 R\,\boldsymbol{\omega}}
\]

(porque \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\)).

Adentro de esa esfera equivalente: \(\mathbf{J}_m=\nabla\times\mathbf{M}=0\).  
En el cascarón real tampoco hay corriente de volumen. Misma **K**, mismo **J=0** → mismo **A** y mismo **B** en todo el espacio.

### Paso 3 — Potencial vector A

#### (i) Interior (\(r<R\))

Para campo **B** uniforme, una elección válida de potencial vector es

\[
\mathbf{A}=\frac12\mathbf{B}\times\mathbf{r}.
\]

(Se verifica directo: \(\nabla\times(\mathbf{B}\times\mathbf{r})=\mathbf{B}(\nabla\cdot\mathbf{r})-(\mathbf{B}\cdot\nabla)\mathbf{r}=3\mathbf{B}-\mathbf{B}=2\mathbf{B}\), luego \(\nabla\times(\tfrac12\mathbf{B}\times\mathbf{r})=\mathbf{B}\).)

Para la esfera con **M** uniforme se obtiene (resultado estándar; lo recordamos y lo usamos)

\[
\mathbf{B}_{\text{int}}=\frac{2}{3}\mu_0\mathbf{M}.
\]

Justificación breve: el campo de una esfera magnetizada uniforme es el de un dipolo afuera y uniforme adentro; las condiciones de contorno de **B** y **H** (o el potencial escalar magnético) fijan el factor \(2/3\). Equivalentemente, \(\mathbf{H}_{\text{int}}=-\mathbf{M}/3\) y \(\mathbf{B}=\mu_0(\mathbf{H}+\mathbf{M})=\tfrac{2}{3}\mu_0\mathbf{M}\).

Entonces

\[
\mathbf{A}_{\text{int}}
=
\frac12\left(\frac{2}{3}\mu_0\mathbf{M}\right)\times\mathbf{r}
=
\frac{\mu_0}{3}\mathbf{M}\times\mathbf{r}.
\]

Con \(\mathbf{M}=\sigma_0 R\,\boldsymbol{\omega}\):

\[
\boxed{
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0\sigma_0 R}{3}\,\boldsymbol{\omega}\times\mathbf{r}
\qquad (r<R)
}
\]

En componentes (eje \(z\)):

\[
A_\varphi(r,\theta)=\frac{\mu_0\sigma_0\omega R}{3}\,r\sin\theta,
\quad A_r=A_\theta=0.
\]

#### (ii) Exterior (\(r>R\))

Afuera, todo se ve como un **dipolo magnético**

\[
\mathbf{m}
=
\int\mathbf{M}\,dV
=
\mathbf{M}\cdot\frac{4\pi}{3}R^3
=
\frac{4\pi}{3}R^3\sigma_0 R\,\boldsymbol{\omega}
=
\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}}.
\]

El potencial vector de un dipolo es

\[
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\hat{\mathbf{r}}}{r^2}.
\]

Sustituyendo **m**:

\[
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0}{4\pi}\cdot\frac{4\pi}{3}\sigma_0\omega R^4
\frac{\hat{\mathbf{z}}\times\hat{\mathbf{r}}}{r^2}
=
\frac{\mu_0\sigma_0\omega R^4}{3}\frac{\sin\theta}{r^2}\,\hat{\boldsymbol{\varphi}}.
\]

En forma vectorial compacta (porque \(\boldsymbol{\omega}\times\mathbf{r}=\omega r\sin\theta\,\hat{\boldsymbol{\varphi}}\)):

\[
\boxed{
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0\sigma_0 R}{3}\left(\frac{R}{r}\right)^3\boldsymbol{\omega}\times\mathbf{r}
\qquad (r>R)
}
\]

**Chequeo de continuidad en \(r=R\):** ambas expresiones dan

\[
\mathbf{A}(R,\theta)=\frac{\mu_0\sigma_0\omega R^2}{3}\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

Bien: **A** paralelo a la superficie es continuo (no hay capa delta de **B** tangencial “rara” que lo rompa; la discontinuidad va en derivadas / en **B** tangencial ligada a **K**).

### Paso 4 — Campo B

#### (i) Interior

\[
\mathbf{B}_{\text{int}}
=
\frac{2}{3}\mu_0\mathbf{M}
=
\frac{2}{3}\mu_0\sigma_0 R\,\boldsymbol{\omega}.
\]

Es decir, **uniforme** y paralelo a **ω**:

\[
\boxed{
\mathbf{B}(\mathbf{r})
=
\frac{2\mu_0\sigma_0\omega R}{3}\,\hat{\mathbf{z}}
\qquad (r<R)
}
\]

Verificación rápida con \(\mathbf{A}=\frac{\mu_0\sigma_0\omega R}{3}r\sin\theta\,\hat{\boldsymbol{\varphi}}\):

En esféricas, con solo \(A_\varphi(r,\theta)\),

\[
B_r=\frac{1}{r\sin\theta}\frac{\partial}{\partial\theta}(\sin\theta\,A_\varphi)
=\frac{2\mu_0\sigma_0\omega R}{3}\cos\theta,
\]

\[
B_\theta=-\frac{1}{r}\frac{\partial}{\partial r}(r A_\varphi)
=-\frac{2\mu_0\sigma_0\omega R}{3}\sin\theta,
\]

\[
B_\varphi=0.
\]

Eso es exactamente \(\mathbf{B}=B\hat{\mathbf{z}}\) escrito en esféricas:  
\(B_r=B\cos\theta\), \(B_\theta=-B\sin\theta\), con \(B=\frac{2\mu_0\sigma_0\omega R}{3}\). Correcto.

#### (ii) Exterior

Campo de dipolo con

\[
\mathbf{m}=\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}}:
\]

\[
\boxed{
\mathbf{B}(\mathbf{r})
=
\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}
\qquad (r>R)
}
\]

Explícitamente:

\[
B_r
=
\frac{\mu_0}{4\pi}\frac{2m\cos\theta}{r^3}
=
\frac{2\mu_0\sigma_0\omega R^4}{3}\frac{\cos\theta}{r^3},
\]

\[
B_\theta
=
\frac{\mu_0}{4\pi}\frac{m\sin\theta}{r^3}
=
\frac{\mu_0\sigma_0\omega R^4}{3}\frac{\sin\theta}{r^3},
\]

\[
B_\varphi=0.
\]

(Con \(m=|\mathbf{m}|=\frac{4\pi}{3}\sigma_0\omega R^4\).)

## 7. Resultado final

Con \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\) y radio \(R\):

**Potencial vector**

\[
\mathbf{A}(\mathbf{r})
=
\begin{cases}
\dfrac{\mu_0\sigma_0 R}{3}\,\boldsymbol{\omega}\times\mathbf{r}, & r<R,\\[10pt]
\dfrac{\mu_0\sigma_0 R}{3}\left(\dfrac{R}{r}\right)^3\boldsymbol{\omega}\times\mathbf{r}, & r>R.
\end{cases}
\]

**Campo de inducción**

\[
\mathbf{B}(\mathbf{r})
=
\begin{cases}
\dfrac{2}{3}\mu_0\sigma_0 R\,\boldsymbol{\omega}, & r<R,\\[10pt]
\dfrac{\mu_0}{4\pi}\dfrac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}, & r>R,
\end{cases}
\]

con momento dipolar

\[
\mathbf{m}=\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}}
=\frac{4\pi R^3}{3}\sigma_0 R\,\boldsymbol{\omega}.
\]

## 8. Chequeos

1. **ω → 0:** no hay movimiento → **K=0** → **A=0**, **B=0**. OK.
2. **σ₀ → 0:** sin carga → sin corriente → campos nulos. OK.
3. **Unidades:** σ₀ ~ C/m², ω ~ 1/s, R ~ m ⇒ σ₀ ω R ~ C/(m·s) = A/m = unidades de **K** y de **M**. Luego μ₀ M ~ T. OK.
4. **Lejos (r ≫ R):** **B** cae como \(1/r^3\) (dipolo). Esperable: distribución localizada de corriente con momento neto.
5. **Discontinuidad de B tangencial:** \(\hat{\mathbf{r}}\times(\mathbf{B}_{\text{out}}-\mathbf{B}_{\text{in}})=\mu_0\mathbf{K}\). En el ecuador (θ=π/2), **K** es máximo; la saltadura de **B_θ** debe ser μ₀ K₀. Con los valores de arriba se cumple (ejercicio rápido de examen).
6. **Analogía con el Prob. 1a:** ahí pedían **J** (o **K**) de la esfera rotante; acá usamos esa **K** para construir **A** y **B**.

## 9. Errores típicos de examen

- Olvidar que **v = ω R sinθ**, y poner **K** constante (mal: en los polos **K=0**).
- Usar el **m** de un dipolo “de carga” eléctrico; acá **m** sale de **M** volumétrico equivalente o de integrar corrientes.
- Escribir el campo interior como \(\frac{2}{3}\mu_0\mathbf{K}\) o confundir **M** con **K** sin el factor geométrico (acá \(M=K_0=\sigma_0\omega R\)).
- Aplicar la fórmula del dipolo también **adentro** (no: adentro es uniforme).
- Mezclar SI y cgs (factores 4π, c, etc.).
- Decir “el cascarón es una esfera magnetizada” en vez de “es equivalente en corrientes”.

## 10. Mini-resumen para recordar

> Cascarón con σ₀ que gira ⇒ **K = σ₀ (ω × r) = σ₀ ω R sinθ φ̂**.  
> Eso imita **M = σ₀ R ω** uniforme.  
> **Adentro:** **B = (2/3) μ₀ M** (uniforme), **A = (μ₀/3) M × r**.  
> **Afuera:** dipolo con **m = (4π/3) R³ M**.

---

## Siguiente paso lógico

- **Variante de práctica:** repetir el cálculo de **B** exterior sacando **∇×A** desde \(A_\varphi\propto\sin\theta/r^2\) (sin invocar de memoria el dipolo).
- **Siguiente de la guía:** Prob. 4 (disco rotante) para contrastar “eje + lejos” vs este cascarón; o Prob. 6 si querés saltar a potencial escalar magnético.
