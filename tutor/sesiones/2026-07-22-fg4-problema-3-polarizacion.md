# FG4 2020 — Problema 3: qué dice la consigna + desarrollo completo

---

# PARTE A — Qué dice la consigna (frase por frase)

## Escenario inicial

> *“Un haz de luz linealmente polarizada se propaga en la dirección \(z\).”*

- Hay un rayo de luz que viaja hacia adelante en el eje \(z\).
- **Linealmente polarizada** = el campo eléctrico \(\mathbf{E}\) vibra siempre sobre **una sola recta** (no da vueltas en círculo ni elipse).

> *“El vector campo eléctrico vibra en el primer cuadrante del plano \(xy\).”*

- Como la luz va en \(z\), \(\mathbf{E}\) está en el plano \(xy\).
- **Primer cuadrante** = la recta de vibración está entre el eje \(+x\) y el eje \(+y\).
- Llamamos \(\alpha\) al ángulo entre esa recta y el eje \(x\). Entonces \(0^\circ < \alpha < 90^\circ\).

## Mediciones con el analizador

Un **analizador** es un polarizador lineal que podés rotar. Solo deja pasar la parte de \(\mathbf{E}\) alineada con su eje.

> *“Si el eje de transmisión del analizador está en la dirección \(y\), la intensidad transmitida es \(I_0\).”*

- Ponés el analizador vertical (eje en \(y\)).
- Sale intensidad \(I_0\).

> *“Si el eje de transmisión está en la dirección \(x\), la intensidad transmitida es \(3I_0\).”*

- Ponés el analizador horizontal (eje en \(x\)).
- Sale intensidad \(3I_0\) (tres veces más que antes).

Eso ya te dice algo: hay **más** componente de \(\mathbf{E}\) en \(x\) que en \(y\), así que \(\alpha\) está más cerca de \(x\) que de \(y\) (menor que \(45^\circ\)).

## Qué te piden (a) y (b)

> **(a)** Determinar la intensidad del haz incidente en función de \(I_0\) y del ángulo \(\alpha\) que forma el plano de polarización original con el eje \(x\).

- “Haz incidente” = la luz **antes** de pasar por el analizador. Intensidad: \(I_i\).
- Pedís \(I_i\) relacionada con \(I_0\) y \(\alpha\). Con los dos datos también se fijan los valores numéricos de \(I_i\) y \(\alpha\).

> **(b)** Determinar la intensidad medida cuando el eje del analizador forma \(\theta = 60^\circ\) con el eje \(x\).

- Girás el analizador a \(60^\circ\) respecto de \(x\) y calculás qué intensidad sale.

## Segunda parte: lámina \(\lambda/2\)

> *“El haz original atraviesa una lámina de media onda (\(\lambda/2\)) y luego el analizador lineal. El eje óptico de la lámina forma \(\beta = 45^\circ\) con el eje \(x\).”*

- Ahora, **antes** del analizador, interponés una lámina de media onda.
- Su eje óptico está a \(45^\circ\) respecto de \(x\).
- Esa lámina **cambia la orientación** del plano de polarización (pero sigue siendo luz lineal).

> **(c)** Determinar el tipo de polarización a la salida de la lámina y describir la orientación del plano de polarización.

- ¿Sigue lineal? ¿circular? ¿elíptica?
- ¿A qué ángulo queda el plano?

> **(d)** Determinar la nueva intensidad transmitida cuando el analizador otra vez está a \(\theta = 60^\circ\) con \(x\).

- Misma posición del analizador que en (b), pero ahora la luz ya pasó por la lámina. La intensidad puede cambiar.

---

# PARTE B — Desarrollo completo ZERO TO HERO

## 0. Herramientas (solo las necesarias)

### Intensidad después de un analizador (ley de Malus)

Si la luz llega con intensidad \(I_i\), polarizada a ángulo \(\alpha\) respecto de \(x\), y el analizador está a ángulo \(\theta\) respecto de \(x\), el ángulo entre ambos es \(\alpha-\theta\). El campo se proyecta con un \(\cos\); la intensidad lleva el cuadrado:

\[
\boxed{I = I_i \cos^2(\alpha - \theta)}
\]

### Lámina de media onda

Introduce un desfase de \(\pi\) entre el eje óptico y su perpendicular.  
Para luz **lineal** de entrada: la salida **sigue lineal**, y el plano queda **reflejado** respecto del eje óptico:

\[
\boxed{\alpha' = 2\beta - \alpha}
\]

donde \(\beta\) es el ángulo del eje óptico.

---

## 1. Qué hay que encontrar (lista limpia)

| Ítem | Pedido |
|------|--------|
| (a) | \(I_i\) y \(\alpha\) |
| (b) | \(I\) con \(\theta=60^\circ\) (sin lámina) |
| (c) | tipo + orientación después de \(\lambda/2\) |
| (d) | \(I\) con \(\theta=60^\circ\) (con lámina) |

---

## 2. Idea central

1. Cada medición = proyección ⇒ Malus.  
2. Con \(I_x\) e \(I_y\) sacamos \(I_i\) y \(\alpha\).  
3. \(\lambda/2\) refleja el plano: \(\alpha \to \alpha'\).  
4. Malus otra vez con \(\alpha'\).

---

## 3. Setup

- \(I_i\): intensidad incidente (desconocida al inicio).  
- \(\alpha\): ángulo de polarización original con \(x\) (desconocido).  
- Datos: \(I(\theta=0^\circ)=3I_0\), \(I(\theta=90^\circ)=I_0\).  
- Luego: \(\beta=45^\circ\), \(\theta=60^\circ\).

---

## 4. Pasos

1. Malus en \(x\) y en \(y\).  
2. Resolver \(I_i\) y \(\alpha\).  
3. Malus a \(60^\circ\).  
4. Reflejar con \(\lambda/2\).  
5. Malus a \(60^\circ\) otra vez.

---

## 5. Desarrollo

### Paso 1 — Escribir las dos mediciones

**Analizador en \(x\)** (\(\theta = 0^\circ\)):

\[
I_i \cos^2\alpha = 3I_0 \tag{1}
\]

**Analizador en \(y\)** (\(\theta = 90^\circ\)):

\[
\cos(\alpha - 90^\circ) = \sin\alpha
\quad\Rightarrow\quad
I_i \sin^2\alpha = I_0 \tag{2}
\]

### Paso 2 — Ítem (a)

Forma pedida “en función de \(I_0\) y \(\alpha\)”:

\[
I_i = \frac{3I_0}{\cos^2\alpha}
\qquad\text{o}\qquad
I_i = \frac{I_0}{\sin^2\alpha}.
\]

Igualamos (dividiendo (2)÷(1)):

\[
\frac{\sin^2\alpha}{\cos^2\alpha} = \tan^2\alpha = \frac{I_0}{3I_0} = \frac{1}{3}.
\]

\[
\tan\alpha = \frac{1}{\sqrt{3}}
\quad\Rightarrow\quad
\alpha = 30^\circ
\]

(primer cuadrante ⇒ tomamos \(30^\circ\), no \(210^\circ\)).

Sumando (1)+(2):

\[
I_i(\cos^2\alpha + \sin^2\alpha) = 3I_0 + I_0 = 4I_0
\quad\Rightarrow\quad
I_i = 4I_0.
\]

**Verificación:**

\[
\cos 30^\circ = \frac{\sqrt{3}}{2},\quad \cos^2 30^\circ = \frac{3}{4},
\quad 4I_0 \cdot \frac{3}{4} = 3I_0. \checkmark
\]

\[
\sin 30^\circ = \frac{1}{2},\quad \sin^2 30^\circ = \frac{1}{4},
\quad 4I_0 \cdot \frac{1}{4} = I_0. \checkmark
\]

**Resultado (a):**

\[
\boxed{I_i = 4I_0, \qquad \alpha = 30^\circ}
\]

### Paso 3 — Ítem (b)

Sin lámina, analizador a \(\theta = 60^\circ\):

\[
\begin{aligned}
I(60^\circ)
&= I_i \cos^2(\alpha - 60^\circ) \\
&= 4I_0 \cos^2(30^\circ - 60^\circ) \\
&= 4I_0 \cos^2(-30^\circ) \\
&= 4I_0 \cos^2 30^\circ \\
&= 4I_0 \cdot \frac{3}{4} \\
&= 3I_0.
\end{aligned}
\]

**Resultado (b):**

\[
\boxed{I(60^\circ) = 3I_0}
\]

### Paso 4 — Ítem (c): después de la lámina \(\lambda/2\)

Eje óptico a \(\beta = 45^\circ\). Polarización de entrada \(\alpha = 30^\circ\).

La media onda **refleja** el plano respecto de ese eje:

\[
\alpha' = 2\beta - \alpha = 2\cdot 45^\circ - 30^\circ = 60^\circ.
\]

Como la entrada era lineal y el desfase es \(\pi\) (no \(\pi/2\)), la salida **sigue siendo lineal**.

**Por qué \(2\beta-\alpha\):** el eje a \(45^\circ\) es el “espejo”. El ángulo de entrada está \(15^\circ\) por debajo de \(45^\circ\) (\(45-30=15\)); la imagen está \(15^\circ\) por encima: \(45+15=60\).

**Resultado (c):**

\[
\boxed{\text{Polarización lineal, plano a } 60^\circ \text{ respecto del eje } x.}
\]

### Paso 5 — Ítem (d)

Ahora la luz que llega al analizador está polarizada a \(\alpha' = 60^\circ\).  
El analizador está a \(\theta = 60^\circ\):

\[
I' = I_i \cos^2(\alpha' - \theta) = 4I_0 \cos^2(60^\circ - 60^\circ) = 4I_0 \cos^2 0 = 4I_0.
\]

Interpretación: analizador **alineado** con \(\mathbf{E}\) ⇒ (idealmente) pasa toda la intensidad.

**Resultado (d):**

\[
\boxed{I' = 4I_0}
\]

---

## 6. Resultado final (todo junto)

| Ítem | Respuesta |
|------|-----------|
| **(a)** | \(I_i = 4I_0\), \(\alpha = 30^\circ\) |
| **(b)** | \(3I_0\) |
| **(c)** | Lineal, a \(60^\circ\) con \(x\) |
| **(d)** | \(4I_0\) |

---

## 7. Chequeos

1. \(I_x + I_y = 3I_0 + I_0 = 4I_0 = I_i\): en polarización lineal, dos ejes ortogonales recuperan toda la intensidad.  
2. \(\alpha = 30^\circ < 45^\circ\): coherente con \(I_x > I_y\).  
3. Con la lámina, a \(60^\circ\) la intensidad **sube** de \(3I_0\) a \(4I_0\): la lámina alineó el campo con el analizador.  
4. \(\lambda/2\) no produce circular: eso sería típico de \(\lambda/4\) con entrada a \(45^\circ\) del eje.

---

## 8. Errores típicos

- Usar \(\cos\) en vez de \(\cos^2\).  
- En \(y\), olvidar que el factor es \(\sin\alpha\).  
- Confundir \(\lambda/2\) con \(\lambda/4\).  
- Usar \(\alpha' = \beta - \alpha\) en vez de \(2\beta - \alpha\).  
- En (d), seguir usando \(\alpha = 30^\circ\) en vez de \(\alpha' = 60^\circ\).

---

## 9. Mini-resumen

> Consigna: luz lineal a ángulo \(\alpha\); medís \(I_x=3I_0\), \(I_y=I_0\); después \(\lambda/2\) a \(45^\circ\) y otra vez el analizador a \(60^\circ\).  
> Malus ⇒ \(I_i=4I_0\), \(\alpha=30^\circ\).  
> Sin lámina a \(60^\circ\) ⇒ \(3I_0\).  
> \(\lambda/2\) refleja ⇒ lineal a \(60^\circ\).  
> Analizador a \(60^\circ\) ⇒ \(4I_0\).

---

## Siguiente paso lógico

¿Seguimos con el **Problema 4** de la misma hoja (doble rendija + difracción), o querés que baje un nivel más en Malus / lámina \(\lambda/2\) con un ejemplo numérico chico?
