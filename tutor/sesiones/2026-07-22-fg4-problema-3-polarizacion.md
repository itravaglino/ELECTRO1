# FG4 2020 — Problema 3 — ZERO TO HERO (completo desde cero)

Material: `tutor/inbox/FG4-2020-problema-3.md` (captura del enunciado).

---

## 0. Desde cero del tema

### ¿Qué es la luz para este problema?

Para polarización tratamos la luz como una **onda electromagnética**. Lo que “vibra” y detectamos con polarizadores es el **campo eléctrico \(\mathbf{E}\)**.

La onda se propaga en \(+z\). Entonces \(\mathbf{E}\) está en el plano \(xy\) (transversal a la propagación).

### ¿Qué significa “linealmente polarizada”?

Significa que \(\mathbf{E}\) oscila **siempre sobre una misma recta** fija en el plano \(xy\).

Esa recta forma un ángulo \(\alpha\) con el eje \(x\). Como el enunciado dice **primer cuadrante**, tenemos

\[
0 < \alpha < 90^\circ.
\]

Si la amplitud del campo es \(E_0\), podemos escribir:

\[
\mathbf{E}
=
E_0\cos(kz-\omega t)
\bigl(\cos\alpha\,\hat{\mathbf{x}}+\sin\alpha\,\hat{\mathbf{y}}\bigr).
\]

### ¿Qué es un polarizador / analizador lineal?

Es un filtro que **solo deja pasar** la componente de \(\mathbf{E}\) paralela a su **eje de transmisión**.

Si el eje del analizador forma un ángulo \(\theta\) con \(x\), la dirección permitida es

\[
\hat{\mathbf{e}}_\theta=\cos\theta\,\hat{\mathbf{x}}+\sin\theta\,\hat{\mathbf{y}}.
\]

La componente transmitida del campo es la proyección:

\[
E_{\text{tx}}
=
\mathbf{E}\cdot\hat{\mathbf{e}}_\theta
=
E_0\cos(kz-\omega t)\cos(\alpha-\theta).
\]

### Intensidad

La intensidad \(I\) es proporcional al promedio temporal de \(|\mathbf{E}|^2\). Por eso, si la intensidad incidente (antes del analizador) es \(I_i\), la transmitida cumple la **ley de Malus**:

\[
\boxed{I=I_i\cos^2(\alpha-\theta)}
\]

dónde \(\alpha-\theta\) es el ángulo entre la polarización de la luz y el eje del analizador.

**De dónde sale el cos²:** el campo se multiplica por \(\cos\delta\); la intensidad va como el cuadrado del campo ⇒ \(\cos^2\delta\).

### ¿Qué es una lámina de media onda (\(\lambda/2\))?

Es una placa birrefringente con dos ejes perpendiculares (eje rápido / eje lento, o “eje óptico” y su perpendicular).

Introduce una diferencia de camino óptico de \(\lambda/2\) entre esas dos componentes ⇒ **desfase de \(\pi\)** (media vuelta).

Efecto sobre luz **linealmente polarizada**:
- sigue siendo **linealmente polarizada**;
- el plano de polarización queda **reflejado** respecto del eje óptico de la lámina.

Si el eje óptico está a ángulo \(\beta\) respecto de \(x\), y la polarización de entrada está a \(\alpha\), la de salida queda a

\[
\boxed{\alpha'=2\beta-\alpha}
\]

(es la reflexión especular del ángulo \(\alpha\) alrededor de la recta a ángulo \(\beta\)).

¿Por qué es una reflexión? Porque un desfase \(\pi\) en la componente perpendicular al eje óptico **cambia el signo** de esa componente, y cambiar el signo de la componente perpendicular es exactamente reflejar el vector \(\mathbf{E}\) respecto del eje óptico.

---

## 1. Qué pide

Tenemos luz linealmente polarizada (ángulo \(\alpha\) desconocido a priori) y mediciones con un analizador.

- **(a)** Intensidad incidente \(I_i\) en términos de \(I_0\) y \(\alpha\) (y, con los datos, fijar sus valores).
- **(b)** Intensidad con analizador a \(\theta=60^\circ\).
- Después: pasa por lámina \(\lambda/2\) con eje a \(\beta=45^\circ\).
- **(c)** Tipo y orientación de la polarización a la salida de la lámina.
- **(d)** Intensidad con analizador otra vez a \(\theta=60^\circ\).

---

## 2. Idea central

1. Cada medición con el analizador es una proyección ⇒ Malus.
2. Con las dos mediciones (\(x\) e \(y\)) fijamos \(I_i\) y \(\alpha\).
3. La lámina \(\lambda/2\) **no cambia** “lineal → lineal”; solo **rota** el plano por reflexión respecto de su eje.
4. Volvemos a aplicar Malus con el nuevo ángulo.

---

## 3. Herramientas previas

| Herramienta | Qué es | Para qué |
|-------------|--------|----------|
| Polarización lineal | \(\mathbf{E}\) vibra en una sola dirección | modelo del haz |
| Analizador | deja pasar solo una proyección | mide componentes |
| Ley de Malus | \(I=I_i\cos^2\delta\) | ítems a, b, d |
| Lámina \(\lambda/2\) | desfase \(\pi\) ⇒ refleja el plano de polarización | ítems c, d |

---

## 4. Setup

| Símbolo | Significado |
|--------|-------------|
| \(I_i\) | intensidad del haz **incidente** (antes del analizador / lámina) |
| \(I_0\) | dato del enunciado (una intensidad de referencia) |
| \(\alpha\) | ángulo del plano de polarización **original** con el eje \(x\) |
| \(\theta\) | ángulo del eje del **analizador** con \(x\) |
| \(\beta=45^\circ\) | ángulo del eje óptico de la lámina \(\lambda/2\) con \(x\) |
| \(\alpha'\) | ángulo de polarización **después** de la lámina |

**Datos:**

- Analizador en \(y\) (\(\theta=90^\circ\)): \(I=I_0\)
- Analizador en \(x\) (\(\theta=0^\circ\)): \(I=3I_0\)
- Primer cuadrante: \(\alpha\in(0,\pi/2)\)

**Diagrama mental (antes de la lámina):**

```
        y
        ^
        |   E (polarización a ángulo α)
        |  /
        | /
        |/____\ α
        +--------> x
```

---

## 5. Pasos numerados

1. Escribir Malus para analizador en \(x\) y en \(y\).
2. Resolver \(I_i\) y \(\alpha\).
3. Aplicar Malus con \(\theta=60^\circ\).
4. Reflejar el ángulo con la lámina \(\lambda/2\) (\(\beta=45^\circ\)).
5. Aplicar Malus otra vez con \(\theta=60^\circ\).

---

## 6. Desarrollo completo

### Paso 1 — Las dos mediciones

Ley de Malus: \(I=I_i\cos^2(\alpha-\theta)\).

**Analizador en \(x\):** \(\theta=0^\circ\)

\[
I_x=I_i\cos^2\alpha=3I_0.
\qquad (1)
\]

**Analizador en \(y\):** \(\theta=90^\circ\)

\[
\cos(\alpha-90^\circ)=\sin\alpha,
\]

\[
I_y=I_i\sin^2\alpha=I_0.
\qquad (2)
\]

### Paso 2 — Ítem (a): \(I_i\) y \(\alpha\)

**Forma pedida “en función de \(I_0\) y \(\alpha\)”:**

De (1):

\[
I_i=\frac{3I_0}{\cos^2\alpha}.
\]

De (2):

\[
I_i=\frac{I_0}{\sin^2\alpha}.
\]

Las dos deben coincidir. Dividiendo (2)/(1):

\[
\frac{\sin^2\alpha}{\cos^2\alpha}=\tan^2\alpha=\frac{I_0}{3I_0}=\frac13.
\]

\[
\tan\alpha=\frac{1}{\sqrt{3}}
\quad\Rightarrow\quad
\alpha=30^\circ
\]

(positivo, primer cuadrante: descartamos \(210^\circ\), etc.).

Ahora, sumando (1)+(2):

\[
I_i(\cos^2\alpha+\sin^2\alpha)=3I_0+I_0
\quad\Rightarrow\quad
I_i=4I_0.
\]

Chequeo con \(\alpha=30^\circ\):

\[
\cos 30^\circ=\sqrt{3}/2,\quad\cos^2=3/4,
\quad
I_i\cdot\frac34=4I_0\cdot\frac34=3I_0.
\]

\[
\sin 30^\circ=1/2,\quad\sin^2=1/4,
\quad
4I_0\cdot\frac14=I_0.
\]

Perfecto.

**Respuesta (a):**

\[
\boxed{I_i=4I_0,\qquad \alpha=30^\circ}
\]

(y en la forma funcional: \(I_i=3I_0/\cos^2\alpha=I_0/\sin^2\alpha\)).

### Paso 3 — Ítem (b): analizador a \(\theta=60^\circ\)

\[
I(60^\circ)
=
I_i\cos^2(\alpha-60^\circ)
=
4I_0\cos^2(30^\circ-60^\circ)
=
4I_0\cos^2(-30^\circ)
=
4I_0\cos^2 30^\circ
=
4I_0\cdot\frac34
=
3I_0.
\]

**Respuesta (b):**

\[
\boxed{I(60^\circ)=3I_0}
\]

### Paso 4 — Ítem (c): después de la lámina \(\lambda/2\)

Eje óptico a \(\beta=45^\circ\). Polarización de entrada a \(\alpha=30^\circ\).

La lámina de media onda **refleja** el plano de polarización respecto de su eje:

\[
\alpha'=2\beta-\alpha=2\cdot 45^\circ-30^\circ=90^\circ-30^\circ=60^\circ.
\]

Como la entrada era lineal, la salida **sigue siendo lineal** (solo giró el plano).

**Respuesta (c):**

\[
\boxed{
\text{Polarización lineal, con plano a }\alpha'=60^\circ\text{ respecto del eje }x.
}
\]

(Es decir: el vector \(\mathbf{E}\) vibra sobre la recta que forma \(60^\circ\) con \(x\), aún en el primer cuadrante.)

**Mini-imagen:**

```
eje óptico de la lámina a 45°
entrada α = 30°   →   se refleja   →   salida α' = 60°
(simétricos respecto de la recta a 45°)
```

### Paso 5 — Ítem (d): otra vez analizador a \(60^\circ\)

Ahora, **antes** del analizador, la luz ya está polarizada a \(\alpha'=60^\circ\).  
El analizador está a \(\theta=60^\circ\).

\[
I'
=
I_i\cos^2(\alpha'-\theta)
=
4I_0\cos^2(60^\circ-60^\circ)
=
4I_0\cos^2 0
=
4I_0.
\]

Interpretación: el analizador está **alineado** con la polarización ⇒ transmite todo (en el modelo ideal).

**Respuesta (d):**

\[
\boxed{I'=4I_0}
\]

---

## 7. Resultado final (junto)

| Ítem | Resultado |
|------|-----------|
| (a) | \(I_i=4I_0\), \(\alpha=30^\circ\) |
| (b) | \(I(60^\circ)=3I_0\) |
| (c) | Lineal, plano a \(60^\circ\) con \(x\) |
| (d) | \(I'=4I_0\) |

---

## 8. Chequeos

1. \(I_x+I_y=3I_0+I_0=4I_0=I_i\): para polarización lineal, las intensidades en dos ejes ortogonales suman la intensidad total. OK.
2. \(\alpha=30^\circ\) está en el primer cuadrante. OK.
3. Sin lámina, a \(60^\circ\) dio \(3I_0\); con lámina alineó a \(60^\circ\) y pasó a \(4I_0 > 3I_0\): coherente (la lámina reorientó el campo a favor del analizador).
4. Lámina \(\lambda/2\) **no** crea elipse: desfase \(\pi\) mantiene linealidad. OK.

---

## 9. Errores típicos de examen

- Usar \(\cos\) en vez de \(\cos^2\) (olvidar que intensidad ∝ campo²).
- Confundir el ángulo: poner \(\cos(\alpha+\theta)\) o mezclar \(\alpha\) con \(\theta\).
- Para analizador en \(y\), olvidar que \(\cos(\alpha-90^\circ)=\sin\alpha\).
- Creer que la lámina \(\lambda/2\) produce polarización circular (eso es, en el caso típico de entrada a \(45^\circ\) respecto del eje, una lámina **cuarto de onda** \(\lambda/4\)).
- Usar \(\alpha'=\beta-\alpha\) en vez de \(2\beta-\alpha\).
- En (d), usar todavía \(\alpha=30^\circ\) en vez de \(\alpha'=60^\circ\).

---

## 10. Mini-resumen

> Malus: \(I=I_i\cos^2(\alpha-\theta)\).  
> Datos \(I_x=3I_0\), \(I_y=I_0\) ⇒ \(I_i=4I_0\), \(\alpha=30^\circ\).  
> Sin lámina, \(\theta=60^\circ\) ⇒ \(3I_0\).  
> \(\lambda/2\) con eje a \(45^\circ\) refleja: \(\alpha'=60^\circ\) (sigue lineal).  
> Analizador a \(60^\circ\) ⇒ transmite todo: \(4I_0\).

---

## Siguiente paso lógico

1. Variante: ¿qué pasaría si fuera lámina \(\lambda/4\) (cuarto de onda) con el mismo eje a \(45^\circ\)?
2. Seguir con el **Problema 4** de la misma hoja (interferencia + difracción, doble rendija).
