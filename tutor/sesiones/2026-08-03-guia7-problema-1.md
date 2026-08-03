# Guía 7 — Problema 1 — ZERO TO HERO

> Camino corto: **1** → 2 → 4 → 5 → 8 → …
> Material: `Guia_7_EMI (1).pdf`

---

# 0. Desde cero del tema

En electrostática las cargas están **quietas** y producen \(\mathbf{E}\).

Acá las cargas están **en movimiento estacionario** (el patrón de corriente no cambia con el tiempo). Ese movimiento es una **corriente**, y la corriente produce campo magnético \(\mathbf{B}\).

Antes de calcular \(\mathbf{B}\), el primer paso casi siempre es: **traducir la física del enunciado a una densidad de corriente**.

## Vocabulario mínimo

| Símbolo | Qué es | Unidad |
|---------|--------|--------|
| \(\sigma\) | densidad superficial de carga (carga por área) | C/m² |
| \(\boldsymbol{\omega}\) | velocidad angular (eje + sentido + módulo) | rad/s |
| \(\mathbf{v}\) | velocidad de un puntito de materia/carga | m/s |
| \(\mathbf{J}\) | densidad volumétrica de corriente | A/m² |
| \(\mathbf{K}\) | densidad superficial de corriente | A/m |

Relaciones:

\[
\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r},
\qquad
\mathbf{K}=\sigma\mathbf{v},
\qquad
\mathbf{J}=\rho\mathbf{v}.
\]

Si la carga vive solo en una superficie, \(\rho\) tiene una **delta de Dirac** (concentra la carga en esa superficie), y entonces \(\mathbf{J}\) también la lleva.

---

## 1. Qué pide

Encontrar la distribución de corriente correspondiente a:

**(a)** Esfera de radio \(R\) con \(\sigma\) uniforme en la superficie, girando con \(\boldsymbol{\omega}\) constante.

**(b)** Disco de espesor despreciable y radio \(R\) con \(\sigma\) uniforme, girando con \(\boldsymbol{\omega}\) constante.

En criollo: “escribí \(\mathbf{J}\) (o \(\mathbf{K}\)) de cada sistema que gira”.

---

## 2. Idea central (sin cuentas)

1. La carga no se crea ni se destruye: solo **se mueve** con el cuerpo rígido.
2. En cada punto, \(\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}\).
3. Donde hay carga superficial \(\sigma\), aparece corriente superficial \(\mathbf{K}=\sigma\mathbf{v}\).
4. Si el enunciado pide \(\mathbf{J}\) volumétrica, escribimos la misma física con una delta que “pega” esa corriente a la superficie (esfera) o al plano del disco.

No hace falta Biot–Savart ni Ampère: este problema es **cinemática + definición de corriente**.

---

## 3. Herramientas previas

### 3.1 Velocidad de rotación rígida

Para rotación con \(\boldsymbol{\omega}\) constante alrededor de un eje por el origen:

\[
\mathbf{v}(\mathbf{r})=\boldsymbol{\omega}\times\mathbf{r}.
\]

Por qué: en un \(dt\), el punto se desplaza un arco perpendicular a \(\boldsymbol{\omega}\) y a \(\mathbf{r}\), de longitud \(\omega\,r\sin\alpha\,dt\). Eso es el módulo de \(\boldsymbol{\omega}\times\mathbf{r}\), y la dirección es la del producto cruz (regla de la mano derecha).

Elegimos ejes con

\[
\boldsymbol{\omega}=\omega\,\hat{\mathbf{z}}.
\]

(Si el eje fuera otro, rotamos el sistema; el resultado vectorial \(\mathbf{K}=\sigma\,\boldsymbol{\omega}\times\mathbf{r}\) es el mismo.)

### 3.2 De \(\sigma\) móvil a \(\mathbf{K}\)

Un parche \(da\) tiene carga \(dq=\sigma\,da\).

En tiempo \(dt\) esa carga se desplaza \(\mathbf{v}\,dt\). La corriente que “atraviesa” un segmento transversal de longitud \(dl_\perp\) es la carga que cruza por segundo.

La definición operativa de densidad superficial de corriente es

\[
\mathbf{K}=\sigma\mathbf{v}.
\]

Unidades: \((\mathrm{C/m^2})\cdot(\mathrm{m/s})=\mathrm{C/(s\cdot m)}=\mathrm{A/m}\). Correcto.

### 3.3 De superficie a volumen: deltas

Si toda la carga está en una superficie \(S\), la densidad volumétrica es

\[
\rho(\mathbf{r})=\sigma\,\delta_S(\mathbf{r}),
\]

donde \(\delta_S\) es la delta que integra a 1 al atravesar \(S\) en la dirección normal.

Entonces

\[
\mathbf{J}=\rho\mathbf{v}=\sigma\mathbf{v}\,\delta_S=\mathbf{K}\,\delta_S.
\]

Casos que usamos:

- Esfera \(r=R\): \(\delta_S=\delta(r-R)\) (en coordenadas esféricas, con \(dV=r^2\sin\theta\,dr\,d\theta\,d\varphi\)).
- Disco en el plano \(z=0\), \(\rho\le R\): \(\delta_S=\delta(z)\) restringido a \(\rho\le R\).

### 3.4 Coordenadas

**Esféricas** \((r,\theta,\varphi)\):

\[
\mathbf{r}=r\hat{\mathbf{r}},
\qquad
\boldsymbol{\omega}\times\mathbf{r}=\omega r\sin\theta\,\hat{\boldsymbol{\varphi}}
\quad(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}).
\]

**Cilíndricas** \((\rho,\varphi,z)\) con \(\rho=\sqrt{x^2+y^2}\) (notación Jackson):

\[
\mathbf{r}=\rho\hat{\boldsymbol{\rho}}+z\hat{\mathbf{z}},
\qquad
\boldsymbol{\omega}\times\mathbf{r}=\omega\rho\,\hat{\boldsymbol{\varphi}}
\quad(\boldsymbol{\omega}=\omega\hat{\mathbf{z}},\ \text{en }z=0).
\]

---

## 4. Setup

**Datos**

- \(\sigma\) uniforme (constante en el tiempo y sobre la superficie/disco).
- \(\boldsymbol{\omega}\) constante.
- Esfera: radio \(R\). Disco: radio \(R\), espesor \(\to 0\).

**Hipótesis**

- Rotación rígida.
- No hay carga de volumen fuera de la superficie/disco.
- El disco está en \(z=0\), centrado en el origen; el eje de rotación es \(z\).

**Notación**

| Símbolo | Significado |
|---------|-------------|
| \(R\) | radio de la esfera / del disco |
| \(\sigma\) | densidad superficial de carga |
| \(\omega\) | módulo de \(\boldsymbol{\omega}\) |
| \(\mathbf{K}\) | corriente superficial |
| \(\mathbf{J}\) | corriente volumétrica (con deltas) |

---

## 5. Pasos numerados

1. Escribir \(\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}\).
2. Ítem (a): restringir a \(r=R\) → \(\mathbf{K}\) → \(\mathbf{J}\) con \(\delta(r-R)\).
3. Ítem (b): restringir al disco \(z=0\), \(\rho\le R\) → \(\mathbf{K}\) → \(\mathbf{J}\) con \(\delta(z)\).
4. Chequear unidades, dirección, ceros en el eje, y carga total.

---

## 6. Desarrollo completo

### Paso 1 — velocidad en todo punto

Con \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\):

\[
\mathbf{v}(\mathbf{r})=\boldsymbol{\omega}\times\mathbf{r}.
\]

En cartesianas:

\[
\boldsymbol{\omega}\times\mathbf{r}
=
\begin{vmatrix}
\hat{\mathbf{x}}&\hat{\mathbf{y}}&\hat{\mathbf{z}}\\
0&0&\omega\\
x&y&z
\end{vmatrix}
=
\omega(-y\,\hat{\mathbf{x}}+x\,\hat{\mathbf{y}})
=
\omega\rho\,\hat{\boldsymbol{\varphi}}.
\]

(La última igualdad es la definición de \(\hat{\boldsymbol{\varphi}}\) en cilíndricas.)

---

### Paso 2 — (a) Esfera

La carga vive solo en \(r=R\):

\[
\rho(\mathbf{r})=\sigma\,\delta(r-R).
\]

Chequeo de normalización (carga total):

\[
Q=\int\rho\,dV
=\int_0^\infty\sigma\,\delta(r-R)\,r^2\,dr\int_0^\pi\sin\theta\,d\theta\int_0^{2\pi}d\varphi
=\sigma\cdot R^2\cdot 2\cdot 2\pi
=4\pi R^2\sigma.
\]

Correcto: área \(4\pi R^2\) por \(\sigma\).

Velocidad sobre la superficie (\(r=R\)):

\[
\mathbf{v}(R,\theta,\varphi)=\boldsymbol{\omega}\times\mathbf{r}\Big|_{r=R}
=\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

Corriente superficial:

\[
\mathbf{K}_a(\theta,\varphi)
=\sigma\mathbf{v}
=\sigma\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}
=\sigma\,\boldsymbol{\omega}\times\mathbf{R},
\]

donde \(\mathbf{R}=R\hat{\mathbf{r}}\) es el radio vector al punto de la esfera.

Forma volumétrica pedida por el enunciado:

\[
\mathbf{J}_a(\mathbf{r})
=\rho\mathbf{v}
=\sigma\,(\boldsymbol{\omega}\times\mathbf{r})\,\delta(r-R).
\]

Como \(\boldsymbol{\omega}\times\mathbf{r}=\omega r\sin\theta\,\hat{\boldsymbol{\varphi}}\) y la delta fuerza \(r=R\),

\[
\boxed{
\mathbf{J}_a(\mathbf{r})
=\sigma\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}\,\delta(r-R)
=\mathbf{K}_a\,\delta(r-R)
}
\]

con

\[
\boxed{
\mathbf{K}_a=\sigma\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}
=\sigma\,(\boldsymbol{\omega}\times\mathbf{R})
}.
\]

**Lectura física**

- En los polos \(\theta=0,\pi\): \(\sin\theta=0\) ⇒ \(\mathbf{K}=0\) (el punto del eje no se mueve).
- En el ecuador \(\theta=\pi/2\): \(\mathbf{K}\) máxima, \(\lvert\mathbf{K}\rvert=\sigma\omega R\).
- La corriente “corre” en círculos de latitud constante, sentido de \(\hat{\boldsymbol{\varphi}}\) (mano derecha con \(\boldsymbol{\omega}\)).

---

### Paso 3 — (b) Disco

El disco está en \(z=0\), \(0\le\rho\le R\). Espesor despreciable ⇒

\[
\rho_{\text{carga}}(\mathbf{r})
=
\begin{cases}
\sigma\,\delta(z) & \text{si }\rho\le R,\\
0 & \text{si }\rho>R.
\end{cases}
\]

Equivale a

\[
\rho_{\text{carga}}(\mathbf{r})=\sigma\,\delta(z)\,\Theta(R-\rho),
\]

donde \(\Theta\) es el escalón de Heaviside (\(\Theta(u)=1\) si \(u>0\), \(0\) si \(u<0\)).

Carga total:

\[
Q=\int\sigma\,\delta(z)\,\Theta(R-\rho)\,\rho\,d\rho\,d\varphi\,dz
=\sigma\int_0^{2\pi}d\varphi\int_0^R\rho\,d\rho
=\sigma\cdot 2\pi\cdot\frac{R^2}{2}
=\sigma\pi R^2.
\]

Correcto.

Sobre el plano del disco (\(z=0\)):

\[
\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}=\omega\rho\,\hat{\boldsymbol{\varphi}}.
\]

(No hay componente \(z\) en \(\mathbf{v}\) porque \(\boldsymbol{\omega}\parallel\hat{\mathbf{z}}\) y el punto está en \(z=0\); en general \(\boldsymbol{\omega}\times\mathbf{r}=\omega\rho\hat{\boldsymbol{\varphi}}\) para cualquier \(z\), de hecho.)

Corriente superficial (solo donde hay disco):

\[
\mathbf{K}_b(\rho,\varphi)
=
\begin{cases}
\sigma\omega\rho\,\hat{\boldsymbol{\varphi}} & \rho\le R,\\
0 & \rho>R.
\end{cases}
\]

En forma compacta:

\[
\mathbf{K}_b=\sigma\,(\boldsymbol{\omega}\times\mathbf{r})\,\Theta(R-\rho)
\Big|_{z=0}
=\sigma\omega\rho\,\hat{\boldsymbol{\varphi}}\,\Theta(R-\rho).
\]

Volumétrica:

\[
\boxed{
\mathbf{J}_b(\mathbf{r})
=\sigma\omega\rho\,\hat{\boldsymbol{\varphi}}\,\delta(z)\,\Theta(R-\rho)
=\mathbf{K}_b\,\delta(z)
}.
\]

**Lectura física**

- En el centro \(\rho=0\): \(\mathbf{K}=0\) (no se mueve).
- En el borde \(\rho=R\): \(\lvert\mathbf{K}\rvert=\sigma\omega R\) (máxima).
- Las líneas de \(\mathbf{K}\) son circunferencias concéntricas en el plano del disco.

---

### Paso 4 — forma unificada (útil para después)

En ambos casos:

\[
\mathbf{J}(\mathbf{r})=\sigma\,(\boldsymbol{\omega}\times\mathbf{r})\,\delta_S(\mathbf{r}),
\]

con \(\delta_S\) la delta de la superficie cargada (esfera o disco).  
Eso es exactamente lo que usan los problemas 4 y 5 para armar \(\mathbf{A}\) y \(\mathbf{B}\).

---

## 7. Resultado final

Con \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\):

**(a) Esfera**

\[
\mathbf{K}_a=\sigma\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}
=\sigma\,(\boldsymbol{\omega}\times\mathbf{R}),
\qquad
\mathbf{J}_a=\mathbf{K}_a\,\delta(r-R).
\]

**(b) Disco** (\(z=0\), \(\rho\le R\))

\[
\mathbf{K}_b=\sigma\omega\rho\,\hat{\boldsymbol{\varphi}}\,\Theta(R-\rho),
\qquad
\mathbf{J}_b=\mathbf{K}_b\,\delta(z).
\]

---

## 8. Chequeos

1. **Unidades:** \(\sigma\omega R\) tiene unidades \((\mathrm{C/m^2})(\mathrm{1/s})(\mathrm{m})=\mathrm{A/m}\) → \(\mathbf{K}\) OK. Con \(\delta(r-R)\) (1/m) → \(\mathbf{J}\) en A/m² OK.
2. **Carga total:** esfera \(4\pi R^2\sigma\); disco \(\pi R^2\sigma\).
3. **Eje:** \(\mathbf{K}=0\) en polos / centro, como exige \(\mathbf{v}=0\).
4. **Dirección:** solo \(\hat{\boldsymbol{\varphi}}\); no hay corriente radial ni axial.
5. **Límite disco ↔ ecuador de esfera:** en el ecuador de la esfera, \(\lvert\mathbf{K}_a\rvert=\sigma\omega R\); en el borde del disco, \(\lvert\mathbf{K}_b\rvert=\sigma\omega R\). Misma escala.

---

## 9. Errores típicos de examen

1. Escribir \(\mathbf{K}=\sigma\omega R\hat{\boldsymbol{\varphi}}\) en toda la esfera (falta el \(\sin\theta\)).
2. En el disco poner \(\mathbf{K}=\sigma\omega R\hat{\boldsymbol{\varphi}}\) constante (debe crecer con \(\rho\)).
3. Olvidar la delta al pasar de \(\mathbf{K}\) a \(\mathbf{J}\).
4. Usar \(\mathbf{v}=\omega r\) sin producto cruz (pierde dirección y el \(\sin\theta\)).
5. Confundir \(\rho\) cilíndrico con \(r\) esférico (en el disco la distancia al eje es \(\rho\)).

---

## 10. Mini-resumen

> Carga superficial que rota ⇒ \(\mathbf{K}=\sigma(\boldsymbol{\omega}\times\mathbf{r})\) sobre la superficie.  
> Esfera: \(\mathbf{K}=\sigma\omega R\sin\theta\,\hat{\varphi}\), \(\mathbf{J}=\mathbf{K}\delta(r-R)\).  
> Disco: \(\mathbf{K}=\sigma\omega\rho\,\hat{\varphi}\) (\(\rho\le R\)), \(\mathbf{J}=\mathbf{K}\delta(z)\).

---

## Siguiente paso lógico

**Problema 2** del camino corto: cilindro conductor con agujero (Ampère + superposición).
