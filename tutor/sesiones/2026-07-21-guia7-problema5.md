# Guía 7 EMI — Problema 5 (ZERO TO HERO)

**Fuente:** `tutor/inbox/Guia_7_EMI.pdf`  
**Tema:** Magnetostática — cascarón esférico cargado en rotación  
**Ítems:** a) potencial vector \(\mathbf{A}\); b) campo \(\mathbf{B}\)

---

## Contexto de la guía (rápido)

La Guía 7 cubre magnetostática: corrientes equivalentes, Ampère, bobinas, discos/esferas rotantes, potencial vector, magnetización, energía.

Para este problema conviene tener fresco: \(\mathbf{K}=\sigma\mathbf{v}\), definición de \(\mathbf{A}\), expansión de Green en esféricas, curl en esféricas, campo dipolar.

---

# Problema 5

**Enunciado:** Un cascarón esférico con densidad de carga uniforme \(\sigma_0\) gira alrededor de un eje que pasa por el centro con velocidad angular constante \(\boldsymbol{\omega}\).

- **a)** Calcular \(\mathbf{A}\) en un punto arbitrario del espacio.
- **b)** Determinar \(\mathbf{B}\) en un punto arbitrario del espacio.

*(El radio del cascarón no está nombrado en el enunciado: lo llamamos \(R\).)*

---

## 1. Qué pide

Tenés una esfera hueca (solo la superficie) cargada de forma uniforme. La hacés girar. Eso mueve cargas → hay corriente superficial → aparece campo magnético.

Hay que encontrar, en **todo** el espacio (adentro y afuera):

1. el potencial vector \(\mathbf{A}\);
2. el campo de inducción \(\mathbf{B}=\nabla\times\mathbf{A}\).

---

## 2. Idea central

La rotación convierte la carga superficial en una **corriente superficial** \(\mathbf{K}=\sigma_0\mathbf{v}=\sigma_0(\boldsymbol{\omega}\times\mathbf{r})\).

Esa \(\mathbf{K}\) es la fuente de \(\mathbf{A}\):

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

Por simetría esférica + eje de rotación, la integral se reduce a un cálculo con la expansión de \(1/|\mathbf{r}-\mathbf{r}'|\) en Legendre. El resultado es:

- **adentro:** \(\mathbf{A}\) lineal en \(\mathbf{r}\) → \(\mathbf{B}\) **uniforme**;
- **afuera:** \(\mathbf{A}\) de dipolo → \(\mathbf{B}\) **dipolar**.

---

## 3. Herramientas previas

### 3.1 Corriente superficial de una superficie cargada que se mueve

Si una superficie tiene densidad de carga \(\sigma\) y velocidad \(\mathbf{v}\), la corriente superficial es

\[
\mathbf{K}=\sigma\mathbf{v}.
\]

**Por qué:** en un pedacito \(da\), la carga es \(dq=\sigma\,da\). En un tiempo \(dt\) esa carga se desplaza \(\mathbf{v}\,dt\). La corriente a través de un segmento transversal es carga por unidad de tiempo por unidad de ancho transversal → \(\mathbf{K}=\sigma\mathbf{v}\).

Acá \(\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}\) (rotación rígida).

### 3.2 Potencial vector en magnetostática (gauge de Coulomb)

En vacío, estacionario:

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{J}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,dV'.
\]

Si la corriente está concentrada en una superficie:

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

Y siempre \(\mathbf{B}=\nabla\times\mathbf{A}\).

### 3.3 Expansión de Green en esféricas

Para \(r'=R\) fijo (sobre la esfera):

\[
\frac{1}{|\mathbf{r}-\mathbf{r}'|}=\sum_{\ell=0}^{\infty}\frac{r_<^\ell}{r_>^{\ell+1}}P_\ell(\cos\gamma),
\]

donde \(r_<=\min(r,R)\), \(r_>=\max(r,R)\), y \(\gamma\) es el ángulo entre \(\mathbf{r}\) y \(\mathbf{r}'\).

Ortogonalidad útil:

\[
\int P_\ell(\cos\gamma)\,P_1(\cos\gamma)\,d\Omega'=\frac{4\pi}{3}\delta_{\ell 1}.
\]

### 3.4 Curl en esféricas cuando \(\mathbf{A}=A_\phi(r,\theta)\,\hat{\phi}\)

\[
B_r=\frac{1}{r\sin\theta}\frac{\partial}{\partial\theta}(\sin\theta\,A_\phi),\qquad
B_\theta=-\frac{1}{r}\frac{\partial}{\partial r}(r A_\phi),\qquad
B_\phi=0.
\]

También: si \(\boldsymbol{\omega}\) es constante, \(\nabla\times(\boldsymbol{\omega}\times\mathbf{r})=2\boldsymbol{\omega}\).

### 3.5 Campo dipolar magnético

Si \(\mathbf{A}=\dfrac{\mu_0}{4\pi}\dfrac{\mathbf{m}\times\hat{r}}{r^2}\), entonces

\[
\mathbf{B}=\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{r})\hat{r}-\mathbf{m}}{r^3}.
\]

---

## 4. Setup

- **Datos:** \(\sigma_0\) uniforme sobre el cascarón; radio \(R\); \(\boldsymbol{\omega}\) constante.
- **Hipótesis:** magnetostática en vacío (\(\mu_0\)); cascarón infinitamente delgado; carga fija sobre la superficie (no se redistribuye).
- **Eje:** tomamos \(\boldsymbol{\omega}=\omega\,\hat{z}\) sin pérdida de generalidad (podemos rotar el sistema).
- **Notación:**
  - \(\mathbf{r}\): punto de observación;
  - \(\mathbf{r}'\): punto fuente sobre la esfera (\(r'=R\));
  - \(\mathbf{K}\): corriente superficial;
  - \(r_<\), \(r_>\): el menor/mayor entre \(r\) y \(R\).

**Diagrama mental:** paralelos de la esfera se mueven como “anillos de corriente”. Cerca del ecuador \(v=\omega R\) es máxima → \(K\) máxima; en los polos \(v=0\) → \(K=0\). Eso es exactamente el patrón de un dipolo magnético a grandes distancias.

---

## 5. Pasos numerados

1. Encontrar \(\mathbf{K}\).
2. Escribir \(\mathbf{A}\) como integral y factorizar \(\boldsymbol{\omega}\).
3. Evaluar \(\displaystyle\int\frac{\mathbf{r}'}{|\mathbf{r}-\mathbf{r}'|}\,da'\) por simetría + Legendre.
4. Obtener \(\mathbf{A}\) interior y exterior.
5. Calcular \(\mathbf{B}=\nabla\times\mathbf{A}\) adentro y afuera.
6. Identificar el momento dipolar \(\mathbf{m}\) del campo exterior.
7. Chequear continuidad / casos límite.

---

## 6. Desarrollo completo

### Paso 1 — Corriente superficial

Sobre el cascarón, \(\mathbf{r}'=R\hat{r}'\), así que

\[
\mathbf{v}(\mathbf{r}')=\boldsymbol{\omega}\times\mathbf{r}'=\boldsymbol{\omega}\times(R\hat{r}').
\]

Entonces

\[
\mathbf{K}(\mathbf{r}')=\sigma_0\,\boldsymbol{\omega}\times\mathbf{r}'=\sigma_0\omega R\sin\theta'\,\hat{\phi}'.
\]

*(Esto es el mismo tipo de objeto que en el Problema 1a de la guía.)*

### Paso 2 — Integral para \(\mathbf{A}\)

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'
=\frac{\mu_0}{4\pi}\sigma_0\,\boldsymbol{\omega}\times\int\frac{\mathbf{r}'}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

Definimos

\[
\mathbf{I}(\mathbf{r})\equiv\int\frac{\mathbf{r}'}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

### Paso 3 — Evaluar \(\mathbf{I}\)

La distribución de fuentes es esféricamente simétrica. El único vector “especial” que puede construir \(\mathbf{I}\) es \(\mathbf{r}\). Por lo tanto

\[
\mathbf{I}(\mathbf{r})=\alpha(r)\,\mathbf{r}
\]

para alguna función escalar \(\alpha(r)\).

Proyectamos sobre \(\hat{r}\):

\[
\hat{r}\cdot\mathbf{I}=\alpha r=\int\frac{\hat{r}\cdot\mathbf{r}'}{|\mathbf{r}-\mathbf{r}'|}\,da'=R\int\frac{\cos\gamma}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

Con \(da'=R^2\,d\Omega'\):

\[
\alpha r=R^3\int\frac{\cos\gamma}{|\mathbf{r}-\mathbf{r}'|}\,d\Omega'.
\]

Expandimos:

\[
\frac{1}{|\mathbf{r}-\mathbf{r}'|}=\sum_{\ell=0}^{\infty}\frac{r_<^\ell}{r_>^{\ell+1}}P_\ell(\cos\gamma),\qquad \cos\gamma=P_1(\cos\gamma).
\]

Al integrar contra \(P_1\), solo sobrevive \(\ell=1\):

\[
\int\frac{\cos\gamma}{|\mathbf{r}-\mathbf{r}'|}\,d\Omega'=\frac{r_<}{r_>^2}\cdot\frac{4\pi}{3}.
\]

Por lo tanto

\[
\alpha r=\frac{4\pi R^3}{3}\frac{r_<}{r_>^2}
\quad\Rightarrow\quad
\mathbf{I}=\frac{4\pi R^3}{3}\frac{r_<}{r_>^2}\,\hat{r}.
\]

Casos:

- **Interior** \(r<R\): \(r_<=r\), \(r_>=R\) ⇒ \(\mathbf{I}=\dfrac{4\pi R}{3}\mathbf{r}\).
- **Exterior** \(r>R\): \(r_<=R\), \(r_>=r\) ⇒ \(\mathbf{I}=\dfrac{4\pi R^4}{3r^2}\hat{r}\).

### Paso 4 — Potencial vector \(\mathbf{A}\) (ítem a)

\[
\mathbf{A}=\frac{\mu_0}{4\pi}\sigma_0\,\boldsymbol{\omega}\times\mathbf{I}.
\]

**Interior (\(r<R\)):**

\[
\mathbf{A}_{\mathrm{in}}(\mathbf{r})=\frac{\mu_0\sigma_0 R}{3}\,\boldsymbol{\omega}\times\mathbf{r}.
\]

Con \(\boldsymbol{\omega}=\omega\hat{z}\):

\[
\mathbf{A}_{\mathrm{in}}=\frac{\mu_0\sigma_0\omega R}{3}\,r\sin\theta\,\hat{\phi}.
\]

**Exterior (\(r>R\)):**

\[
\mathbf{A}_{\mathrm{out}}(\mathbf{r})=\frac{\mu_0\sigma_0 R^4}{3r^2}\,\boldsymbol{\omega}\times\hat{r}
=\frac{\mu_0\sigma_0\omega R^4}{3}\frac{\sin\theta}{r^2}\,\hat{\phi}.
\]

### Paso 5 — Campo \(\mathbf{B}\) (ítem b)

#### Interior

Como \(\nabla\times(\boldsymbol{\omega}\times\mathbf{r})=2\boldsymbol{\omega}\),

\[
\mathbf{B}_{\mathrm{in}}=\nabla\times\mathbf{A}_{\mathrm{in}}=\frac{\mu_0\sigma_0 R}{3}\cdot 2\boldsymbol{\omega}
=\frac{2\mu_0\sigma_0\omega R}{3}\,\hat{z}.
\]

Chequeo con componentes esféricas (\(A_\phi=\frac{\mu_0\sigma_0\omega R}{3}r\sin\theta\)):

\[
B_r=\frac{2\mu_0\sigma_0\omega R}{3}\cos\theta,\qquad
B_\theta=-\frac{2\mu_0\sigma_0\omega R}{3}\sin\theta,
\]

que es exactamente \(\mathbf{B}=\dfrac{2\mu_0\sigma_0\omega R}{3}\hat{z}\). Uniforme.

#### Exterior

\(A_\phi=\dfrac{\mu_0\sigma_0\omega R^4}{3}\dfrac{\sin\theta}{r^2}\) es la forma de un **dipolo**. Comparando con

\[
\mathbf{A}_{\mathrm{dip}}=\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\hat{r}}{r^2}
\]

obtenemos el momento magnético

\[
\mathbf{m}=\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{z}.
\]

Entonces

\[
\mathbf{B}_{\mathrm{out}}=\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{r})\hat{r}-\mathbf{m}}{r^3},
\]

o en componentes:

\[
B_r=\frac{\mu_0}{4\pi}\frac{2m\cos\theta}{r^3}=\frac{2\mu_0\sigma_0\omega R^4}{3r^3}\cos\theta,
\]

\[
B_\theta=\frac{\mu_0}{4\pi}\frac{m\sin\theta}{r^3}=\frac{\mu_0\sigma_0\omega R^4}{3r^3}\sin\theta,
\]

\[
B_\phi=0.
\]

---

## 7. Resultado final

Con radio \(R\) y \(\boldsymbol{\omega}=\omega\hat{z}\):

**a) Potencial vector**

\[
\boxed{
\mathbf{A}(\mathbf{r})=
\begin{cases}
\dfrac{\mu_0\sigma_0 R}{3}\,(\boldsymbol{\omega}\times\mathbf{r})
& r<R\\[0.8em]
\dfrac{\mu_0\sigma_0 R^4}{3r^2}\,(\boldsymbol{\omega}\times\hat{r})
& r>R
\end{cases}
}
\]

**b) Campo magnético**

\[
\boxed{
\mathbf{B}(\mathbf{r})=
\begin{cases}
\dfrac{2\mu_0}{3}\,\sigma_0\,(\boldsymbol{\omega})\,R
=\dfrac{2\mu_0\sigma_0\omega R}{3}\,\hat{z}
& r<R\\[0.8em]
\dfrac{\mu_0}{4\pi}\dfrac{3(\mathbf{m}\cdot\hat{r})\hat{r}-\mathbf{m}}{r^3}
& r>R
\end{cases}
}
\]

con

\[
\boxed{\mathbf{m}=\dfrac{4\pi}{3}\sigma_0\omega R^4\,\hat{z}}.
\]

---

## 8. Chequeos

- **\(r\to 0\):** \(\mathbf{A}\to 0\), \(\mathbf{B}\) finito uniforme. Razonable.
- **\(r\to\infty\):** \(\mathbf{A}\sim 1/r^2\), \(\mathbf{B}\sim 1/r^3\). Decae como dipolo (no hay monopolos magnéticos).
- **En \(r=R\):** \(A_\phi\) es continuo. \(B_r\) continuo. La componente tangencial de \(\mathbf{B}/\mu_0\) salta según \(\mathbf{K}\times\hat{n}\) (Ampère superficial).
- **Dimensiones:** \(\sigma_0\omega R\) tiene unidades de corriente/longitud (\(K\)); \(\mu_0 K\) tiene unidades de \(B\). OK.
- **Analogía:** igual que una esfera uniformemente magnetizada (equivalente a \(\mathbf{K}_m=\mathbf{M}\times\hat{n}\)). Acá \(K_\phi=\sigma_0\omega R\sin\theta\) imita \(M\sin\theta\).

---

## 9. Errores típicos de examen

- Olvidar que hay que separar **interior / exterior**.
- Usar Biot–Savart “a lo bruto” sin aprovechar simetría → se traba el cálculo.
- Confundir \(\mathbf{J}\) volumétrica con \(\mathbf{K}\) superficial.
- Perder un factor \(R\) en \(\mathbf{B}_{\mathrm{in}}\) (el resultado lleva \(\sigma_0\omega R\)).
- Escribir el dipolo exterior con \(m\) incorrecto (el valor correcto es \(\frac{4\pi}{3}\sigma_0\omega R^4\)).
- Calcular solo sobre el eje y afirmar que eso es “todo el espacio”.

---

## 10. Mini-resumen para recordar

> Cascarón cargado que rota ⇒ \(K=\sigma_0(\omega\times r)\).  
> \(\mathbf{A}\) se obtiene con Green + simetría.  
> **Adentro: \(B\) uniforme** \(\frac{2}{3}\mu_0\sigma_0\omega R\).  
> **Afuera: dipolo** con \(m=\frac{4\pi}{3}\sigma_0\omega R^4\).

---

## Siguiente paso lógico

- **Problema 6** de la misma guía (cáscara con \(\mathbf{B}\) interior dado → potencial magnético, exterior y corrientes), o
- variante: comparar con el **disco rotante** (Problema 4) y ver por qué allá el exterior no es exacto dipolo salvo lejos.
