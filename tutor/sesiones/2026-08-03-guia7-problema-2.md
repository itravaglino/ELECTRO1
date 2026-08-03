# Guía 7 — Problema 2 — ZERO TO HERO (desde absolutamente cero)

> Pedido: desarrollo completo desde cero, como si no se entendiera nada del tema.
> Material: `Guia_7_EMI (1).pdf`
> Camino: 1 → **2** → 4 → 5 → 8 → …

---

# 0. Desde cero del tema

## 0.1 ¿Qué está pasando en el universo de este problema?

Imaginate un cable grueso, cilíndrico, muy largo, hecho de metal. Por ese metal “corre” corriente eléctrica: cargas (electrones) que se desplazan a lo largo del cable.

Esa corriente produce un **campo magnético** \(\mathbf{B}\) alrededor (y también adentro) del cable.

Ahora viene el twist del problema: ese cable **no es macizo**. Le hicieron un **agujero cilíndrico** a lo largo, pero el agujero **no está centrado**: está corrido hacia un costado.

Preguntas del enunciado, en criollo:

1. ¿Con qué “densidad” corre la corriente en el metal que queda?
2. ¿Cómo es \(\mathbf{B}\) **dentro del agujero** (donde no hay metal ni corriente)?
3. ¿Cómo es \(\mathbf{B}\) **dentro del metal** (el “seno” del conductor)?

## 0.2 Vocabulario mínimo (cada símbolo, la primera vez)

- **Corriente \(I\):** cuánta carga atraviesa una sección transversal por segundo. Unidad: ampere \(\mathrm{A}=\mathrm{C/s}\).
- **Densidad de corriente \(\mathbf{J}\):** corriente por unidad de área perpendicular al flujo. Unidad: \(\mathrm{A/m^2}\).
  Si en un pedacito de área \(dA\) (perpendicular a la corriente) pasa corriente \(dI\), entonces
  \[
  dI=\mathbf{J}\cdot\hat{\mathbf{n}}\,dA.
  \]
  Si \(\mathbf{J}\) es uniforme y paralelo al eje, \(I=J\cdot A\), con \(A\) el área total por donde corre.
- **Campo de inducción magnética \(\mathbf{B}\):** el campo magnético. Unidad: tesla (T).
  Efecto físico básico: una carga \(q\) con velocidad \(\mathbf{v}\) siente fuerza
  \[
  \mathbf{F}=q\,\mathbf{v}\times\mathbf{B}.
  \]
- **\(\mu_0\):** permeabilidad del vacío,
  \[
  \mu_0=4\pi\times 10^{-7}\,\frac{\mathrm{T\cdot m}}{\mathrm{A}}.
  \]
  Es la constante que mide “cuánto \(\mathbf{B}\) produce una corriente” en el vacío. En este problema el conductor también tiene permeabilidad \(\mu_0\) (el enunciado lo dice).
- **Cilindro infinito (o “muy largo”):** ignoramos los extremos. Todo se repite igual a lo largo de \(z\). Los campos solo dependen de la posición en el plano transversal \(xy\).
- **Coordenadas cilíndricas** (notación Jackson):
  - \(\rho=\sqrt{x^2+y^2}\): distancia al eje \(z\) (no confundir con densidad de carga).
  - \(\varphi\): ángulo alrededor del eje.
  - \(z\): a lo largo del eje.
  - Versores: \(\hat{\boldsymbol{\rho}}\) (hacia afuera del eje), \(\hat{\boldsymbol{\varphi}}\) (tangente al círculo), \(\hat{\mathbf{z}}\) (eje).

## 0.3 Las dos leyes de Maxwell que usamos (magnetostática)

Cuando las corrientes **no cambian con el tiempo** y no hay campos eléctricos que varíen:

1. **No hay monopolos magnéticos**
   \[
   \nabla\cdot\mathbf{B}=0.
   \]
   Las líneas de \(\mathbf{B}\) no nacen ni mueren: son cerradas (o van al infinito).

2. **Ley de Ampère (forma local)**
   \[
   \nabla\times\mathbf{B}=\mu_0\mathbf{J}.
   \]
   Las corrientes “enroscan” \(\mathbf{B}\).

La forma **integral** de Ampère (la que vamos a usar a muerte) se obtiene integrando la local y aplicando el teorema de Stokes:

\[
\oint_C\mathbf{B}\cdot d\mathbf{l}
=
\mu_0\int_S\mathbf{J}\cdot d\mathbf{A}
=
\mu_0 I_{\text{enc}}.
\]

Léelo en palabras:

> La circulación de \(\mathbf{B}\) a lo largo de una curva cerrada \(C\)
> es \(\mu_0\) veces la corriente neta que atraviesa cualquier superficie \(S\) cuyo borde sea \(C\).

**Circulación** \(\oint_C\mathbf{B}\cdot d\mathbf{l}\): sumás (integrás) la componente de \(\mathbf{B}\) tangente a la curva, dando la vuelta completa.

**Corriente encerrada** \(I_{\text{enc}}\): la corriente que “atraviesa el aro” \(C\), con signo (sentido dado por la regla de la mano derecha).

## 0.4 ¿Por qué Ampère sirve para calcular \(\mathbf{B}\)?

Ampère **sola** no alcanza: es una ecuación integral. Pero si la simetría te dice de antemano la **forma** de \(\mathbf{B}\) (dirección y de qué variables depende), entonces elegís una curva \(C\) inteligente y Ampère te deja una ecuación algebraica para el módulo desconocido.

Eso es exactamente lo que haremos para un cilindro macizo con \(\mathbf{J}\) uniforme. Después, con **superposición**, armamos el cilindro con agujero.

## 0.5 ¿Qué es superposición? (y por qué es legal)

Las ecuaciones

\[
\nabla\cdot\mathbf{B}=0,
\qquad
\nabla\times\mathbf{B}=\mu_0\mathbf{J}
\]

son **lineales** en \(\mathbf{B}\) y en \(\mathbf{J}\): si \(\mathbf{J}_1\) produce \(\mathbf{B}_1\) y \(\mathbf{J}_2\) produce \(\mathbf{B}_2\), entonces \(\mathbf{J}_1+\mathbf{J}_2\) produce \(\mathbf{B}_1+\mathbf{B}_2\).

Estrategia del agujero:

> Cilindro grande **lleno** de corriente uniforme \(\mathbf{J}\)
> **menos**
> un cilindro del tamaño del agujero, también con corriente uniforme \(\mathbf{J}\).

Restar esa corriente del agujero deja: corriente \(\mathbf{J}\) en el metal y **cero** en el agujero. Exactamente el sistema real.

Por linealidad:

\[
\mathbf{B}_{\text{real}}=\mathbf{B}_{\text{grande lleno}}-\mathbf{B}_{\text{cilindro del agujero}}.
\]

No es magia: es “corriente = grande − pedazo del agujero”.

---

# Enunciado reformulado

Un **cilindro conductor** de radio \(a\) tiene un **agujero cilíndrico** de radio \(b\) (vacío). Los ejes son paralelos y están separados una distancia \(d\), con

\[
a>b+d
\]

(así el agujero cabe enterito adentro del conductor).

Permeabilidad del conductor: \(\mu_0\). Por el conductor circula una corriente total \(I\).

**(a)** Densidad de corriente \(\mathbf{J}\) en el conductor (uniforme, paralela al eje).

**(b)** Campo \(\mathbf{B}\) **en el agujero** (Ampère + superposición).

**(c)** Campo \(\mathbf{B}\) **en el seno del conductor** (en el material).

---

## 1. Qué pide

| Ítem | Pregunta concreta |
|------|-------------------|
| (a) | ¿Cuánto vale \(\mathbf{J}\) en el metal? |
| (b) | ¿Cómo es \(\mathbf{B}(x,y)\) si estoy dentro del vacío del agujero? |
| (c) | ¿Cómo es \(\mathbf{B}(x,y)\) si estoy dentro del metal? |

---

## 2. Idea central (sin cuentas)

1. La corriente \(I\) se reparte en el área de metal \(\pi a^2-\pi b^2\) ⇒ sale \(J\).
2. Reemplazo el problema por: cilindro lleno \(a\) con ese \(J\), menos cilindro lleno \(b\) con el mismo \(J\).
3. Para un cilindro lleno, Ampère + simetría dan \(\mathbf{B}\) adentro y afuera.
4. Resto vectorialmente. En el agujero la resta se simplifica a un campo **constante** (uniforme).

---

## 3. Herramientas previas (derivadas, no “conocidas”)

### 3.1 Producto cruz y dirección de \(\mathbf{B}\) alrededor de una corriente

Si la corriente va en \(+\hat{\mathbf{z}}\), la regla de la mano derecha dice que \(\mathbf{B}\) gira en el sentido de \(\hat{\boldsymbol{\varphi}}\):

\[
\mathbf{B}=B_\varphi(\rho)\,\hat{\boldsymbol{\varphi}}
\]

en un cilindro con simetría de revolución alrededor de \(z\).

Identidad que usaremos:

\[
\hat{\mathbf{z}}\times\hat{\boldsymbol{\rho}}=\hat{\boldsymbol{\varphi}}.
\]

(Porque \(\{\hat{\boldsymbol{\rho}},\hat{\boldsymbol{\varphi}},\hat{\mathbf{z}}\}\) es base derecha ortonormal.)

### 3.2 Ampère + simetría ⇒ \(\mathbf{B}\) de un cilindro infinito con \(\mathbf{J}\) uniforme

Supongamos un cilindro infinito de radio \(R\), con

\[
\mathbf{J}=
\begin{cases}
J\hat{\mathbf{z}} & \rho<R,\\
\mathbf{0} & \rho>R,
\end{cases}
\]

y \(J\) constante.

**Simetría**

- Traslación en \(z\): nada depende de \(z\).
- Rotación alrededor de \(z\): \(\lvert\mathbf{B}\rvert\) solo puede depender de \(\rho\).
- Reflexión / mano derecha: \(\mathbf{B}\) solo puede ser azimutal: \(\mathbf{B}=B_\varphi(\rho)\hat{\boldsymbol{\varphi}}\).
  (No puede haber \(B_\rho\) neta: las líneas no “salen” del eje; no puede haber \(B_z\) por simetría de inversión de corriente + reflejos.)

**Curva de Ampère:** circunferencia \(C\) de radio \(\rho\), centrada en el eje, recorrida en sentido \(\hat{\boldsymbol{\varphi}}\).

Sobre \(C\): \(\mathbf{B}\) es paralelo a \(d\mathbf{l}\) y constante en módulo, así que

\[
\oint_C\mathbf{B}\cdot d\mathbf{l}
=
B_\varphi(\rho)\oint_C dl
=
B_\varphi(\rho)\cdot 2\pi\rho.
\]

**Corriente encerrada**

La superficie \(S\) natural es el disco plano de radio \(\rho\).

- Si \(\rho<R\) (la curva está **dentro** del cilindro de corriente):

\[
I_{\text{enc}}
=
\int_S\mathbf{J}\cdot d\mathbf{A}
=
J\cdot(\text{área del disco})
=
J\cdot\pi\rho^2.
\]

- Si \(\rho>R\) (la curva está **fuera**):

\[
I_{\text{enc}}
=
J\cdot\pi R^2
\]

(solo cuenta el área donde hay \(\mathbf{J}\)).

**Caso interior \(\rho<R\)**

Ampère:

\[
B_\varphi\cdot 2\pi\rho=\mu_0\cdot J\pi\rho^2.
\]

Dividimos ambos lados por \(2\pi\rho\) (con \(\rho>0\)):

\[
B_\varphi=\frac{\mu_0 J\rho}{2}.
\]

Por lo tanto

\[
\mathbf{B}=\frac{\mu_0 J\rho}{2}\,\hat{\boldsymbol{\varphi}}.
\]

Pasamos a forma vectorial. Como \(\boldsymbol{\rho}=\rho\hat{\boldsymbol{\rho}}\) es el vector del eje al punto (en el plano),

\[
\mathbf{J}\times\boldsymbol{\rho}
=
(J\hat{\mathbf{z}})\times(\rho\hat{\boldsymbol{\rho}})
=
J\rho\,(\hat{\mathbf{z}}\times\hat{\boldsymbol{\rho}})
=
J\rho\,\hat{\boldsymbol{\varphi}}.
\]

Entonces

\[
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
=
\frac{\mu_0 J\rho}{2}\,\hat{\boldsymbol{\varphi}}.
\]

Conclusión (interior):

\[
\boxed{
\mathbf{B}_{\text{int}}(\boldsymbol{\rho})
=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
\qquad(\rho<R).
}
\]

Esta forma es oro: no hace falta elegir coordenadas; sirve para restar campos de dos ejes distintos.

**Caso exterior \(\rho>R\)**

\[
B_\varphi\cdot 2\pi\rho=\mu_0\cdot J\pi R^2
\quad\Rightarrow\quad
B_\varphi=\frac{\mu_0 J R^2}{2\rho}.
\]

Vectorialmente, como \(\mathbf{J}\times\boldsymbol{\rho}=J\rho\hat{\boldsymbol{\varphi}}\),

\[
\frac{\mu_0}{2}\,\frac{R^2}{\rho^2}\,\mathbf{J}\times\boldsymbol{\rho}
=
\frac{\mu_0 J R^2}{2\rho}\,\hat{\boldsymbol{\varphi}}.
\]

Conclusión (exterior):

\[
\boxed{
\mathbf{B}_{\text{ext}}(\boldsymbol{\rho})
=
\frac{\mu_0}{2}\,\frac{R^2}{\rho^2}\,\mathbf{J}\times\boldsymbol{\rho}
\qquad(\rho>R).
}
\]

Chequeo: \(I_{\text{cil}}=J\pi R^2\), entonces \(B_\varphi=\mu_0 I_{\text{cil}}/(2\pi\rho)\), la fórmula del hilo. OK.

### 3.3 Continuidad en \(\rho=R\)

Desde adentro: \(B_\varphi=\mu_0 JR/2\).  
Desde afuera: \(B_\varphi=\mu_0 J R^2/(2R)=\mu_0 JR/2\).  
Coincide. Bien: no hay corriente superficial en \(\rho=R\) en este modelo.

---

## 4. Setup del problema real

### 4.1 Geometría

- Eje del conductor grande: punto \(O\) en el plano transversal.
- Eje del agujero: punto \(O'\).
- Vector entre ejes:
  \[
  \mathbf{d}=\overrightarrow{OO'},
  \qquad
  \lvert\mathbf{d}\rvert=d.
  \]
- Condición \(a>b+d\): el agujero no toca el borde exterior.

Punto de observación \(P\):

\[
\boldsymbol{\rho}=\overrightarrow{OP},
\qquad
\boldsymbol{\rho}'=\overrightarrow{O'P},
\qquad
\boldsymbol{\rho}=\mathbf{d}+\boldsymbol{\rho}'.
\]

(Dibujo mental: \(O\) —\(d\)→ \(O'\) —\(\rho'\)→ \(P\); o sea \(O\) —\(\rho\)→ \(P\).)

### 4.2 Hipótesis

- Cilindros infinitos (o muy largos).
- \(\mathbf{J}\) uniforme en el metal, nula en el agujero, paralela a \(\hat{\mathbf{z}}\).
- \(\mu=\mu_0\) en todos lados.
- Magnetostática (corriente estacionaria).

### 4.3 Notación

| Símbolo | Significado |
|---------|-------------|
| \(a\) | radio exterior del conductor |
| \(b\) | radio del agujero |
| \(d\) | separación de ejes |
| \(I\) | corriente total por el metal |
| \(\mathbf{J}\) | densidad en el metal |
| \(\boldsymbol{\rho},\boldsymbol{\rho}'\) | vectores desde \(O\) y desde \(O'\) |

---

## 5. Pasos numerados

1. Calcular \(\mathbf{J}\) con el área efectiva (ítem a).
2. Escribir \(\mathbf{B}_a\) y \(\mathbf{B}_b\) de los dos cilindros ficticios.
3. Restar: \(\mathbf{B}=\mathbf{B}_a-\mathbf{B}_b\).
4. Especializar al agujero (ítem b) y simplificar.
5. Especializar al material (ítem c).
6. Chequear límites y continuidad.

---

## 6. Desarrollo completo

### Paso 1 — (a) ¿Cuál es \(\mathbf{J}\)?

La corriente total \(I\) tiene que “atravesar” toda la sección de metal.

Área del círculo grande: \(\pi a^2\).  
Área del agujero: \(\pi b^2\).  
Área efectiva:

\[
A=\pi a^2-\pi b^2=\pi(a^2-b^2).
\]

El enunciado pide \(\mathbf{J}\) **uniforme** y paralela al eje. Tomamos el sentido \(+\hat{\mathbf{z}}\) (si \(I\) fuera al revés, cambia el signo global):

\[
I=J\cdot A
\quad\Rightarrow\quad
J=\frac{I}{\pi(a^2-b^2)}.
\]

Por lo tanto

\[
\boxed{
\mathbf{J}
=
\frac{I}{\pi(a^2-b^2)}\,\hat{\mathbf{z}}
\quad\text{en el material;}
\qquad
\mathbf{J}=\mathbf{0}\text{ en el agujero.}
}
\]

**Por qué no \(\pi a^2\)?** Porque por el agujero no pasa corriente. Si usás \(\pi a^2\), inventás corriente donde no hay metal.

**Chequeo de unidades:** \(I\) en A, área en m² ⇒ \(J\) en A/m². OK.

---

### Paso 2 — Armar la superposición con cuidado

Definimos dos problemas auxiliares, **ambos con la misma densidad \(J\) del paso 1**:

**Auxiliar A:** cilindro infinito de radio \(a\), lleno, con \(\mathbf{J}=J\hat{\mathbf{z}}\) en \(\rho<a\).  
Campo: \(\mathbf{B}_a\), dado por las fórmulas de la sección 3.2 con \(R=a\) y vector \(\boldsymbol{\rho}\) desde \(O\).

**Auxiliar B:** cilindro infinito de radio \(b\), lleno, con \(\mathbf{J}=J\hat{\mathbf{z}}\) en \(\rho'<b\).  
Campo: \(\mathbf{B}_b\), mismas fórmulas con \(R=b\) y vector \(\boldsymbol{\rho}'\) desde \(O'\).

Densidad del sistema real:

\[
\mathbf{J}_{\text{real}}
=
\mathbf{J}_A-\mathbf{J}_B
=
\begin{cases}
J\hat{\mathbf{z}}-J\hat{\mathbf{z}}=\mathbf{0} & \text{dentro del agujero},\\
J\hat{\mathbf{z}}-\mathbf{0}=J\hat{\mathbf{z}} & \text{en el metal (fuera del agujero, dentro de }a\text{)},\\
\mathbf{0} & \text{fuera de todo}.
\end{cases}
\]

Perfecto: reproduce el conductor con agujero.

Por linealidad:

\[
\mathbf{B}_{\text{real}}=\mathbf{B}_a-\mathbf{B}_b.
\]

Escribamos \(\mathbf{B}_a\) y \(\mathbf{B}_b\) explícitos:

\[
\mathbf{B}_a=
\begin{cases}
\dfrac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho} & \rho<a,\\[6pt]
\dfrac{\mu_0}{2}\,\dfrac{a^2}{\rho^2}\,\mathbf{J}\times\boldsymbol{\rho} & \rho>a,
\end{cases}
\]

\[
\mathbf{B}_b=
\begin{cases}
\dfrac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}' & \rho'<b,\\[6pt]
\dfrac{\mu_0}{2}\,\dfrac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}' & \rho'>b.
\end{cases}
\]

---

### Paso 3 — (b) \(\mathbf{B}\) dentro del agujero, cuenta por cuenta

“Dentro del agujero” significa:

\[
\rho'<b.
\]

Como el agujero está contenido en el conductor grande (\(a>b+d\)), cualquier punto del agujero también cumple

\[
\rho<a.
\]

(Justificación: el punto más lejos de \(O\) dentro del agujero está a distancia \(\le d+b<a\).)

Por lo tanto, en el agujero usamos:

- fórmula **interior** de \(A\): \(\mathbf{B}_a=\dfrac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}\),
- fórmula **interior** de \(B\): \(\mathbf{B}_b=\dfrac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}'\).

Restamos:

\begin{align}
\mathbf{B}
&=
\mathbf{B}_a-\mathbf{B}_b
\\
&=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}'
\\
&=
\frac{\mu_0}{2}\,\mathbf{J}\times\bigl(\boldsymbol{\rho}-\boldsymbol{\rho}'\bigr).
\end{align}

Pero \(\boldsymbol{\rho}=\mathbf{d}+\boldsymbol{\rho}'\), luego

\[
\boldsymbol{\rho}-\boldsymbol{\rho}'=\mathbf{d}.
\]

\(\mathbf{d}\) **no depende del punto \(P\)**. Es el mismo vector en todo el agujero.

Entonces

\[
\mathbf{B}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\mathbf{d}.
\]

Sustituyendo \(\mathbf{J}=\dfrac{I}{\pi(a^2-b^2)}\hat{\mathbf{z}}\):

\[
\mathbf{B}
=
\frac{\mu_0}{2}
\cdot
\frac{I}{\pi(a^2-b^2)}
\,
\hat{\mathbf{z}}\times\mathbf{d}
=
\frac{\mu_0 I}{2\pi(a^2-b^2)}
\,
\hat{\mathbf{z}}\times\mathbf{d}.
\]

**Resultado (b)**

\[
\boxed{
\mathbf{B}_{\text{agujero}}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\mathbf{d}
=
\frac{\mu_0 I}{2\pi(a^2-b^2)}\,\hat{\mathbf{z}}\times\mathbf{d}
}
\]

**Qué significa en criollo**

- \(\mathbf{B}\) es **el mismo en todos los puntos del agujero**: campo **uniforme**.
- Su dirección es perpendicular a \(\mathbf{d}\) y a la corriente: si \(\mathbf{d}=d\hat{\mathbf{x}}\) y \(\mathbf{J}\parallel\hat{\mathbf{z}}\), entonces \(\hat{\mathbf{z}}\times\mathbf{d}=d\hat{\mathbf{y}}\), o sea \(\mathbf{B}\) apunta en \(+\hat{\mathbf{y}}\).
- Módulo:
  \[
  \lvert\mathbf{B}_{\text{agujero}}\rvert
  =
  \frac{\mu_0 I\,d}{2\pi(a^2-b^2)}.
  \]

**Caso especial \(d=0\)** (agujero centrado): \(\mathbf{d}=\mathbf{0}\) ⇒ \(\mathbf{B}=\mathbf{0}\) en todo el agujero. Tiene sentido: simetría circular perfecta; las contribuciones se cancelan.

---

### Paso 4 — (c) \(\mathbf{B}\) en el seno del conductor, cuenta por cuenta

“Seno del conductor” = punto en el **material**:

\[
\rho<a
\quad\text{y}\quad
\rho'>b.
\]

Ahora:

- Seguimos **adentro** del cilindro grande ⇒ \(\mathbf{B}_a=\dfrac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}\).
- Estamos **afuera** del cilindro ficticio del agujero ⇒ usamos la fórmula **exterior** de \(B\):

\[
\mathbf{B}_b
=
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'.
\]

Restamos:

\begin{align}
\mathbf{B}
&=
\mathbf{B}_a-\mathbf{B}_b
\\
&=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'.
\end{align}

**Resultado (c)**

\[
\boxed{
\mathbf{B}_{\text{conductor}}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'
}
\]

Con \(J\) explícito:

\[
\mathbf{B}_{\text{conductor}}
=
\frac{\mu_0 I}{2\pi(a^2-b^2)}
\left[
\hat{\mathbf{z}}\times\boldsymbol{\rho}
-
\frac{b^2}{\rho'^2}\,
\hat{\mathbf{z}}\times\boldsymbol{\rho}'
\right].
\]

Recordá siempre \(\boldsymbol{\rho}=\mathbf{d}+\boldsymbol{\rho}'\) si querés escribir todo respecto de un solo origen.

---

### Paso 5 — Continuidad en la pared del agujero (debe salir)

La pared del agujero es \(\rho'=b\). No hay corriente superficial libre ahí (solo termina el material). Entonces la componente de \(\mathbf{B}\) tangente a la pared debe ser continua.

Evaluemos \(\mathbf{B}_{\text{conductor}}\) justo afuera del agujero, en \(\rho'=b\):

\[
\frac{b^2}{\rho'^2}=1
\quad\Rightarrow\quad
\mathbf{B}
=
\frac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}'
=
\frac{\mu_0}{2}\mathbf{J}\times\mathbf{d},
\]

igual que \(\mathbf{B}_{\text{agujero}}\). Encaja. Si no coincidiera, habría un error en la resta.

---

### Paso 6 — Límites que tenés que saber hacer en el examen

**Límite \(b\to 0\)** (sin agujero):

\[
J\to\frac{I}{\pi a^2},
\qquad
\mathbf{B}_{\text{int}}\to\frac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho},
\]

el cilindro macizo clásico. El segundo término de (c) se va porque \(b^2\to 0\).

**Límite \(d=0\)** (agujero coaxial): \(\boldsymbol{\rho}'=\boldsymbol{\rho}\), y en el agujero \(\mathbf{B}=0\). En el material:

\[
\mathbf{B}
=
\frac{\mu_0}{2}\mathbf{J}\times\boldsymbol{\rho}
\left(1-\frac{b^2}{\rho^2}\right).
\]

**Fuera de todo** (\(\rho>a\); no lo piden, pero cierra el mapa):

\[
\mathbf{B}
=
\frac{\mu_0}{2}\,\frac{a^2}{\rho^2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'.
\]

A \(\rho\to\infty\), ambos términos se comportan como hilos y la corriente neta es \(J\pi(a^2-b^2)=I\), así que

\[
B\sim\frac{\mu_0 I}{2\pi\rho}.
\]

---

## 7. Resultado final (hoja limpia)

**(a)**

\[
\mathbf{J}=\frac{I}{\pi(a^2-b^2)}\,\hat{\mathbf{z}}
\quad\text{(material)},
\qquad
\mathbf{J}=\mathbf{0}
\quad\text{(agujero)}.
\]

**(b)** En el agujero (\(\rho'<b\)):

\[
\mathbf{B}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\mathbf{d}
=
\frac{\mu_0 I}{2\pi(a^2-b^2)}\,\hat{\mathbf{z}}\times\mathbf{d}
\quad\text{(uniforme)}.
\]

**(c)** En el material (\(\rho<a\), \(\rho'>b\)):

\[
\mathbf{B}
=
\frac{\mu_0}{2}\,\mathbf{J}\times\boldsymbol{\rho}
-
\frac{\mu_0}{2}\,\frac{b^2}{\rho'^2}\,\mathbf{J}\times\boldsymbol{\rho}'.
\]

---

## 8. Chequeos (lista de control)

1. Unidades de \(J\): A/m². Unidades de \(B\): \(\mu_0 J d\) → T. OK.
2. \(I_{\text{total}}=J\pi(a^2-b^2)=I\). OK.
3. \(d=0\) ⇒ \(\mathbf{B}=\mathbf{0}\) en el agujero. OK por simetría.
4. Continuidad de \(\mathbf{B}\) en \(\rho'=b\). OK.
5. \(b\to 0\) ⇒ cilindro lleno. OK.
6. Dirección: \(\mathbf{B}_{\text{agujero}}\perp\mathbf{d}\) y \(\perp\mathbf{J}\). OK (producto cruz).

---

## 9. Errores típicos de examen (y cómo no caer)

1. **Área \(\pi a^2\)** para \(J\) — olvidaste restar el agujero.
2. **En el agujero usar \(\mathbf{B}_b\) exterior** — adentro del agujero \(\rho'<b\), va la fórmula interior.
3. **Decir que \(\mathbf{B}\) en el agujero “da vueltas”** — si \(d\neq 0\), es uniforme (líneas rectas paralelas, no círculos).
4. **Medir \(\boldsymbol{\rho}\) y \(\boldsymbol{\rho}'\) desde el mismo origen** — son ejes distintos \(O\) y \(O'\).
5. **Olvidar el factor \(b^2/\rho'^2\)** en el material — sin eso no recuperás la continuidad.
6. **Confundir \(\rho\) cilíndrico con \(r\) esférico** — acá todo es cilindros; usamos \(\rho\).

---

## 10. Mini-resumen

> La corriente se reparte en el metal: \(J=I/[\pi(a^2-b^2)]\).  
> El agujero = cilindro lleno \(a\) **menos** cilindro lleno \(b\) (misma \(J\)).  
> Ampère en un lleno da \(\mathbf{B}=(\mu_0/2)\mathbf{J}\times\boldsymbol{\rho}\) adentro.  
> En el agujero la resta deja \(\mathbf{B}=(\mu_0/2)\mathbf{J}\times\mathbf{d}\), **uniforme**.  
> En el metal, el cilindro \(b\) se resta con la fórmula de afuera: factor \(b^2/\rho'^2\).

---

## Siguiente paso lógico

**Problema 4** del camino corto: disco cargado que rota → \(\mathbf{B}\) en el eje y lejos (multipolo).
