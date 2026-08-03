# Guía 7 — Problema 4 — ZERO TO HERO (desde absolutamente cero)

> Pedido: desarrollo completo desde cero, misma forma que el Problema 2.
> Material: `Guia_7_EMI (1).pdf`
> Camino: 1 → 2 → **4** → 5 → 8 → …
> Previo útil: Problema 1 (ítem b) — ya sabemos \(\mathbf{K}\) del disco.

---

# 0. Desde cero del tema

## 0.1 ¿Qué está pasando?

Tenés un **disco plano** (como un CD), de radio \(R\), con carga total \(Q\) repartida **de manera uniforme** sobre su superficie. El disco **gira** alrededor del eje que pasa por su centro y es perpendicular al disco, con velocidad angular constante \(\omega\).

Como la carga se mueve, hay **corriente**. Esa corriente produce campo magnético \(\mathbf{B}\).

El enunciado pide \(\mathbf{B}\) en dos regímenes distintos:

- **(a)** exactamente sobre el **eje** de rotación (donde el cálculo es manejable);
- **(b)** en un punto cualquiera, pero **muy muy lejos** del disco (donde el disco “se ve” como un dipolo magnético);
- **(c)** comparar (a) con (b) en la zona donde ambos valen (eje, lejos).

## 0.2 Vocabulario mínimo

| Símbolo | Qué es | Unidad |
|---------|--------|--------|
| \(Q\) | carga total del disco | C |
| \(R\) | radio del disco | m |
| \(\sigma\) | densidad superficial de carga (uniforme) | C/m² |
| \(\boldsymbol{\omega}\) | velocidad angular (eje + sentido + módulo \(\omega\)) | rad/s |
| \(\mathbf{v}\) | velocidad de un puntito del disco | m/s |
| \(\mathbf{K}\) | densidad superficial de corriente | A/m |
| \(\mathbf{B}\) | campo de inducción magnética | T |
| \(\mu_0\) | permeabilidad del vacío | T·m/A |
| \(\rho=\sqrt{x^2+y^2}\) | distancia al eje \(z\) (Jackson) | m |
| \(r=\lvert\mathbf{r}\rvert\) | distancia al origen (esférico) | m |
| \(\mathbf{m}\) | momento dipolar magnético | A·m² |

## 0.3 De carga quieta a corriente (repaso del Prob. 1, desde cero)

Densidad superficial uniforme:

\[
\sigma=\frac{Q}{\text{área}}=\frac{Q}{\pi R^2}.
\]

El disco está en el plano \(z=0\), centrado en el origen. Elegimos

\[
\boldsymbol{\omega}=\omega\,\hat{\mathbf{z}}.
\]

Un punto a distancia \(\rho\) del eje tiene velocidad de rotación rígida

\[
\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}=\omega\rho\,\hat{\boldsymbol{\varphi}}.
\]

(En el plano del disco \(z=0\), \(\mathbf{r}=\rho\hat{\boldsymbol{\rho}}\).)

Corriente superficial:

\[
\mathbf{K}=\sigma\mathbf{v}=\sigma\omega\rho\,\hat{\boldsymbol{\varphi}}
\qquad(0\le\rho\le R).
\]

Intuición: en el centro \(\rho=0\) no se mueve \(\Rightarrow\mathbf{K}=0\); en el borde \(\rho=R\) va más rápido \(\Rightarrow\lvert\mathbf{K}\rvert\) máxima.

## 0.4 ¿Qué herramienta usamos para \(\mathbf{B}\)?

**Ley de Biot–Savart** (forma para corriente superficial):

\[
\mathbf{B}(\mathbf{r})
=
\frac{\mu_0}{4\pi}
\int
\frac{\mathbf{K}(\mathbf{r}')\times(\mathbf{r}-\mathbf{r}')}{\lvert\mathbf{r}-\mathbf{r}'\rvert^3}\,da'.
\]

De dónde sale (idea): es la suma (integral) de los campitos \(d\mathbf{B}\) que produce cada pedacito de corriente, análoga a Coulomb pero con el producto cruz que da la dirección de \(\mathbf{B}\).

En el eje, en vez de integrar Biot–Savart “a lo bruto”, es más limpio pensar el disco como **muchos anillos** concéntricos (espiras) y usar el \(\mathbf{B}\) de una espira en su eje — que también sale de Biot–Savart, una vez.

Muy lejos, no hace falta la integral exacta: el primer término no nulo de la expansión multipolar es el **dipolo magnético**.

## 0.5 Campo de una espira circular en el eje (derivación breve)

Espira de radio \(a\), corriente \(I\), en el plano \(z=0\). Punto sobre el eje: \(\mathbf{r}=z\hat{\mathbf{z}}\).

Por Biot–Savart, cada \(Id\mathbf{l}'\) aporta \(d\mathbf{B}\). Por simetría solo sobrevive la componente \(z\).

Geometría: \(\lvert\mathbf{r}-\mathbf{r}'\rvert=\sqrt{a^2+z^2}\) constante sobre la espira. El ángulo entre \(Id\mathbf{l}'\times(\mathbf{r}-\mathbf{r}')\) y el eje da un factor \(a/\sqrt{a^2+z^2}\) (el seno del ángulo entre el radio al punto y el plano).

Resultado (después de integrar \(0\to 2\pi a\)):

\[
\boxed{
B_z^{\text{espira}}(z)
=
\frac{\mu_0}{2}
\frac{I a^2}{(a^2+z^2)^{3/2}}
}
\]

Dirección: si \(I\) va en \(+\hat{\boldsymbol{\varphi}}\) (mano derecha con \(+\hat{\mathbf{z}}\)), entonces \(B_z>0\) en el eje (apunta hacia \(+\hat{\mathbf{z}}\) a ambos lados; \(B_z(z)\) es función **par**).

Chequeo en el centro \(z=0\): \(B_z=\mu_0 I/(2a)\), fórmula clásica.

---

# Enunciado reformulado

Disco circular radio \(R\), carga total \(Q\) homogénea, rota con \(\omega\) alrededor del eje perpendicular por el centro. Hallar \(\mathbf{B}\):

**(a)** en un punto arbitrario del eje de rotación;

**(b)** en un punto arbitrario del espacio, muy lejos del disco;

**(c)** comparar (a) y (b) donde se pueda.

---

## 1. Qué pide

| Ítem | En criollo |
|------|------------|
| (a) | Fórmula exacta de \(\mathbf{B}\) sobre el eje \(z\). |
| (b) | Fórmula aproximada de \(\mathbf{B}\) en todo el espacio cuando \(r\gg R\). |
| (c) | ¿Coincide (a) con (b) si me voy lejos **sobre el eje**? |

---

## 2. Idea central (sin cuentas)

1. \(\sigma=Q/(\pi R^2)\), \(\mathbf{K}=\sigma\omega\rho\hat{\boldsymbol{\varphi}}\).
2. Cortar el disco en anillos: cada anillo es una espira con corriente \(dI=\sigma\omega\rho'\,d\rho'\).
3. Sumar \(dB_z\) de cada espira en el eje ⇒ integral ⇒ (a).
4. Muy lejos: calcular el momento \(\mathbf{m}\) del disco y usar el campo dipolar ⇒ (b).
5. Expandir (a) para \(\lvert z\rvert\gg R\) y ver que coincide con (b) sobre el eje ⇒ (c).

---

## 3. Herramientas previas

### 3.1 Anillo = espira infinitesimal

Entre \(\rho'\) y \(\rho'+d\rho'\) hay una corona de ancho \(d\rho'\).

\(\mathbf{K}\) es tangencial (\(\hat{\boldsymbol{\varphi}}\)). La corriente que “circula” en esa corona es la que atraviesa un corte radial de longitud \(d\rho'\):

\[
dI = K\,d\rho' = \sigma\omega\rho'\,d\rho'.
\]

(Unidades: \((\mathrm{A/m})\cdot\mathrm{m}=\mathrm{A}\). OK.)

Esa corona es una espira de radio \(a=\rho'\) y corriente \(dI\).

### 3.2 Momento dipolar magnético de corrientes

Para una distribución localizada de corriente,

\[
\mathbf{m}
=
\frac12\int\mathbf{r}'\times\mathbf{J}(\mathbf{r}')\,dV'.
\]

Si la corriente es solo superficial,

\[
\mathbf{m}
=
\frac12\int\mathbf{r}'\times\mathbf{K}(\mathbf{r}')\,da'.
\]

Para una espira plana de área \(A\) y corriente \(I\), con normal \(\hat{\mathbf{n}}\) (mano derecha):

\[
\mathbf{m}=I A\,\hat{\mathbf{n}}.
\]

Campo de un dipolo en el vacío (lejos):

\[
\boxed{
\mathbf{B}_{\text{dip}}(\mathbf{r})
=
\frac{\mu_0}{4\pi}
\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}
}
\]

Sobre el eje de \(\mathbf{m}=m\hat{\mathbf{z}}\), en \(\mathbf{r}=z\hat{\mathbf{z}}\) con \(z>0\):

\[
\mathbf{B}_{\text{dip}}
=
\frac{\mu_0}{4\pi}\frac{2m}{z^3}\,\hat{\mathbf{z}}
=
\frac{\mu_0 m}{2\pi z^3}\,\hat{\mathbf{z}}.
\]

---

## 4. Setup

- Disco en \(z=0\), \(0\le\rho\le R\).
- \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\), \(Q>0\) ⇒ \(\sigma>0\) ⇒ \(\mathbf{K}\) en \(+\hat{\boldsymbol{\varphi}}\) ⇒ \(\mathbf{m}\) en \(+\hat{\mathbf{z}}\).
- Punto del eje: \(\mathbf{r}=z\hat{\mathbf{z}}\) ( \(z\) puede ser positivo o negativo).
- Punto lejano: \(r=\lvert\mathbf{r}\rvert\gg R\).

---

## 5. Pasos numerados

1. Escribir \(\sigma\) y \(\mathbf{K}\).
2. Anillos \(dI\) → \(dB_z\) en el eje → integrar (a).
3. Calcular \(\mathbf{m}\) del disco.
4. Escribir \(\mathbf{B}\) dipolar (b).
5. Expandir (a) para \(\lvert z\rvert\gg R\) y comparar (c).

---

## 6. Desarrollo completo

### Paso 1 — \(\sigma\) y \(\mathbf{K}\)

\[
\sigma=\frac{Q}{\pi R^2},
\qquad
\mathbf{K}(\rho)=\sigma\omega\rho\,\hat{\boldsymbol{\varphi}}
\quad(0\le\rho\le R).
\]

---

### Paso 2 — (a) \(\mathbf{B}\) en el eje, desde cero

Corona \(\rho'\to\rho'+d\rho'\):

\[
dI=\sigma\omega\rho'\,d\rho'.
\]

Campo en el eje de esa espira (fórmula de la sección 0.5, con \(a=\rho'\), \(I\to dI\)):

\[
dB_z
=
\frac{\mu_0}{2}
\frac{(\sigma\omega\rho'\,d\rho')\,(\rho')^2}{(\rho'^2+z^2)^{3/2}}
=
\frac{\mu_0\sigma\omega}{2}
\frac{\rho'^3\,d\rho'}{(\rho'^2+z^2)^{3/2}}.
\]

Las componentes transversales se cancelan por simetría (cada \(d\mathbf{B}_\perp\) de un lado se anula con el opuesto). Por lo tanto

\[
\mathbf{B}(0,0,z)=B_z(z)\,\hat{\mathbf{z}},
\]

con

\[
B_z(z)
=
\frac{\mu_0\sigma\omega}{2}
\int_0^R
\frac{\rho'^3\,d\rho'}{(\rho'^2+z^2)^{3/2}}.
\]

#### Cómo se hace la integral (sin saltos)

Queremos

\[
I(z)=\int_0^R\frac{\rho'^3\,d\rho'}{(\rho'^2+z^2)^{3/2}}.
\]

Cambio: \(u=\rho'^2+z^2\), entonces \(du=2\rho'\,d\rho'\), y \(\rho'^2=u-z^2\).

Pero el numerador es \(\rho'^3\,d\rho'=\rho'^2\cdot(\rho'\,d\rho')=(u-z^2)\,(du/2)\).

Más directo: verificar por derivación que

\[
\frac{d}{d\rho'}
\left[
\frac{\rho'^2+2z^2}{\sqrt{\rho'^2+z^2}}
\right]
=
\frac{\rho'^3}{(\rho'^2+z^2)^{3/2}}.
\]

Cuenta:

\begin{align}
\frac{d}{d\rho'}
\left[
\frac{\rho'^2+2z^2}{(\rho'^2+z^2)^{1/2}}
\right]
&=
\frac{
2\rho'(\rho'^2+z^2)^{1/2}
-
(\rho'^2+2z^2)\cdot\tfrac12(\rho'^2+z^2)^{-1/2}\cdot 2\rho'
}{\rho'^2+z^2}
\\
&=
\frac{
\rho'\bigl[2(\rho'^2+z^2)-(\rho'^2+2z^2)\bigr]
}{(\rho'^2+z^2)^{3/2}}
\\
&=
\frac{\rho'(\rho'^2)}{(\rho'^2+z^2)^{3/2}}
=
\frac{\rho'^3}{(\rho'^2+z^2)^{3/2}}.
\end{align}

Sí. Entonces

\begin{align}
I(z)
&=
\left[
\frac{\rho'^2+2z^2}{\sqrt{\rho'^2+z^2}}
\right]_0^R
\\
&=
\frac{R^2+2z^2}{\sqrt{R^2+z^2}}
-
\frac{0+2z^2}{\sqrt{z^2}}
\\
&=
\frac{R^2+2z^2}{\sqrt{R^2+z^2}}
-
2\lvert z\rvert.
\end{align}

(Usamos \(\sqrt{z^2}=\lvert z\rvert\) para que \(B_z\) sea par en \(z\), como debe ser.)

Por lo tanto

\[
B_z(z)
=
\frac{\mu_0\sigma\omega}{2}
\left[
\frac{R^2+2z^2}{\sqrt{R^2+z^2}}
-
2\lvert z\rvert
\right].
\]

Con \(\sigma=Q/(\pi R^2)\):

\[
\boxed{
\mathbf{B}(0,0,z)
=
\frac{\mu_0 Q\omega}{2\pi R^2}
\left[
\frac{R^2+2z^2}{\sqrt{R^2+z^2}}
-
2\lvert z\rvert
\right]
\hat{\mathbf{z}}
}
\]

**Chequeos parciales**

- En el centro \(z=0\):
  \[
  B_z(0)=\frac{\mu_0\sigma\omega}{2}\,R=\frac{\mu_0 Q\omega}{2\pi R}.
  \]
- Signo: \(Q>0\), \(\omega>0\) ⇒ \(B_z>0\) (mano derecha).
- Paridad: \(B_z(-z)=B_z(z)\).

---

### Paso 3 — Momento dipolar \(\mathbf{m}\) del disco

**Método 1 — por anillos**

Anillo: \(dI=\sigma\omega\rho'\,d\rho'\), área \(\pi\rho'^2\), normal \(\hat{\mathbf{z}}\):

\[
d\mathbf{m}=dI\cdot(\pi\rho'^2)\,\hat{\mathbf{z}}
=\pi\sigma\omega\rho'^3\,d\rho'\,\hat{\mathbf{z}}.
\]

Integrando:

\[
\mathbf{m}
=
\pi\sigma\omega\hat{\mathbf{z}}
\int_0^R\rho'^3\,d\rho'
=
\pi\sigma\omega\hat{\mathbf{z}}\cdot\frac{R^4}{4}
=
\frac{\pi\sigma\omega R^4}{4}\,\hat{\mathbf{z}}.
\]

**Método 2 — fórmula integral** (misma respuesta)

\[
\mathbf{r}'\times\mathbf{K}
=
(\rho'\hat{\boldsymbol{\rho}})\times(\sigma\omega\rho'\hat{\boldsymbol{\varphi}})
=
\sigma\omega\rho'^2\hat{\mathbf{z}},
\]

\[
\mathbf{m}
=
\frac12\int\sigma\omega\rho'^2\hat{\mathbf{z}}\,da'
=
\frac12\sigma\omega\hat{\mathbf{z}}
\int_0^{2\pi}\!\!d\varphi'
\int_0^R\rho'^3\,d\rho'
=
\frac12\sigma\omega\cdot 2\pi\cdot\frac{R^4}{4}\,\hat{\mathbf{z}}
=
\frac{\pi\sigma\omega R^4}{4}\,\hat{\mathbf{z}}.
\]

Con \(\sigma=Q/(\pi R^2)\):

\[
\boxed{
\mathbf{m}
=
\frac{Q\omega R^2}{4}\,\hat{\mathbf{z}}
}
\]

---

### Paso 4 — (b) \(\mathbf{B}\) muy lejos (todo el espacio)

Si \(r\gg R\), el disco es una distribución localizada. El monopolo magnético no existe (\(\nabla\cdot\mathbf{B}=0\)). El primer término es el dipolo:

\[
\boxed{
\mathbf{B}(\mathbf{r})
\simeq
\frac{\mu_0}{4\pi}
\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}
,
\qquad
\mathbf{m}=\frac{Q\omega R^2}{4}\,\hat{\mathbf{z}}
,
\quad r\gg R.
}
\]

Explícito en cartesianas/esféricas (con \(\mathbf{m}=m\hat{\mathbf{z}}\), \(m=Q\omega R^2/4\)):

\[
\mathbf{B}(\mathbf{r})
\simeq
\frac{\mu_0 m}{4\pi r^3}
\bigl(3\cos\theta\,\hat{\mathbf{r}}-\hat{\mathbf{z}}\bigr)
=
\frac{\mu_0 Q\omega R^2}{16\pi r^3}
\bigl(3\cos\theta\,\hat{\mathbf{r}}-\hat{\mathbf{z}}\bigr).
\]

(Usamos \(\mathbf{m}\cdot\hat{\mathbf{r}}=m\cos\theta\).)

---

### Paso 5 — (c) Comparación sobre el eje, lejos

Tomá el resultado exacto (a) con \(z>0\) y \(z\gg R\).

\[
B_z(z)
=
\frac{\mu_0\sigma\omega}{2}
\left[
\frac{R^2+2z^2}{\sqrt{R^2+z^2}}-2z
\right]
=
\frac{\mu_0\sigma\omega}{2}\,z
\left[
\frac{2+R^2/z^2}{\sqrt{1+R^2/z^2}}-2
\right].
\]

Sea \(\varepsilon=R^2/z^2\ll 1\). Expandí:

\[
\frac{1}{\sqrt{1+\varepsilon}}=1-\frac{\varepsilon}{2}+\frac{3\varepsilon^2}{8}+O(\varepsilon^3),
\]

\begin{align}
(2+\varepsilon)\left(1-\frac{\varepsilon}{2}+\frac{3\varepsilon^2}{8}\right)
&=
2-\varepsilon+\frac{3\varepsilon^2}{4}
+\varepsilon-\frac{\varepsilon^2}{2}+\frac{3\varepsilon^3}{8}
\\
&=
2+\left(\frac{3}{4}-\frac{1}{2}\right)\varepsilon^2+O(\varepsilon^3)
=
2+\frac{1}{4}\varepsilon^2+O(\varepsilon^3).
\end{align}

Entonces

\[
\frac{2+\varepsilon}{\sqrt{1+\varepsilon}}-2
=
\frac{\varepsilon^2}{4}+O(\varepsilon^3)
=
\frac{R^4}{4z^4}+O\!\left(\frac{R^6}{z^6}\right).
\]

Luego

\[
B_z(z)
=
\frac{\mu_0\sigma\omega}{2}\,z\cdot\frac{R^4}{4z^4}
+O(z^{-5})
=
\frac{\mu_0\sigma\omega R^4}{8z^3}+O(z^{-5}).
\]

Ahora el dipolo (b) sobre el eje \(z>0\):

\[
B_z^{\text{dip}}
=
\frac{\mu_0 m}{2\pi z^3}
=
\frac{\mu_0}{2\pi z^3}\cdot\frac{\pi\sigma\omega R^4}{4}
=
\frac{\mu_0\sigma\omega R^4}{8z^3}.
\]

**Coinciden.** Para \(z<0\), \(\lvert z\rvert\gg R\), lo mismo con \(\lvert z\rvert^3\) en el denominador ( \(B_z\) par).

Donde **no** podés comparar directamente: fuera del eje el (a) no da fórmula cerrada sencilla; ahí solo vale (b) como aproximación lejana.

---

## 7. Resultado final

**(a)** Eje (\(x=y=0\)):

\[
\mathbf{B}(z)
=
\frac{\mu_0\sigma\omega}{2}
\left[
\frac{R^2+2z^2}{\sqrt{R^2+z^2}}-2\lvert z\rvert
\right]
\hat{\mathbf{z}}
=
\frac{\mu_0 Q\omega}{2\pi R^2}
\left[
\frac{R^2+2z^2}{\sqrt{R^2+z^2}}-2\lvert z\rvert
\right]
\hat{\mathbf{z}},
\]

con \(\sigma=Q/(\pi R^2)\).

**(b)** Muy lejos (\(r\gg R\)):

\[
\mathbf{B}(\mathbf{r})
\simeq
\frac{\mu_0}{4\pi}
\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3},
\qquad
\mathbf{m}=\frac{Q\omega R^2}{4}\,\hat{\mathbf{z}}.
\]

**(c)** Sobre el eje, \(\lvert z\rvert\gg R\): ambos dan

\[
B_z\simeq\frac{\mu_0\sigma\omega R^4}{8z^3}
=
\frac{\mu_0 Q\omega R^2}{8\pi z^3}.
\]

---

## 8. Chequeos

1. Unidades: \(\sigma\omega R\) es A/m; \(\mu_0\times(\mathrm{A/m})\) da T. OK.
2. \(z=0\): \(B_z=\mu_0\sigma\omega R/2>0\).
3. \(B_z(z)=B_z(-z)\).
4. Límite lejano del eje = dipolo. OK.
5. \(\mathbf{m}\) por dos métodos iguales.

---

## 9. Errores típicos de examen

1. Poner \(dI=\sigma\omega R\,d\rho'\) (usar el borde en vez de \(\rho'\)).
2. Olvidar \(\lvert z\rvert\) y romper la paridad de \(B_z\).
3. En el dipolo usar \(\mathbf{m}=Q\omega R^2\hat{\mathbf{z}}\) (falta el \(1/4\)).
4. Comparar (a) y (b) **cerca** del disco (el dipolo no vale).
5. Confundir \(\rho\) (cilíndrico) con \(r\) (esférico) en el far field.

---

## 10. Mini-resumen

> Disco que rota ⇒ anillos con \(dI=\sigma\omega\rho'\,d\rho'\).  
> Eje: sumar espiras ⇒ \(B_z=(\mu_0\sigma\omega/2)[(R^2+2z^2)/\sqrt{R^2+z^2}-2\lvert z\rvert]\).  
> Lejos: dipolo con \(m=Q\omega R^2/4\).  
> En el eje lejano, la expansión de (a) recupera el dipolo.

---

## Siguiente paso lógico

**Problema 5** del camino corto (ya resuelto) o **Problema 8** (imán cilíndrico permanente: \(\mathbf{H}\) y \(\mathbf{B}\)).
