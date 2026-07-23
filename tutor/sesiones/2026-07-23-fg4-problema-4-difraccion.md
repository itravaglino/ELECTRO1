# FG4 2020 — Problema 4 — ZERO TO HERO (completo, cada fórmula explicada)

---

# PARTE A — Qué dice la consigna

## Datos

- Dos rendijas, cada una de **ancho** \(a = 0{,}020\,\mathrm{mm}\).
- Luz de sodio: \(\lambda = 589{,}6\,\mathrm{nm}\), ondas planas.
- Patrón de **Fraunhofer** (campo lejano / pantalla lejos).
- Se ven **11 franjas brillantes estrechas** dentro del **primer máximo de difracción** (lóbulo central), y la irradiancia baja al alejarse del centro.

## Qué pedir

| Ítem | Pedido |
|------|--------|
| (a) | Dibujar el patrón en pantalla a \(D = 1\,\mathrm{m}\) |
| (b) | Estimar la **separación** \(d\) entre rendijas |
| (c) | Intensidad del máximo de orden \(m=3\) **relativa** al máximo central |

---

# PARTE B — Desde cero: qué fenómenos hay

## 1. Luz como onda

La luz tiene longitud de onda \(\lambda\): distancia entre dos crestas.

Si dos ondas llegan a un mismo punto de la pantalla:

- **en fase** (cresta con cresta) → se suman → **máximo** (brillante);
- **en oposición** (cresta con valle) → se cancelan → **mínimo** (oscuro).

Eso depende de la **diferencia de camino** óptico \(\delta\) desde cada rendija hasta ese punto.

## 2. Geometría (ángulo chico)

```
  rendija 1  ----*----  rendija 2
       |    d     |
       |          |
       |     \    |
       |      \ θ |
       |       \  |
       +--------\*---- pantalla (distancia D)
                 P(y)
```

- \(d\): distancia entre **centros** de las dos rendijas.
- \(D\): distancia rendijas → pantalla (\(D=1\,\mathrm{m}\)).
- \(y\): posición en la pantalla (centro = 0).
- \(\theta\): ángulo desde el eje central hasta el punto \(P\).

Para ángulos chicos:

\[
\sin\theta \approx \tan\theta \approx \frac{y}{D}.
\]

Diferencia de camino entre las dos rendijas:

\[
\delta = d\sin\theta \approx d\,\frac{y}{D}.
\]

## 3. Interferencia de dos rendijas (como si cada una fuera “muy fina”)

### Condición de MÁXIMO de interferencia (brillante)

Las ondas llegan en fase cuando la diferencia de camino es un número entero de longitudes de onda:

\[
\boxed{\delta = m\lambda}
\quad\Leftrightarrow\quad
\boxed{d\sin\theta = m\lambda}
\quad (m = 0,\pm 1,\pm 2,\pm 3,\ldots)
\]

- \(m = 0\): centro (\(y=0\)), máximo principal.
- \(m = +1,+2,\ldots\): máximos a la derecha.
- \(m = -1,-2,\ldots\): máximos a la izquierda.

**Posición en pantalla** (ángulo chico):

\[
\boxed{y_m^{\mathrm{(máx\ interferencia)}} = m\,\frac{\lambda D}{d}}
\]

Definimos el **paso entre máximos vecinos**:

\[
\boxed{\Delta y = \frac{\lambda D}{d}}
\]

Entonces: \(y_m^{\max} = m\,\Delta y\).

Esto es **solo interferencia**: te dice **dónde** están las franjas brillantes, no cuánto brillan si hay difracción.

### Condición de MÍNIMO de interferencia (oscuro)

Se cancelan cuando la diferencia de camino es semientero de \(\lambda\):

\[
\boxed{\delta = \left(m+\tfrac12\right)\lambda}
\quad\Leftrightarrow\quad
\boxed{d\sin\theta = \left(m+\tfrac12\right)\lambda}
\quad (m = 0,\pm 1,\pm 2,\ldots)
\]

A veces se numera con otro índice; lo importante: los mínimos van **en el medio** entre dos máximos.

**Posición en pantalla:**

\[
\boxed{y^{\mathrm{(mín\ interferencia)}} = \left(m+\tfrac12\right)\Delta y}
\quad (m=0,\pm1,\pm2,\ldots)
\]

Ejemplo: entre el máximo \(m=0\) y el \(m=+1\), el mínimo está en \(y = \Delta y/2\).

## 4. Difracción de UNA rendija de ancho \(a\)

Cada rendija **no** es un punto: tiene ancho \(a\). La luz que sale de distintos puntos de **la misma** rendija también interfiere.

### MÍNIMO de difracción (una rendija)

\[
\boxed{a\sin\theta = p\lambda}
\quad (p = \pm 1,\pm 2,\pm 3,\ldots)
\]

- \(p = \pm 1\): **primer** mínimo de difracción (el más cercano al centro).
- Ahí la envolvente toca (casi) cero.

**NO** uses esta fórmula para franjas de interferencia entre las dos rendijas. Esta es solo por el **ancho** \(a\).

**Posición del primer mínimo de difracción** (ángulo chico, pantalla a \(D\)):

\[
\boxed{y_{\mathrm{mín\ difr}}^{(1)} = \pm \frac{\lambda D}{a}}
\]

Entre \(-\lambda D/a\) y \(+\lambda D/a\) está el **primer máximo / lóbulo central de difracción**.

### Forma de la intensidad de una rendija (envolvente)

\[
\boxed{I_1(\theta) = I_{1,0}\left(\frac{\sin\beta}{\beta}\right)^2}
\qquad
\boxed{\beta = \frac{\pi a\sin\theta}{\lambda}}
\]

- En el centro: \(\beta \to 0\), \(\sin\beta/\beta \to 1\) → máximo.
- Cuando \(\beta = \pi\) (o sea \(a\sin\theta=\lambda\)): \(\sin\beta=0\) → **mínimo de difracción**.

## 5. Las dos juntas (lo del problema)

Intensidad total en Fraunhofer:

\[
\boxed{
I(\theta)
=
4\,I_{1,0}
\left(\frac{\sin\beta}{\beta}\right)^2
\cos^2\!\left(\frac{\phi}{2}\right)
}
\]

con

\[
\boxed{\phi = \frac{\pi d\sin\theta}{\lambda}}
\qquad
\boxed{\beta = \frac{\pi a\sin\theta}{\lambda}}
\]

| Factor | Qué hace | Máx / mín |
|--------|----------|-----------|
| \(\cos^2(\phi/2)\) | franjas **finas** de interferencia | máx cuando \(\phi/2 = m\pi\) (o sea \(d\sin\theta=m\lambda\)); mín cuando \(\phi/2=(m+1/2)\pi\) |
| \((\sin\beta/\beta)^2\) | envolvente **ancha** de difracción | máx en centro; mín cuando \(\beta=p\pi\) (o sea \(a\sin\theta=p\lambda\)) |

Por eso el dibujo: colinas redondeadas finas (interferencia) dentro de una campana grande (difracción).

---

# PARTE C — Desarrollo del problema

## Setup numérico

\[
a = 0{,}020\,\mathrm{mm} = 2{,}0\times 10^{-5}\,\mathrm{m}
\]

\[
\lambda = 589{,}6\,\mathrm{nm} = 5{,}896\times 10^{-7}\,\mathrm{m}
\]

\[
D = 1\,\mathrm{m}
\quad\text{(para el dibujo)}
\]

\(d\) desconocida al inicio.

---

## Paso 0 — De dónde sale \(N = 2m_*-1\) (contar franjas)

Esta es la parte que más confunde. No es una fórmula mágica: es **contar** máximos de interferencia que quedan **adentro** del lóbulo central.

### Recordatorio de posiciones

Máximos de interferencia (brillantes), orden entero \(m\):

\[
\sin\theta_m = \frac{m\lambda}{d}
\quad\Leftrightarrow\quad
y_m = m\,\Delta y,\qquad \Delta y=\frac{\lambda D}{d}.
\]

Primer mínimo de difracción (borde del lóbulo), a derecha e izquierda:

\[
\sin\theta_{\mathrm{borde}} = \pm\frac{\lambda}{a}
\quad\Leftrightarrow\quad
y_{\mathrm{borde}} = \pm\frac{\lambda D}{a}.
\]

### Idea: el borde “cae” sobre un máximo

Suponemos (caso típico del enunciado) que el borde derecho del lóbulo coincide con el máximo de interferencia de orden \(m_*\):

\[
\frac{m_*\lambda}{d} = \frac{\lambda}{a}
\quad\Rightarrow\quad
m_* = \frac{d}{a}.
\]

(Entonces \(m_*\) es un número entero positivo: 2, 3, 4, 5, 6, …)

Igual a la izquierda con \(-m_*\).

### ¿Ese máximo \(m_*\) se ve?

No. Justo ahí la envolvente de difracción vale **cero**.  
Aunque la interferencia “querría” un máximo en \(m_*\), la difracción lo apaga.  
Lo mismo con \(-m_*\).

Por eso \(m = \pm m_*\) **no cuentan** como franjas visibles.

### ¿Cuáles sí se ven?

Todos los máximos **estrictamente adentro** del intervalo

\[
-y_{\mathrm{borde}} < y < +y_{\mathrm{borde}},
\]

o sea órdenes

\[
m = 0,\ \pm 1,\ \pm 2,\ \ldots,\ \pm(m_*-1).
\]

Lista explícita:

- el centro: \(m=0\) → **1** franja  
- a la derecha: \(m=+1,+2,\ldots,+(m_*-1)\) → **\(m_*-1\)** franjas  
- a la izquierda: \(m=-1,-2,\ldots,-(m_*-1)\) → **\(m_*-1\)** franjas  

Total:

\[
N = 1 + (m_*-1) + (m_*-1) = 1 + 2(m_*-1) = 2m_* - 1.
\]

Esa es la fórmula:

\[
\boxed{N = 2m_* - 1}
\]

con \(m_* = d/a\) (entero).

### Ejemplo chico (para sentir el conteo)

Supongamos \(m_*=3\) (o sea \(d=3a\)).

Órdenes:

| \(m\) | ¿Adentro del lóbulo? | ¿Se ve? |
|------|----------------------|---------|
| 0 | sí | sí |
| ±1 | sí | sí |
| ±2 | sí | sí |
| ±3 | justo en el borde (cero de difracción) | **no** |

Franjas visibles: \(0,\pm1,\pm2\) → son **5**.  
Y \(2\cdot 3 - 1 = 5\). Coincide.

### Otro ejemplo: el del problema (\(N=11\))

\[
2m_*-1 = 11 \Rightarrow m_*=6.
\]

Visibles: \(0,\pm1,\pm2,\pm3,\pm4,\pm5\) → contá:

\[
1 + 5 + 5 = 11.
\]

No visibles: \(\pm 6\) (en el cero).  
Y \(2\cdot 6 - 1 = 11\). OK.

### Dibujo mental del conteo

```
borde izq (m=-m_*)     centro      borde der (m=+m_*)
   |--- visibles ---|----|--------|--- visibles ---|
   X  ...(m*-1)...  0  ...(m*-1)...  X
   ^ no se ve                         ^ no se ve
```

Cantidad visible = todos los enteros desde \(-(m_*-1)\) hasta \(+(m_*-1)\) inclusive  
= \(2(m_*-1)+1 = 2m_*-1\).

### Por qué no es \(N=2m_*\) ni \(N=2d/a\)

- Si contaras también \(\pm m_*\), saldría \(2m_*+1\), pero esos **no brillan**.
- A veces se escribe \(N=2d/a - 1\). Es lo mismo, porque \(m_*=d/a\):
  \[
  N = 2\frac{d}{a} - 1.
  \]

### Resumen en una frase

> El lóbulo llega hasta el orden \(m_*=d/a\); ese orden se apaga; quedan los enteros de \(-(m_*-1)\) a \(+(m_*-1)\); eso son \(2m_*-1\) franjas.

---

## Paso 1 — Relacionar “11 franjas” con \(d\) (ítem b)

Queremos que el **primer mínimo de difracción** coincida con un **máximo de interferencia** de orden \(m_*\).

- Mínimo de difracción (\(p=1\)): \(\displaystyle a\sin\theta = \lambda\) → \(\sin\theta = \lambda/a\).
- Máximo de interferencia (\(m=m_*\)): \(\displaystyle d\sin\theta = m_*\lambda\) → \(\sin\theta = m_*\lambda/d\).

Igualando (mismo \(\theta\)):

\[
\frac{m_*\lambda}{d} = \frac{\lambda}{a}
\quad\Rightarrow\quad
\boxed{\frac{d}{a} = m_*}
\]

En ese caso, los máximos \(m = \pm m_*\) caen **justo** donde la difracción vale cero → **no se ven**.

Los máximos de interferencia **visibles** dentro del lóbulo central son:

\[
m = 0,\ \pm 1,\ \pm 2,\ \ldots,\ \pm(m_*-1).
\]

Cantidad:

\[
N = 1 + 2(m_*-1) = 2m_* - 1.
\]

El enunciado: \(N = 11\).

\[
2m_* - 1 = 11
\quad\Rightarrow\quad
m_* = 6
\quad\Rightarrow\quad
d = 6a.
\]

\[
d = 6 \times 0{,}020\,\mathrm{mm} = 0{,}120\,\mathrm{mm}
= 1{,}20\times 10^{-4}\,\mathrm{m}.
\]

**Resultado (b):**

\[
\boxed{d = 0{,}120\,\mathrm{mm}}
\]

**Conteo:** se ven \(m=0,\pm1,\pm2,\pm3,\pm4,\pm5\) → 11.  
Los \(m=\pm6\) están en el mínimo de difracción.

---

## Paso 2 — Dónde va cada máximo y cada mínimo (para dibujar, ítem a)

Con \(d\) ya conocido:

\[
\Delta y = \frac{\lambda D}{d}
= \frac{5{,}896\times 10^{-7}\cdot 1}{1{,}20\times 10^{-4}}
= 4{,}913\times 10^{-3}\,\mathrm{m}
\approx 0{,}491\,\mathrm{cm}.
\]

### Primer mínimo de DIFRACCIÓN (apaga el lóbulo)

\[
y_{\mathrm{mín\ difr}}^{(1)}
= \pm\frac{\lambda D}{a}
= \pm\frac{5{,}896\times 10^{-7}}{2{,}0\times 10^{-5}}
\approx \pm 2{,}95\,\mathrm{cm}.
\]

### Máximos de INTERFERENCIA (fórmula \(y = m\Delta y\))

| \(m\) | ¿Se ve? | \(y_m^{\max}\) |
|------|---------|----------------|
| 0 | sí | \(0\) |
| \(\pm 1\) | sí | \(\pm 0{,}49\,\mathrm{cm}\) |
| \(\pm 2\) | sí | \(\pm 0{,}98\,\mathrm{cm}\) |
| \(\pm 3\) | sí | \(\pm 1{,}47\,\mathrm{cm}\) |
| \(\pm 4\) | sí | \(\pm 1{,}96\,\mathrm{cm}\) |
| \(\pm 5\) | sí | \(\pm 2{,}46\,\mathrm{cm}\) |
| \(\pm 6\) | no (cero de difracción) | \(\pm 2{,}95\,\mathrm{cm}\) |

### Mínimos de INTERFERENCIA (en el medio: \(y=(m+1/2)\Delta y\))

Ejemplos a la derecha:

| Entre máximos | \(y^{\min}\) |
|---------------|--------------|
| 0 y +1 | \(+0{,}25\,\mathrm{cm}\) |
| +1 y +2 | \(+0{,}74\,\mathrm{cm}\) |
| +2 y +3 | \(+1{,}23\,\mathrm{cm}\) |
| +3 y +4 | \(+1{,}72\,\mathrm{cm}\) |
| +4 y +5 | \(+2{,}21\,\mathrm{cm}\) |
| +5 y +6 | \(+2{,}70\,\mathrm{cm}\) |

(y simétricos a la izquierda).

### Cómo dibujar (redondeado, no puntas)

```
I
^
|    *     *     *     *     *     *     *     *     *     *     *
|   * *   * *   * *   * *   * *   * *   * *   * *   * *   * *   * *
|  *   * *   * *   * *   * *   * *   * *   * *   * *   * *   * *   *
|*      *      *      *      *      *      *      *      *      *
+------+------+------+------+------+------+------+------+-------> y
     -2.5   -1.5   -0.5    0    0.5    1.5    2.5
|<-------------- lóbulo hasta ±2.95 cm (mín DIFRACCIÓN) ------------>|
 máx interferencia: 11 colinas redondas
 mín interferencia: valles entre colinas (casi a cero)
```

También podés dibujar la **envolvente punteada** que toca cero en \(\pm 2{,}95\,\mathrm{cm}\).

**Resultado (a):** ese esquema (11 máximos redondeados bajo la envolvente; primer mín. de difracción en \(\approx\pm 2{,}95\,\mathrm{cm}\)).

---

## Paso 3 — Intensidad del máximo m = 3 relativa al centro (ítem c)

En un **máximo de interferencia**, \(d\sin\theta = m\lambda\), luego \(\cos^2(\phi/2)=1\).

La intensidad relativa queda **solo** por la envolvente de difracción:

\[
\boxed{
\frac{I_m}{I_{\mathrm{centro}}}
=
\left(\frac{\sin\beta_m}{\beta_m}\right)^2
}
\]

¿Qué es \(\beta_m\) en un máximo de interferencia?

\[
\beta_m
= \frac{\pi a\sin\theta_m}{\lambda}
= \frac{\pi a}{\lambda}\cdot\frac{m\lambda}{d}
= \frac{m\pi a}{d}.
\]

Esta fórmula es para evaluar la envolvente **en la posición de un máximo de interferencia** de orden \(m\). No es una condición de máximo/mínimo nueva: es sustituir \(sin\theta = m\lambda/d\) dentro de \(\beta\).

Con \(d=6a\) y \(m=3\):

\[
\beta_3 = \frac{3\pi a}{6a} = \frac{\pi}{2}.
\]

\[
\frac{\sin(\pi/2)}{\pi/2} = \frac{1}{\pi/2} = \frac{2}{\pi}.
\]

\[
\frac{I_3}{I_{\mathrm{centro}}}
= \left(\frac{2}{\pi}\right)^2
= \frac{4}{\pi^2}
\approx 0{,}405.
\]

**Resultado (c):**

\[
\boxed{\frac{I_3}{I_{\mathrm{centro}}} = \frac{4}{\pi^2} \approx 0{,}405}
\]

Significado: el máximo \(m=3\) brilla ~40,5 % de lo que brilla el centro, porque ya está más lejos del centro y la envolvente de difracción lo atenuó.

---

# Resumen de fórmulas (chuleta)

| Fórmula | ¿Para qué? | ¿Máx o mín? |
|---------|------------|-------------|
| \(d\sin\theta = m\lambda\) | interferencia (2 rendijas) | **máximo** interferencia |
| \(d\sin\theta = (m+1/2)\lambda\) | interferencia | **mínimo** interferencia |
| \(y = m\lambda D/d\) | posición en pantalla | máximos interferencia |
| \(\Delta y = \lambda D/d\) | distancia entre máximos vecinos | — |
| \(y = (m+1/2)\Delta y\) | posición en pantalla | mínimos interferencia |
| \(a\sin\theta = p\lambda\) | difracción (1 rendija, ancho \(a\)) | **mínimo** difracción |
| \(y = \pm\lambda D/a\) | primer mín. difracción en pantalla | **mínimo** difracción |
| \(\beta=\pi a\sin\theta/\lambda\) | argumento de la envolvente | — |
| \(I\propto(\sin\beta/\beta)^2\cos^2(\phi/2)\) | intensidad total | producto de ambos efectos |
| \(N=2d/a-1\) (si \(d/a\) entero) | nº de franjas en lóbulo central | — |
| \(I_m/I_0=(\sin\beta_m/\beta_m)^2\), \(\beta_m=m\pi a/d\) | brillo de un máx. de interferencia | evalúa en un **máximo** |

---

# Resultado final

| Ítem | Respuesta |
|------|-----------|
| (a) | 11 colinas redondas bajo envolvente; mín. difracción en \(\approx\pm 2{,}95\,\mathrm{cm}\) |
| (b) | \(d=0{,}120\,\mathrm{mm}\) |
| (c) | \(4/\pi^2 \approx 0{,}405\) |

---

# Errores típicos

- Usar \(a\sin\theta=m\lambda\) para interferencia (mal: eso es **mínimo de difracción**, y el símbolo suele ser \(p\), no el \(m\) de Young).
- Confundir \(a\) (ancho) con \(d\) (separación).
- Contar \(N=2d/a\) en vez de \(2d/a-1\).
- En (c), olvidar la envolvente y decir que \(I_3=I_0\).
- Dibujar puntas en vez de lóbulos redondeados.

---

# Mini-resumen

> Interferencia (\(d\)): máx \(d\sin\theta=m\lambda\), mín \(d\sin\theta=(m+1/2)\lambda\).  
> Difracción (\(a\)): mín \(a\sin\theta=p\lambda\); lóbulo central hasta \(\pm\lambda D/a\).  
> 11 franjas ⇒ \(d/a=6\) ⇒ \(d=0{,}120\,\mathrm{mm}\).  
> \(m=3\): \(\beta=\pi/2\) ⇒ \(I_3/I_0=4/\pi^2\).

---

## Siguiente paso lógico

¿Querés que arme la misma chuleta pero solo con un dibujo numerado \(m=0,\pm1,\ldots\) sobre el eje \(y\), o pasamos a otro ejercicio?
