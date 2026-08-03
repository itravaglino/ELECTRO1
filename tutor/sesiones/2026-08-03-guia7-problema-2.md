# Guía 7 — Problema 2 — ZERO TO HERO

> Camino corto: 1 → **2** → 4 → 5 → 8 → …
> Material: `Guia_7_EMI (1).pdf`
> Previo: Problema 1 (corrientes de cargas rotantes)

---

# 0. Desde cero del tema

En el Problema 1 armamos \(\mathbf{J}\) a partir de cargas que giran. Acá \(\mathbf{J}\) ya está “dada” (uniforme en un conductor), y el objetivo es **el campo \(\mathbf{B}\)**.

## ¿Qué es Ampère en la práctica?

La forma integral (magnetostática, sin \(\partial\mathbf{E}/\partial t\)):

\[
\oint_C\mathbf{B}\cdot d\mathbf{l}=\mu_0 I_{\text{enc}}.
\]

Significado: la circulación de \(\mathbf{B}\) alrededor de una curva cerrada \(C\) vale \(\mu_0\) veces la corriente neta que atraviesa cualquier superficie apoyada en \(C\).

Si hay **simetría** suficiente, esa ley fija \(\mathbf{B}\) sin integrar Biot–Savart.

## ¿Qué es superposición acá?

El agujero = “saqué un cilindro de corriente”.  
Matemáticamente:

\[
\mathbf{J}_{\text{real}}
=
\mathbf{J}_{\text{cilindro grande lleno}}
-
\mathbf{J}_{\text{cilindro del agujero}}.
\]

Como las ecuaciones de magnetostática son lineales en \(\mathbf{J}\),

\[
\mathbf{B}_{\text{real}}=\mathbf{B}_{\text{grande}}-\mathbf{B}_{\text{agujero}}.
\]

Eso es una **estrategia**, no un truco mágico: es linealidad.

## Vocabulario de este problema

| Símbolo | Qué es |
|---------|--------|
| \(a\) | radio del cilindro conductor |
| \(b\) | radio del agujero (vacío) |
| \(d\) | distancia entre ejes (\(a>b+d\): el agujero cabe adentro) |
| \(I\) | corriente total por el conductor |
| \(\mathbf{J}\) | densidad de corriente (A/m²), paralela al eje |
| \(\rho\) | distancia cilíndrica al eje que indiquemos, \(\rho=\sqrt{x^2+y^2}\) |

Geometría infinita en \(z\) (o “muy largo”): despreciamos bordes; todo es 2D en el plano transversal.

---

## 1. Qué pide

**(a)** \(\mathbf{J}\) en el material (uniforme, \(\parallel\) al eje).  
**(b)** \(\mathbf{B}\) **dentro del agujero** (Ampère + superposición).  
**(c)** \(\mathbf{B}\) **en el seno del conductor** (en el material, no en el agujero).

---

## 2. Idea central (sin cuentas)

1. Área efectiva de corriente = \(\pi a^2-\pi b^2\) ⇒ \(\lvert\mathbf{J}\rvert=I/(\pi(a^2-b^2))\).
2. Reemplazar el sistema por: cilindro lleno de radio \(a\) con esa \(\mathbf{J}\), **menos** cilindro de radio \(b\) con la misma \(\mathbf{J}\).
3. Ampère en un cilindro infinito con \(\mathbf{J}\) uniforme da \(\mathbf{B}\) dentro y fuera en una línea.
4. Restar vectorialmente. En el agujero la resta da un campo **uniforme**.

---

## 3. Herramientas previas

### 3.1 Ley de Ampère (integral)

\[
\oint_C\mathbf{B}\cdot d\mathbf{l}=\mu_0 I_{\text{enc}}.
\]

Vale en el vacío (acá \(\mu=\mu_0\) también en el conductor).

### 3.2 Cilindro infinito con \(\mathbf{J}=J\hat{\mathbf{z}}\) uniforme en \(\rho<R\)

Simetría: \(\mathbf{B}\) es azimutal, \(\mathbf{B}=B_\varphi(\rho)\hat{\boldsymbol{\varphi}}\), y \(\lvert\mathbf{B}\rvert\) solo depende de \(\rho\) al eje.

Curva de Ampère: circunferencia de radio \(\rho\) centrada en el eje.

- \(\oint\mathbf{B}\cdot d\mathbf{l}=B_\varphi\cdot 2\pi\rho\).
- \(I_{\text{enc}}=J\cdot\pi\rho^2\) si \(\rho<R\); \(I_{\text{enc}}=J\cdot\pi R^2\) si \(\rho>R\).

**Dentro** (\(\rho<R\)):

\[
B_\varphi\cdot 2\pi\rho=\mu_0 J\pi\rho^2
\quad\Rightarrow\quad
B_\varphi=\frac{\mu_0 J\rho}{2}
\quad\Rightarrow\quad
\mathbf{B}=\frac{\mu_0}{2}J\rho\,\hat{\boldsymbol{\varphi}}.
\]

Forma vectorial (misma información, más cómoda para restar):

\[
\boxed{
\mathbf{B}_{\text{int}}=\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
}
\]

donde \(\boldsymbol{\rho}\) es el vector perpendicular del eje al punto (en el plano \(xy\)).  
Chequeo: \(\mathbf{J}=J\hat{\mathbf{z}}\), \(\boldsymbol{\rho}=\rho\hat{\boldsymbol{\rho}}\) ⇒ \(\mathbf{J}\times\boldsymbol{\rho}=J\rho\hat{\boldsymbol{\varphi}}\). OK.

**Fuera** (\(\rho>R\)):

\[
B_\varphi\cdot 2\pi\rho=\mu_0 J\pi R^2
\quad\Rightarrow\quad
B_\varphi=\frac{\mu_0 J R^2}{2\rho}
\quad\Rightarrow\quad
\mathbf{B}_{\text{ext}}=\frac{\mu_0}{2}\,\frac{R^2}{\rho^2}\,\mathbf{J}\times\boldsymbol{\rho}.
\]

(Equivale a un hilo con corriente \(I_{\text{cil}}=J\pi R^2\): \(B=\mu_0 I_{\text{cil}}/(2\pi\rho)\).)

### 3.3 Superposición lineal

Si \(\mathbf{J}=\mathbf{J}_1+\mathbf{J}_2\), entonces \(\mathbf{B}=\mathbf{B}_1+\mathbf{B}_2\).  
Acá \(\mathbf{J}_2=-\mathbf{J}\) en el agujero (corriente “negativa” = restar).

---

## 4. Setup

**Diagrama mental**

- Eje del conductor grande: \(O\).
- Eje del agujero: \(O'\), con \(\overrightarrow{OO'}=\mathbf{d}\), \(\lvert\mathbf{d}\rvert=d\), y \(a>b+d\).
- Punto de observación \(P\):
  - \(\boldsymbol{\rho}=\overrightarrow{OP}\) (vector en el plano transversal desde \(O\)),
  - \(\boldsymbol{\rho}'=\overrightarrow{O'P}\) (desde \(O'\)),
  - relación: \(\boldsymbol{\rho}=\mathbf{d}+\boldsymbol{\rho}'\).

**Hipótesis**

- Cilindros infinitos (o muy largos).
- \(\mathbf{J}\) uniforme en el material, \(\mathbf{J}=\mathbf{0}\) en el agujero.
- \(\mu=\mu_0\) en todos lados.

**Datos**

\(a,b,d,I,\mu_0\).

---

## 5. Pasos numerados

1. Área efectiva → \(\mathbf{J}\) (ítem a).
2. Ampère: \(\mathbf{B}\) de un cilindro lleno uniforme (dentro/fuera).
3. Superposición: \(\mathbf{B}=\mathbf{B}_a-\mathbf{B}_b\).
4. Especializar al agujero (ítem b).
5. Especializar al material (ítem c).

---

## 6. Desarrollo completo

### Paso 1 — (a) Densidad de corriente

Corriente total \(I\) repartida en el área del material:

\[
A=\pi a^2-\pi b^2=\pi(a^2-b^2).
\]

Uniforme y paralela al eje (tomamos \(\hat{\mathbf{z}}\)):

\[
\boxed{
\mathbf{J}=\frac{I}{\pi(a^2-b^2)}\,\hat{\mathbf{z}}
}
\]

(Si el sentido de \(I\) fuera \(-z\), cambia el signo; el enunciado no fija sentido, así que esta elección es la convencional.)

Chequeo: \(\int\mathbf{J}\cdot d\mathbf{A}=J\cdot\pi(a^2-b^2)=I\). OK.

---

### Paso 2 — Campos auxiliares \(\mathbf{B}_a\) y \(\mathbf{B}_b\)

**Cilindro \(a\)** con densidad \(+\mathbf{J}\) en todo \(\rho<a\):

\[
\mathbf{B}_a(P)=
\begin{cases}
\dfrac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho} & \text{si }\rho<a,\\[8pt]
\dfrac{\mu_0}{2}\,\dfrac{a^2}{\rho^2}\,\mathbf{J}\times\boldsymbol{\rho} & \text{si }\rho>a.
\end{cases}
\]

**Cilindro \(b\)** (ficticio del agujero) con la misma \(+\mathbf{J}\) en \(\rho'<b\):

\[
\mathbf{B}_b(P)=
\begin{cases}
\dfrac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}' & \text{si }\rho'<b,\\[8pt]
\dfrac{\mu_0}{2}\,\dfrac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}' & \text{si }\rho'>b.
\end{cases}
\]

El sistema real es “grande menos agujero”:

\[
\mathbf{B}(P)=\mathbf{B}_a(P)-\mathbf{B}_b(P).
\]

---

### Paso 3 — (b) \(\mathbf{B}\) en el agujero

Dentro del agujero: \(\rho'<b\), y además (porque el agujero está dentro del grande) \(\rho<a\).

Entonces usamos las fórmulas **interiores** de ambos:

\[
\mathbf{B}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}'
=
\frac{\mu_0}{2}\,\mathbf{J}\times(\boldsymbol{\rho}-\boldsymbol{\rho}').
\]

Pero \(\boldsymbol{\rho}-\boldsymbol{\rho}'=\mathbf{d}\) (constante: el vector entre ejes).

Por lo tanto

\[
\boxed{
\mathbf{B}_{\text{agujero}}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\mathbf{d}
=
\frac{\mu_0 I}{2\pi(a^2-b^2)}\,\hat{\mathbf{z}}\times\mathbf{d}
}
\]

**Lectura física**

- \(\mathbf{B}\) es **uniforme** en todo el agujero (no depende de \(P\)).
- Dirección: perpendicular a \(\mathbf{d}\) y a la corriente (mano derecha: \(\hat{\mathbf{z}}\times\mathbf{d}\)).
- Si \(d=0\) (agujero centrado): \(\mathbf{B}=\mathbf{0}\) en el agujero. Tiene sentido por simetría azimutal.

Módulo:

\[
\lvert\mathbf{B}_{\text{agujero}}\rvert
=
\frac{\mu_0 I\,d}{2\pi(a^2-b^2)}.
\]

---

### Paso 4 — (c) \(\mathbf{B}\) en el seno del conductor

“Seno del conductor” = puntos del **material**: \(\rho<a\) y \(\rho'>b\).

- Para el grande: seguimos **adentro** ⇒ \(\mathbf{B}_a=\dfrac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}\).
- Para el ficticio del agujero: estamos **afuera** del cilindro \(b\) ⇒

\[
\mathbf{B}_b=\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'.
\]

Restando:

\[
\boxed{
\mathbf{B}_{\text{conductor}}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'
}
\]

Con \(\mathbf{J}=\dfrac{I}{\pi(a^2-b^2)}\hat{\mathbf{z}}\) y \(\boldsymbol{\rho}=\mathbf{d}+\boldsymbol{\rho}'\):

\[
\mathbf{B}_{\text{conductor}}
=
\frac{\mu_0 I}{2\pi(a^2-b^2)}
\left[
\hat{\mathbf{z}}\times\boldsymbol{\rho}
-
\frac{b^2}{\rho'^2}\,\hat{\mathbf{z}}\times\boldsymbol{\rho}'
\right].
\]

**Continuidad en el borde del agujero**

En \(\rho'=b\) (desde el material), \(\dfrac{b^2}{\rho'^2}=1\), así que

\[
\mathbf{B}
\to
\frac{\mu_0}{2}\mathbf{J}\times(\boldsymbol{\rho}-\boldsymbol{\rho}')
=
\frac{\mu_0}{2}\mathbf{J}\times\mathbf{d},
\]

igual que adentro del agujero. Las componentes tangenciales de \(\mathbf{B}\) coinciden (no hay \(\mathbf{K}\) libre en la pared del agujero). Chequeo de consistencia OK.

---

### Paso 5 — (opcional, útil) Fuera de todo el cilindro

No lo pide, pero cierra el mapa: \(\rho>a\) (y entonces automáticamente \(\rho'>b\)).

\[
\mathbf{B}_{\text{ext}}
=
\frac{\mu_0}{2}\,\frac{a^2}{\rho^2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'.
\]

A distancias grandes, el sistema se ve como un hilo con corriente \(I\): \(B\sim\mu_0 I/(2\pi\rho)\).

---

## 7. Resultado final

\[
\mathbf{J}=\frac{I}{\pi(a^2-b^2)}\,\hat{\mathbf{z}}.
\]

\[
\mathbf{B}_{\text{agujero}}
=\frac{\mu_0}{2}\,\mathbf{J}\times\mathbf{d}
=\frac{\mu_0 I\,d}{2\pi(a^2-b^2)}
\quad\text{(uniforme; dirección \(\hat{\mathbf{z}}\times\hat{\mathbf{d}}\))}.
\]

\[
\mathbf{B}_{\text{conductor}}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'.
\]

---

## 8. Chequeos

1. \(d=0\): \(\mathbf{B}_{\text{agujero}}=\mathbf{0}\); en el material \(\mathbf{B}=\dfrac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}\bigl(1-\dfrac{b^2}{\rho^2}\bigr)\) (agujero coaxial clásico).
2. \(b\to 0\): agujero desaparece ⇒ \(\mathbf{J}\to I/(\pi a^2)\) y \(\mathbf{B}_{\text{int}}\to(\mu_0/2)\mathbf{J}\times\boldsymbol{\rho}\).
3. Continuidad de \(\mathbf{B}\) al cruzar \(\rho'=b\).
4. Unidades: \(\mu_0 J d\) tiene unidades de tesla.

---

## 9. Errores típicos de examen

1. Usar área \(\pi a^2\) en vez de \(\pi(a^2-b^2)\) para \(\mathbf{J}\).
2. En el agujero restar mal: usar fórmula **exterior** del cilindro \(b\).
3. Decir que \(\mathbf{B}\) en el agujero “sigue círculos” (en realidad es **uniforme** si \(d\neq 0\)).
4. Olvidar que \(\boldsymbol{\rho}\) y \(\boldsymbol{\rho}'\) se miden desde **ejes distintos**.
5. Confundir \(\rho\) (cilíndrico al eje \(O\)) con la coordenada esférica \(r\).

---

## 10. Mini-resumen

> \(\mathbf{J}=I/[\pi(a^2-b^2)]\,\hat z\).  
> Superposición: lleno \(a\) menos lleno \(b\).  
> En el agujero: \(\mathbf{B}=(\mu_0/2)\mathbf{J}\times\mathbf{d}\) **uniforme**.  
> En el material: \(\mathbf{B}=(\mu_0/2)\mathbf{J}\times\boldsymbol{\rho}-(\mu_0/2)(b^2/\rho'^2)\mathbf{J}\times\boldsymbol{\rho}'\).

---

## Siguiente paso lógico

**Problema 4** del camino corto: disco cargado rotante → \(\mathbf{B}\) en el eje y lejos (multipolo).
