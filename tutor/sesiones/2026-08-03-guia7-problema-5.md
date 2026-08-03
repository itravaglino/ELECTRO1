# Guía 7 — Problema 5 — ZERO TO HERO (desde absolutamente cero)

> Pedido: desarrollo completo desde cero, misma forma que Problemas 2 y 4.
> Material: `Guia_7_EMI (1).pdf`
> Camino: 1 → 2 → 4 → **5** → 8 → …
> Previo útil: Problema 1 (ítem a) — \(\mathbf{K}\) del cascarón.

---

## Mapa breve (solo contexto)

**Temas:** magnetostática (corrientes, Ampère, cargas rotantes, \(\mathbf{M}\), \(\mathbf{A}\), \(\mathbf{B}\)).

**Orden camino corto:** 1 → 2 → 4 → **5** → 8.

Abajo: **solo el problema 5**, completo.

---

# 0. Desde cero del tema

## ¿De qué habla este problema?

Hasta ahora, en electrostática, cargas **quietas** producen campo eléctrico **E**.

Acá las cargas **se mueven de forma estacionaria** (corrientes que no cambian con el tiempo). Eso produce campo magnético **B**.

Esa área se llama **magnetostática**.

## Vocabulario mínimo (lo vamos a usar)

- **Carga eléctrica:** cantidad \(q\). Unidad: coulomb (C).
- **Densidad superficial de carga \(\sigma\):** cuánta carga hay por unidad de área. Unidad: C/m².
  Si un pedacito de superficie tiene área \(da\) y carga \(dq\), entonces \(dq=\sigma\,da\).
- **Corriente eléctrica \(I\):** carga que pasa por segundo. Unidad: ampere (A = C/s).
- **Densidad de corriente superficial \(\mathbf{K}\):** corriente por unidad de ancho transversal sobre una superficie. Unidad: A/m.
- **Campo de inducción magnética \(\mathbf{B}\):** el campo magnético “que sentís” en el vacío (fuerza sobre cargas en movimiento). Unidad: tesla (T).
- **Potencial vector \(\mathbf{A}\):** un campo auxiliar del que se obtiene \(\mathbf{B}\) por una derivada. No es energía potencial; es una herramienta de cálculo.

## Las leyes de Maxwell en magnetostática (lo esencial)

En el vacío, cuando todo es estacionario:

1. **No hay monopolos magnéticos:**
   \[
   \nabla\cdot\mathbf{B}=0.
   \]
   Significado: las líneas de \(\mathbf{B}\) no empiezan ni terminan; son cerradas (o van al infinito).

2. **Ley de Ampère (forma local, sin campos que cambien en el tiempo):**
   \[
   \nabla\times\mathbf{B}=\mu_0\mathbf{J}.
   \]
   Significado: las corrientes \(\mathbf{J}\) “enroscan” el campo \(\mathbf{B}\).
   \(\mu_0\) es la permeabilidad del vacío:
   \[
   \mu_0=4\pi\times 10^{-7}\,\frac{\mathrm{T\cdot m}}{\mathrm{A}}.
   \]

Si la corriente está solo en una superficie (como en un cascarón), en vez de \(\mathbf{J}\) de volumen usamos \(\mathbf{K}\) de superficie, y la ley de Ampère en la frontera dice (lo usaremos más adelante con cuidado):

\[
\hat{\mathbf{n}}\times(\mathbf{B}_{\text{arriba}}-\mathbf{B}_{\text{abajo}})=\mu_0\mathbf{K}.
\]

## ¿Por qué aparece el potencial vector \(\mathbf{A}\)?

Como \(\nabla\cdot\mathbf{B}=0\) siempre (en magnetostática y en general), existe un campo vectorial \(\mathbf{A}\) tal que

\[
\mathbf{B}=\nabla\times\mathbf{A}.
\]

Eso no es magia: es un teorema de cálculo vectorial (“si un campo tiene divergencia nula, es el rotor de otro”).

\(\mathbf{A}\) no es único: podés sumarle el gradiente de una función escalar y \(\mathbf{B}\) no cambia. En magnetostática suele elegirse el **gauge de Coulomb**:

\[
\nabla\cdot\mathbf{A}=0.
\]

Con esa elección, la ecuación para \(\mathbf{A}\) se vuelve

\[
\nabla^2\mathbf{A}=-\mu_0\mathbf{J},
\]

cuya solución (corrientes localizadas, \(\mathbf{A}\to 0\) en el infinito) es

\[
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0}{4\pi}
\int
\frac{\mathbf{J}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,dV'.
\]

Si no hay corriente de volumen, solo superficial:

\[
\boxed{
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0}{4\pi}
\int
\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'
}
\]

Esa es la fórmula madre del ítem (a). El problema se reduce a: **encontrar \(\mathbf{K}\)** y **hacer la integral** (o un método equivalente bien justificado).

---

# Problema 5 — enunciado reformulado

Un **cascarón esférico** (superficie esférica delgada) tiene densidad de carga superficial **uniforme** \(\sigma_0\) y gira con velocidad angular **constante** \(\boldsymbol{\omega}\) alrededor de un eje que pasa por el centro.

- **(a)** Calcular \(\mathbf{A}\) en un punto cualquiera del espacio.
- **(b)** Calcular \(\mathbf{B}\) en un punto cualquiera del espacio.

La guía no escribe el radio: lo llamamos **\(R\)**.

---

## 1. Qué pide

En criollo:

> La esfera cargada está girando. Eso mueve carga ⇒ hay corriente en la cáscara ⇒ hay campo magnético.  
> Quiero las fórmulas de \(\mathbf{A}\) y \(\mathbf{B}\) **adentro** del cascarón (\(r<R\)) y **afuera** (\(r>R\)).

## 2. Idea central (sin cuentas)

1. En cada puntito del cascarón la carga se mueve ⇒ aparece una **corriente superficial \(\mathbf{K}\)**.
2. Con \(\mathbf{K}\) se determina \(\mathbf{A}\) (integral de arriba) y luego \(\mathbf{B}=\nabla\times\mathbf{A}\).
3. Calcular esa integral “a lo bruto” es pesado. Hay una **estrategia** (no es que el cascarón “sea” un imán):
   - la \(\mathbf{K}\) del cascarón es **idéntica** a la corriente superficial de una esfera con magnetización uniforme \(\mathbf{M}\);
   - ese problema se resuelve con potencial escalar magnético (ecuación de Laplace + condiciones de borde);
   - de ahí salen \(\mathbf{B}\) y \(\mathbf{A}\) en todo el espacio.

## 3. Herramientas previas (explicadas desde cero)

### 3.1 Velocidad de un punto que rota

Si un cuerpo rígido gira con velocidad angular \(\boldsymbol{\omega}\) (vector: dirección = eje, sentido = regla de la mano derecha, módulo = rad/s), un punto de posición \(\mathbf{r}\) tiene velocidad

\[
\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}.
\]

Por qué: el desplazamiento infinitesimal es un arco perpendicular a \(\boldsymbol{\omega}\) y a \(\mathbf{r}\), de longitud \(\omega r\sin\theta\,dt\), donde \(\theta\) es el ángulo entre \(\boldsymbol{\omega}\) y \(\mathbf{r}\). Eso es exactamente el producto cruz.

### 3.2 De carga móvil a corriente superficial

Imaginá un pedacito de superficie con carga \(dq=\sigma\,da\).  
Si se mueve con velocidad \(\mathbf{v}\), en un tiempo \(dt\) transporta esa carga una distancia \(\mathbf{v}dt\).

La densidad de corriente superficial se define como

\[
\mathbf{K}=\sigma\mathbf{v}.
\]

Intuición: \(\sigma\) es “carga por área”; multiplicada por velocidad da “carga por tiempo por ancho transversal” = amperes por metro.

### 3.3 Coordenadas esféricas (porque la geometría es una esfera)

Un punto se describe con \((r,\theta,\varphi)\):

- \(r\): distancia al origen (\(r\ge 0\)).
- \(\theta\): ángulo polar desde el eje \(+z\) (\(0\le\theta\le\pi\)). En el ecuador \(\theta=\pi/2\); en el polo norte \(\theta=0\).
- \(\varphi\): ángulo azimutal alrededor de \(z\) (\(0\le\varphi<2\pi\)).

Versores locales (unitarios):

- \(\hat{\mathbf{r}}\): hacia afuera.
- \(\hat{\boldsymbol{\theta}}\): hacia “aumentar \(\theta\)” (de norte a sur).
- \(\hat{\boldsymbol{\varphi}}\): hacia “aumentar \(\varphi\)” (alrededor de \(z\)).

Relación útil con cartesianas:

\[
\begin{aligned}
x&=r\sin\theta\cos\varphi,\\
y&=r\sin\theta\sin\varphi,\\
z&=r\cos\theta.
\end{aligned}
\]

Si \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\), entonces

\[
\boldsymbol{\omega}\times\mathbf{r}=\omega r\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

(Eso lo aceptamos como identidad de coordenadas; se verifica expandiendo el producto cruz en cartesianas y pasando a esféricas.)

### 3.4 Magnetización \(\mathbf{M}\) y corrientes de magnetización

En materiales, la magnetización \(\mathbf{M}\) es el momento magnético por unidad de volumen (vamos a usarla solo como herramienta).

Se demuestra (promediando corrientes microscópicas) que un \(\mathbf{M}\) produce corrientes equivalentes:

\[
\mathbf{J}_m=\nabla\times\mathbf{M}
\quad\text{(volumen)},\qquad
\mathbf{K}_m=\mathbf{M}\times\hat{\mathbf{n}}
\quad\text{(superficie)}.
\]

Si \(\mathbf{M}\) es **constante** dentro de una región, \(\nabla\times\mathbf{M}=\mathbf{0}\), y solo puede haber corriente en la superficie.

### 3.5 Campo auxiliar \(\mathbf{H}\)

Se define

\[
\mathbf{H}\equiv\frac{\mathbf{B}}{\mu_0}-\mathbf{M}.
\]

(En el vacío, \(\mathbf{M}=\mathbf{0}\), así que \(\mathbf{B}=\mu_0\mathbf{H}\).)

Tomando el rotor de \(\mathbf{B}=\mu_0(\mathbf{H}+\mathbf{M})\) y usando \(\nabla\times\mathbf{B}=\mu_0\mathbf{J}_{\text{total}}\), se obtiene

\[
\nabla\times\mathbf{H}=\mathbf{J}_f,
\]

donde \(\mathbf{J}_f\) son las **corrientes libres** (las que “ponés vos” con cables, no las de magnetización).

En nuestro problema equivalente **no habrá corrientes libres de volumen**. Entonces, en las regiones con \(\mathbf{J}_f=\mathbf{0}\),

\[
\nabla\times\mathbf{H}=\mathbf{0}
\quad\Rightarrow\quad
\mathbf{H}=-\nabla\Phi_M
\]

para alguna función escalar \(\Phi_M\) (potencial escalar magnético).

Además, \(\nabla\cdot\mathbf{B}=0\) implica, si \(\mathbf{M}\) es uniforme a trozos,

\[
\nabla\cdot\mathbf{H}=-\nabla\cdot\mathbf{M}=0
\]

dentro de cada región uniforme ⇒ \(\nabla^2\Phi_M=0\) (Laplace).

### 3.6 Soluciones de Laplace con simetría azimutal (eje \(z\))

Si el problema no depende de \(\varphi\) y es lineal en \(\cos\theta\) (lo veremos), las soluciones regulares útiles son:

- Interior (finito en \(r=0\)): \(\Phi_{\text{in}}=\alpha\, r\cos\theta\).
- Exterior (que se anule en el infinito): \(\Phi_{\text{out}}=\dfrac{\beta}{r^2}\cos\theta\).

(Estas son los términos \(l=1\) de la expansión general en polinomios de Legendre. El borde con \(\cos\theta\) solo “enciende” el modo \(l=1\).)

---

## 4. Setup

| Símbolo | Significado |
|--------|-------------|
| \(R\) | radio del cascarón |
| \(\sigma_0\) | densidad superficial de carga (uniforme) |
| \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\) | velocidad angular |
| \(\mathbf{r}\) | punto donde calculamos los campos |
| \(r=|\mathbf{r}|\) | distancia al centro |
| \(\mathbf{K}\) | corriente superficial en el cascarón |
| \(\mathbf{A}\) | potencial vector |
| \(\mathbf{B}\) | inducción magnética |
| \(\mathbf{M}\) | magnetización equivalente (estrategia) |
| \(\mathbf{H},\Phi_M\) | campo auxiliar y potencial escalar |

**Hipótesis**

- Régimen magnetostático (\(\omega\) constante; no hay campos que cambien en el tiempo de forma relevante).
- Cascarón infinitamente delgado.
- Vacío adentro y afuera (\(\mu_0\)).
- Eje de rotación = eje \(z\).

**Diagrama mental**

Esfera de radio \(R\). Gira alrededor de \(z\). En el ecuador la velocidad es máxima; en los polos es casi cero. Por eso esperamos \(\mathbf{K}\propto\sin\theta\).

---

## 5. Pasos numerados

1. Calcular \(\mathbf{v}\) y \(\mathbf{K}\) sobre el cascarón.
2. Encontrar \(\mathbf{M}\) uniforme tal que \(\mathbf{M}\times\hat{\mathbf{r}}=\mathbf{K}\) (equivalencia).
3. Plantear el problema de potencial escalar \(\Phi_M\) adentro/afuera.
4. Imponer condiciones de borde en \(r=R\) y resolver \(\alpha,\beta\).
5. Obtener \(\mathbf{H}\) y \(\mathbf{B}\) (ítem b).
6. Construir \(\mathbf{A}\) a partir de \(\mathbf{B}\) (ítem a), justificando cada región.
7. Chequear continuidad, unidades y límites.

---

## 6. Desarrollo completo

### Paso 1 — Velocidad y corriente superficial \(\mathbf{K}\)

Sobre el cascarón, la posición de un punto es \(\mathbf{r}'=R\hat{\mathbf{r}}\).

Velocidad:

\[
\mathbf{v}(\mathbf{r}')
=
\boldsymbol{\omega}\times\mathbf{r}'
=
\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

Corriente superficial:

\[
\mathbf{K}(\theta)
=
\sigma_0\mathbf{v}
=
\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

Definimos

\[
K_0\equiv\sigma_0\omega R
\qquad\Rightarrow\qquad
\mathbf{K}=K_0\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

**Lectura física:** en \(\theta=0\) (polo), \(\sin\theta=0\) ⇒ no hay corriente; en \(\theta=\pi/2\) (ecuador), máxima corriente azimutal. Tiene sentido: ahí la carga “corre” más rápido.

Con esto, el ítem (a) sería en principio

\[
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0}{4\pi}
\int
\frac{K_0\sin\theta'\,\hat{\boldsymbol{\varphi}}'}{|\mathbf{r}-\mathbf{r}'|}\,R^2\sin\theta'\,d\theta'\,d\varphi'.
\]

Esa integral se puede hacer con expansión en armónicos esféricos. En vez de ahogarnos ahí, usamos la equivalencia con magnetización, que da **el mismo** \(\mathbf{A}\) porque depende solo de las corrientes.

### Paso 2 — Magnetización equivalente (estrategia)

Buscamos un campo \(\mathbf{M}\) **constante** dentro de la bola \(r<R\) (y \(\mathbf{M}=\mathbf{0}\) afuera) tal que su corriente superficial sea exactamente la del cascarón:

\[
\mathbf{K}_m=\mathbf{M}\times\hat{\mathbf{n}}=\mathbf{M}\times\hat{\mathbf{r}}.
\]

Proponemos \(\mathbf{M}=M\hat{\mathbf{z}}\) (alineada con \(\boldsymbol{\omega}\), por simetría). Entonces

\[
\mathbf{M}\times\hat{\mathbf{r}}=M\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

Igualando a \(\mathbf{K}=K_0\sin\theta\,\hat{\boldsymbol{\varphi}}\):

\[
M=K_0=\sigma_0\omega R.
\]

Por lo tanto

\[
\boxed{\mathbf{M}=\sigma_0 R\,\boldsymbol{\omega}}.
\]

Además, como \(\mathbf{M}\) es uniforme dentro,

\[
\mathbf{J}_m=\nabla\times\mathbf{M}=\mathbf{0}.
\]

En el cascarón real tampoco hay corriente de volumen: solo \(\mathbf{K}\) en \(r=R\).

**Conclusión:** el cascarón cargado en rotación y la bola con \(\mathbf{M}=\sigma_0 R\boldsymbol{\omega}\) uniforme producen **las mismas corrientes**. Por lo tanto producen el **mismo** \(\mathbf{A}\) y el **mismo** \(\mathbf{B}\) en todo el espacio.

Repetimos: esto es una **equivalencia de corrientes**, no una afirmación de que el cascarón esté magnetizado “de verdad”.

### Paso 3 — Potencial escalar magnético

En el problema equivalente:

- No hay corrientes **libres** \(\mathbf{J}_f\) (las corrientes de magnetización ya están “metidas” en \(\mathbf{M}\)).
- Entonces \(\nabla\times\mathbf{H}=\mathbf{0}\) adentro y afuera ⇒ \(\mathbf{H}=-\nabla\Phi_M\).
- \(\mathbf{M}\) es uniforme a trozos ⇒ \(\nabla^2\Phi_M=0\) en \(r<R\) y en \(r>R\).

Por simetría azimutal y porque la condición de borde traerá un \(\cos\theta\) (lo veremos), tomamos

\[
\Phi_{\text{in}}(r,\theta)=\alpha\, r\cos\theta
\qquad(r<R),
\]

\[
\Phi_{\text{out}}(r,\theta)=\frac{\beta}{r^2}\cos\theta
\qquad(r>R).
\]

Calculemos los gradientes (útiles ya):

En esféricas, para una función \(f(r,\theta)\),

\[
\nabla f
=
\frac{\partial f}{\partial r}\hat{\mathbf{r}}
+
\frac{1}{r}\frac{\partial f}{\partial\theta}\hat{\boldsymbol{\theta}}.
\]

Entonces

\[
\mathbf{H}_{\text{in}}
=
-\nabla\Phi_{\text{in}}
=
-\alpha\cos\theta\,\hat{\mathbf{r}}
+\alpha\sin\theta\,\hat{\boldsymbol{\theta}}
=
-\alpha\,\hat{\mathbf{z}}.
\]

(La última igualdad: \(\hat{\mathbf{z}}=\cos\theta\hat{\mathbf{r}}-\sin\theta\hat{\boldsymbol{\theta}}\).)

\[
\mathbf{H}_{\text{out}}
=
-\nabla\Phi_{\text{out}}
=
\frac{2\beta}{r^3}\cos\theta\,\hat{\mathbf{r}}
+
\frac{\beta}{r^3}\sin\theta\,\hat{\boldsymbol{\theta}}.
\]

### Paso 4 — Condiciones de borde en \(r=R\)

En la superficie \(r=R\):

**(i) Continuidad de \(H_\parallel\)** (no hay corriente libre superficial; la \(\mathbf{K}_m\) ya está contabilizada vía \(\mathbf{M}\)).

Equivalente práctico: continuidad de \(\Phi_M\) (si \(\Phi\to 0\) en el infinito y es regular en el origen):

\[
\Phi_{\text{in}}(R,\theta)=\Phi_{\text{out}}(R,\theta)
\]

\[
\alpha R\cos\theta=\frac{\beta}{R^2}\cos\theta
\quad\Rightarrow\quad
\beta=\alpha R^3.
\]

**(ii) Continuidad de \(B_r\)** (porque \(\nabla\cdot\mathbf{B}=0\) ⇒ el flujo normal no puede saltar si no hay monopolos):

\[
B_r^{\text{out}}=B_r^{\text{in}}
\quad\text{en }r=R.
\]

Relaciones \(\mathbf{B}\)–\(\mathbf{H}\):

- Afuera: \(\mathbf{M}=\mathbf{0}\) ⇒ \(\mathbf{B}_{\text{out}}=\mu_0\mathbf{H}_{\text{out}}\).
- Adentro: \(\mathbf{B}_{\text{in}}=\mu_0(\mathbf{H}_{\text{in}}+\mathbf{M})\).

Componentes radiales en \(r=R\):

\[
B_r^{\text{out}}
=
\mu_0 H_r^{\text{out}}
=
\mu_0\cdot\frac{2\beta}{R^3}\cos\theta.
\]

\[
B_r^{\text{in}}
=
\mu_0\bigl(H_r^{\text{in}}+M_r\bigr)
=
\mu_0\bigl(-\alpha\cos\theta+M\cos\theta\bigr)
=
\mu_0(M-\alpha)\cos\theta.
\]

Igualando:

\[
\frac{2\beta}{R^3}=M-\alpha.
\]

Con \(\beta=\alpha R^3\):

\[
\frac{2\alpha R^3}{R^3}=M-\alpha
\quad\Rightarrow\quad
2\alpha=M-\alpha
\quad\Rightarrow\quad
3\alpha=M
\quad\Rightarrow\quad
\alpha=\frac{M}{3}.
\]

Luego

\[
\beta=\frac{M}{3}R^3.
\]

### Paso 5 — Campos \(\mathbf{H}\) y \(\mathbf{B}\) (ítem b)

#### Interior \(r<R\)

\[
\mathbf{H}_{\text{in}}=-\frac{M}{3}\hat{\mathbf{z}}.
\]

\[
\mathbf{B}_{\text{in}}
=
\mu_0\bigl(\mathbf{H}_{\text{in}}+\mathbf{M}\bigr)
=
\mu_0\Bigl(-\frac{M}{3}\hat{\mathbf{z}}+M\hat{\mathbf{z}}\Bigr)
=
\mu_0\cdot\frac{2M}{3}\hat{\mathbf{z}}.
\]

Con \(M=\sigma_0\omega R\):

\[
\boxed{
\mathbf{B}(\mathbf{r})
=
\frac{2}{3}\mu_0\sigma_0\omega R\,\hat{\mathbf{z}}
=
\frac{2}{3}\mu_0\sigma_0 R\,\boldsymbol{\omega}
\qquad(r<R)
}
\]

Es un campo **uniforme**, paralelo al eje de rotación.

#### Exterior \(r>R\)

\[
\Phi_{\text{out}}
=
\frac{M R^3}{3}\frac{\cos\theta}{r^2}.
\]

El potencial de un dipolo magnético (definición de \(\mathbf{m}\)), con la convención \(\mathbf{H}=-\nabla\Phi_M\), es

\[
\Phi_M^{\text{(dipolo)}}
=
\frac{1}{4\pi}\frac{\mathbf{m}\cdot\hat{\mathbf{r}}}{r^2}
=
\frac{m\cos\theta}{4\pi r^2}
\quad\text{si }\mathbf{m}=m\hat{\mathbf{z}}.
\]

Comparando:

\[
\frac{m}{4\pi}=\frac{M R^3}{3}
\quad\Rightarrow\quad
m=\frac{4\pi}{3}M R^3.
\]

Con \(M=\sigma_0\omega R\):

\[
\boxed{
\mathbf{m}
=
\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}}
}
\]

Y el campo de dipolo (afuera, vacío: \(\mathbf{B}=\mu_0\mathbf{H}\)) es

\[
\boxed{
\mathbf{B}(\mathbf{r})
=
\frac{\mu_0}{4\pi}
\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}
\qquad(r>R)
}
\]

Componentes (sustituyendo \(m=\frac{4\pi}{3}\sigma_0\omega R^4\)):

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

**De dónde sale la fórmula del dipolo:** es el campo \(\mathbf{H}=-\nabla\Phi\) con \(\Phi=\frac{1}{4\pi}\frac{m\cos\theta}{r^2}\). Haciendo el gradiente en esféricas se obtienen exactamente esas componentes. No es un acto de fe: es \(\mathbf{H}=-\nabla\Phi\) aplicado a ese \(\Phi\).

### Paso 6 — Potencial vector \(\mathbf{A}\) (ítem a)

Recordemos: \(\mathbf{B}=\nabla\times\mathbf{A}\). Hay que encontrar un \(\mathbf{A}\) cuyo rotor sea el \(\mathbf{B}\) que ya tenemos, con \(\mathbf{A}\to 0\) en el infinito y continuo en lo posible.

#### Interior: \(\mathbf{B}\) uniforme

Si \(\mathbf{B}=B\hat{\mathbf{z}}\) es constante, una elección válida es

\[
\mathbf{A}=\frac12\mathbf{B}\times\mathbf{r}.
\]

**Verificación explícita** (para que no quede “de memoria”):

Identidad vectorial (campos constantes):

\[
\nabla\times(\mathbf{B}\times\mathbf{r})
=
\mathbf{B}(\nabla\cdot\mathbf{r})-(\mathbf{B}\cdot\nabla)\mathbf{r}
=
\mathbf{B}\cdot 3-\mathbf{B}
=
2\mathbf{B}.
\]

Por lo tanto

\[
\nabla\times\Bigl(\frac12\mathbf{B}\times\mathbf{r}\Bigr)=\mathbf{B}.
\]

Con \(B=\frac{2}{3}\mu_0 M\):

\[
\mathbf{A}_{\text{in}}
=
\frac12\cdot\frac{2}{3}\mu_0 M\,\hat{\mathbf{z}}\times\mathbf{r}
=
\frac{\mu_0}{3}\mathbf{M}\times\mathbf{r}.
\]

Con \(\mathbf{M}=\sigma_0 R\boldsymbol{\omega}\):

\[
\boxed{
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0\sigma_0 R}{3}\,\boldsymbol{\omega}\times\mathbf{r}
\qquad(r<R)
}
\]

En componentes:

\[
A_\varphi=\frac{\mu_0\sigma_0\omega R}{3}\,r\sin\theta,
\quad A_r=A_\theta=0.
\]

#### Exterior: campo de dipolo

Para un dipolo \(\mathbf{m}\) en el origen, el potencial vector (gauge de Coulomb, \(\mathbf{A}\to 0\) en \(\infty\)) es

\[
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\hat{\mathbf{r}}}{r^2}.
\]

**Motivación breve:** es el término líder de la expansión multipolar de

\[
\mathbf{A}=\frac{\mu_0}{4\pi}\int\frac{\mathbf{J}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,dV'
\]

cuando el sistema de corrientes está localizado cerca del origen y \(r\) es grande; el momento dipolar magnético aparece como

\[
\mathbf{m}=\frac12\int\mathbf{r}'\times\mathbf{J}(\mathbf{r}')\,dV',
\]

que para magnetización uniforme coincide con \(\int\mathbf{M}\,dV=\frac{4\pi}{3}R^3\mathbf{M}\).

Sustituyendo \(\mathbf{m}=\frac{4\pi}{3}\sigma_0\omega R^4\hat{\mathbf{z}}\):

\[
\mathbf{A}
=
\frac{\mu_0}{4\pi}\cdot\frac{4\pi}{3}\sigma_0\omega R^4
\frac{\hat{\mathbf{z}}\times\hat{\mathbf{r}}}{r^2}
=
\frac{\mu_0\sigma_0\omega R^4}{3}\frac{\sin\theta}{r^2}\,\hat{\boldsymbol{\varphi}}.
\]

Forma vectorial compacta:

\[
\boxed{
\mathbf{A}(\mathbf{r})
=
\frac{\mu_0\sigma_0 R}{3}\left(\frac{R}{r}\right)^3\boldsymbol{\omega}\times\mathbf{r}
\qquad(r>R)
}
\]

#### Continuidad de \(\mathbf{A}\) en \(r=R\)

Interior en \(r=R\):

\[
A_\varphi=\frac{\mu_0\sigma_0\omega R}{3}\,R\sin\theta=\frac{\mu_0\sigma_0\omega R^2}{3}\sin\theta.
\]

Exterior en \(r=R\):

\[
A_\varphi=\frac{\mu_0\sigma_0\omega R^4}{3}\frac{\sin\theta}{R^2}=\frac{\mu_0\sigma_0\omega R^2}{3}\sin\theta.
\]

Iguales. Bien.

#### Chequeo: \(\nabla\times\mathbf{A}\) interior recupera \(\mathbf{B}\)

Con solo \(A_\varphi(r,\theta)=C r\sin\theta\) y \(C=\frac{\mu_0\sigma_0\omega R}{3}\), las fórmulas del rotor en esféricas dan:

\[
B_r
=
\frac{1}{r\sin\theta}\frac{\partial}{\partial\theta}(\sin\theta\,A_\varphi)
=
\frac{1}{r\sin\theta}\frac{\partial}{\partial\theta}(C r\sin^2\theta)
=
2C\cos\theta,
\]

\[
B_\theta
=
-\frac{1}{r}\frac{\partial}{\partial r}(r A_\varphi)
=
-\frac{1}{r}\frac{\partial}{\partial r}(C r^2\sin\theta)
=
-2C\sin\theta,
\]

\[
B_\varphi=0.
\]

Eso es \(\mathbf{B}=2C\,\hat{\mathbf{z}}\) porque

\[
B_r=B\cos\theta,\quad B_\theta=-B\sin\theta
\quad\text{con}\quad
B=2C=\frac{2\mu_0\sigma_0\omega R}{3}.
\]

Coincide con el Paso 5. El círculo se cierra.

---

## 7. Resultado final

Con radio \(R\) y \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\):

**Magnetización equivalente:** \(\mathbf{M}=\sigma_0 R\boldsymbol{\omega}\).

**Momento dipolar:** \(\mathbf{m}=\dfrac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}}\).

### (a) Potencial vector

\[
\mathbf{A}(\mathbf{r})
=
\begin{cases}
\dfrac{\mu_0\sigma_0 R}{3}\,\boldsymbol{\omega}\times\mathbf{r}, & r<R,\\[12pt]
\dfrac{\mu_0\sigma_0 R}{3}\left(\dfrac{R}{r}\right)^3\boldsymbol{\omega}\times\mathbf{r}, & r>R.
\end{cases}
\]

### (b) Campo de inducción

\[
\mathbf{B}(\mathbf{r})
=
\begin{cases}
\dfrac{2}{3}\mu_0\sigma_0 R\,\boldsymbol{\omega}, & r<R,\\[12pt]
\dfrac{\mu_0}{4\pi}\dfrac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}, & r>R.
\end{cases}
\]

---

## 8. Chequeos

1. **\(\omega=0\)** o **\(\sigma_0=0\)**: no hay corriente ⇒ \(\mathbf{A}=\mathbf{0}\), \(\mathbf{B}=\mathbf{0}\). OK.
2. **Unidades:** \(\sigma_0\omega R\) tiene unidades de A/m (igual que \(\mathbf{K}\) y que \(\mathbf{M}\)). Luego \(\mu_0 M\) es tesla. OK.
3. **Lejos:** \(\mathbf{B}\sim 1/r^3\) (dipolo). OK para un sistema localizado de corrientes.
4. **Polos vs ecuador:** \(K\propto\sin\theta\) se anula en polos; coherente con \(v=\omega R\sin\theta\).
5. **Continuidad de \(A_\varphi\)** en \(r=R\): verificada.
6. **\(\nabla\times\mathbf{A}=\mathbf{B}\)** adentro: verificado componente a componente.

---

## 9. Errores típicos de examen

- Poner \(\mathbf{K}\) constante (olvidar el \(\sin\theta\)).
- Usar la fórmula del dipolo también **adentro**.
- Confundir \(\mathbf{M}\) con \(\mathbf{K}\) sin escribir \(\mathbf{K}=\mathbf{M}\times\hat{\mathbf{r}}\).
- Mezclar \(\mathbf{B}\) y \(\mathbf{H}\) (adentro \(\mathbf{B}=\mu_0(\mathbf{H}+\mathbf{M})\), no \(\mu_0\mathbf{H}\)).
- Decir “el cascarón está magnetizado” en vez de “es equivalente en corrientes”.
- Olvidar el radio \(R\) en \(M=\sigma_0\omega R\).

---

## 10. Mini-resumen

> Cascarón con \(\sigma_0\) que gira ⇒ \(\mathbf{K}=\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}\).  
> Equivale a \(\mathbf{M}=\sigma_0 R\boldsymbol{\omega}\) uniforme.  
> Laplace + bordes ⇒ adentro \(\mathbf{B}=\tfrac{2}{3}\mu_0\mathbf{M}\) (uniforme); afuera dipolo \(\mathbf{m}=\tfrac{4\pi}{3}R^3\mathbf{M}\).  
> \(\mathbf{A}=\tfrac12\mathbf{B}\times\mathbf{r}\) adentro; \(\mathbf{A}=\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\hat{\mathbf{r}}}{r^2}\) afuera.

---

## Siguiente paso lógico

Decime cuál querés:

1. **Misma idea, otra ruta:** calcular \(\mathbf{A}\) haciendo la integral con expansión de \(1/|\mathbf{r}-\mathbf{r}'|\) (sin pasar por \(\mathbf{M}\)).
2. **Práctica:** sacar \(\mathbf{B}\) exterior haciendo \(\nabla\times\mathbf{A}\) desde \(A_\varphi\propto\sin\theta/r^2\).
3. **Siguiente ejercicio de la guía:** problema 4 (disco) o problema 6.
