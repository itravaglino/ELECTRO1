# FG4 2020 — Problema 4: qué dice la consigna + desarrollo completo

---

# PARTE A — Qué dice la consigna (frase por frase)

## El experimento

> *“Configuración de dos rendijas, cada una de ancho \(0{,}020\,\mathrm{mm}\).”*

- Hay **dos aberturas** (rendijas) paralelas.
- Cada una tiene **ancho** \(a = 0{,}020\,\mathrm{mm}\) (no confundir con la separación entre ellas).
- La **separación** entre centros de rendijas se llama \(d\) y **no te la dan**: la vas a estimar en (b).

Conversión a metros (la usamos después):

\[
a = 0{,}020\,\mathrm{mm} = 0{,}020 \times 10^{-3}\,\mathrm{m} = 2{,}0 \times 10^{-5}\,\mathrm{m}.
\]

> *“Iluminadas por ondas planas de luz amarilla de sodio (\(\lambda = 589{,}6\,\mathrm{nm}\)).”*

- Luz monocromática de longitud de onda
\[
\lambda = 589{,}6\,\mathrm{nm} = 589{,}6 \times 10^{-9}\,\mathrm{m}.
\]
- **Ondas planas** = el frente de onda llega “plano” a las rendijas (iluminación coherente, típica de Fraunhofer / campo lejano).

> *“El patrón de Fraunhofer resultante…”*

- **Fraunhofer** = difracción en **campo lejano** (pantalla muy lejos, o con lentes; acá te dicen pantalla a \(1\,\mathrm{m}\)).
- En la pantalla ves un patrón de **interferencia** (por haber **dos** rendijas) **modulado** por un **envolvente de difracción** (porque cada rendija tiene **ancho finito** \(a\)).

## Qué significa “11 franjas dentro del primer máximo de difracción”

> *“…consiste en 11 franjas brillantes estrechas dentro del primer máximo de difracción, cuya irradiancia disminuye gradualmente al alejarse del máximo central.”*

Dos efectos a la vez:

1. **Difracción de una rendija** (ancho \(a\)): produce un **lóbulo central ancho** (el “primer máximo de difracción” / máximo central de difracción) y mínimos a los costados. La intensidad de ese lóbulo **baja** al alejarte del centro.
2. **Interferencia de dos rendijas** (separación \(d\)): produce **franjas finas** (máximos y mínimos rápidos) **dentro** de ese lóbulo.

“11 franjas brillantes estrechas” = contás **11 máximos de interferencia** visibles **dentro** del lóbulo central de difracción (antes de llegar al primer mínimo de difracción de cada lado).

## Qué te piden

| Ítem | En criollo |
|------|------------|
| **(a)** | Dibujar (esquema) cómo se ve en una pantalla a \(1\,\mathrm{m}\). |
| **(b)** | Estimar \(d\) (distancia entre rendijas). |
| **(c)** | Del máximo de interferencia \(m=3\), ¿qué fracción es de la intensidad del centro? \(I_3/I_{\text{centro}}\). |

---

# PARTE B — Desarrollo completo ZERO TO HERO

## 0. Desde cero del tema

### Interferencia de Young (dos rendijas “ideales”, sin ancho)

Si cada rendija fuera una línea infinitamente angosta, en la pantalla verías franjas **todas del mismo brillo**:

\[
d\sin\theta = m\lambda
\quad (m=0,\pm 1,\pm 2,\ldots)
\]

máximos brillantes. El ángulo \(\theta\) se mide desde el eje central.

En pantalla a distancia \(D\), con ángulos chicos (\(\sin\theta\approx\tan\theta\approx y/D\)):

\[
y_m \approx m\frac{\lambda D}{d}.
\]

La separación entre franjas vecinas es

\[
\Delta y \approx \frac{\lambda D}{d}.
\]

### Difracción de una sola rendija de ancho \(a\)

Una sola rendija ancha no manda luz igual en todas direcciones. Hay **mínimos** cuando

\[
a\sin\theta = p\lambda
\quad (p=\pm 1,\pm 2,\ldots).
\]

El **primer mínimo** (el más cercano al centro) es \(p=\pm 1\):

\[
\sin\theta_{\text{min}} = \pm \frac{\lambda}{a}.
\]

Entre \(-\lambda/a\) y \(+\lambda/a\) (en \(\sin\theta\)) está el **máximo central de difracción** (“primer máximo de difracción” del enunciado). Ahí la intensidad cae desde el centro hacia esos mínimos.

La forma de la intensidad de **una** rendija es

\[
I_1(\theta) = I_{1,0}\left(\frac{\sin\beta}{\beta}\right)^2,
\qquad
\beta = \frac{\pi a\sin\theta}{\lambda}.
\]

En el centro, \(\beta\to 0\) y \(\sin\beta/\beta \to 1\).

### Las dos juntas (lo que hay en este problema)

Con dos rendijas de ancho \(a\) y separación \(d\), la intensidad en Fraunhofer es:

\[
\boxed{
I(\theta)
=
4\,I_1(\theta)\,\cos^2\!\left(\frac{\phi}{2}\right)
=
4\,I_{1,0}\left(\frac{\sin\beta}{\beta}\right)^2\cos^2\!\left(\frac{\phi}{2}\right)
}
\]

donde

\[
\phi = \frac{\pi d\sin\theta}{\lambda}
\quad\text{(fase por diferencia de camino entre las dos rendijas).}
\]

Lectura en criollo:

- \(\cos^2(\phi/2)\): **franjas finas** de interferencia.
- \((\sin\beta/\beta)^2\): **envolvente ancha** de difracción.

Por eso ves muchas franjitas dentro de un lóbulo grande que se apaga hacia los costados.

---

## 1. Qué pide (lista limpia)

- (a) Esquema del patrón a \(D=1\,\mathrm{m}\).
- (b) Valor de \(d\).
- (c) Cociente \(I(m=3)/I(m=0)\).

## 2. Idea central

El primer mínimo de difracción “corta” el lóbulo central.  
Si ese mínimo cae justo donde iría un máximo de interferencia de orden \(m_*\), entonces \(d/a = m_*\) y el número de franjas brillantes visibles en el centro es \(2m_*-1\).  
Con 11 franjas ⇒ \(m_*=6\) ⇒ \(d=6a\).  
Para (c), en un máximo de interferencia el \(\cos^2=1\) y solo queda el factor de difracción \((\sin\beta/\beta)^2\).

## 3. Setup

| Símbolo | Significado | Valor |
|--------|-------------|-------|
| \(a\) | ancho de cada rendija | \(2{,}0\times 10^{-5}\,\mathrm{m}\) |
| \(d\) | separación entre rendijas (centros) | ¿? (ítem b) |
| \(\lambda\) | longitud de onda | \(5{,}896\times 10^{-7}\,\mathrm{m}\) |
| \(D\) | distancia a la pantalla | \(1\,\mathrm{m}\) |
| \(m\) | orden del máximo de interferencia | \(0,\pm1,\pm2,\ldots\) |

---

## 4. Pasos numerados

1. Relacionar “11 franjas en el lóbulo central” con \(d/a\).
2. Calcular \(d\).
3. (Opcional para el dibujo) tamaños en la pantalla a \(1\,\mathrm{m}\).
4. Evaluar \(I_3/I_0\) con la fórmula completa.

---

## 5. Desarrollo completo

### Paso 1 — Dónde termina el primer máximo de difracción

Primer mínimo de difracción de una rendija:

\[
a\sin\theta = \lambda
\quad\Rightarrow\quad
\sin\theta_{\text{min}} = \frac{\lambda}{a}.
\]

Los máximos de interferencia de Young están en

\[
d\sin\theta = m\lambda
\quad\Rightarrow\quad
\sin\theta_m = \frac{m\lambda}{d}.
\]

### Paso 2 — Cuándo un máximo de interferencia cae en el mínimo de difracción

Si el mínimo de difracción coincide con el máximo de interferencia de orden \(m_*\):

\[
\frac{m_*\lambda}{d} = \frac{\lambda}{a}
\quad\Rightarrow\quad
\frac{d}{a} = m_*.
\]

En ese caso, los órdenes \(\pm m_*\) caen **exactamente** en los ceros de difracción: **no se ven** (intensidad nula).

¿Cuáles sí se ven dentro del lóbulo?

\[
m = 0,\ \pm 1,\ \pm 2,\ \ldots,\ \pm(m_*-1).
\]

Cantidad:

\[
N = 2(m_*-1) + 1 = 2m_* - 1.
\]

### Paso 3 — Ítem (b): usar N = 11

El enunciado dice que hay **11** franjas brillantes en el primer máximo de difracción:

\[
2m_* - 1 = 11
\quad\Rightarrow\quad
2m_* = 12
\quad\Rightarrow\quad
m_* = 6.
\]

Por lo tanto

\[
\frac{d}{a} = 6
\quad\Rightarrow\quad
d = 6a = 6 \times 0{,}020\,\mathrm{mm} = 0{,}120\,\mathrm{mm}.
\]

En metros:

\[
d = 1{,}20 \times 10^{-4}\,\mathrm{m}.
\]

**Resultado (b):**

\[
\boxed{d = 0{,}120\,\mathrm{mm} = 1{,}20\times 10^{-4}\,\mathrm{m}}
\]

**Chequeo de conteo:** se ven \(m=0,\pm1,\pm2,\pm3,\pm4,\pm5\) → eso son **11**. Los \(m=\pm6\) están en el cero de difracción.

### Paso 4 — Ítem (a): esquema + tamaños en la pantalla

Pantalla a \(D=1\,\mathrm{m}\). Ángulos chicos: \(y \approx D\sin\theta\).

**Semiancho del lóbulo central de difracción** (del centro al primer mínimo):

\[
y_{\text{min}}
=
D\frac{\lambda}{a}
=
(1\,\mathrm{m})\frac{589{,}6\times 10^{-9}}{2{,}0\times 10^{-5}}
=
2{,}948\times 10^{-2}\,\mathrm{m}
\approx 2{,}95\,\mathrm{cm}.
\]

El lóbulo central va de \(-y_{\text{min}}\) a \(+y_{\text{min}}\) (unos \(5{,}9\,\mathrm{cm}\) de ancho total).

**Separación entre franjas de interferencia:**

\[
\Delta y
=
D\frac{\lambda}{d}
=
\frac{589{,}6\times 10^{-9}}{1{,}20\times 10^{-4}}
=
4{,}913\times 10^{-3}\,\mathrm{m}
\approx 4{,}91\,\mathrm{mm}.
\]

**Cómo dibujar el esquema:**

```
I
^
|     *           *           *           *           *           *
|    * *         * *         * *         * *         * *         * *
|   *   *       *   *       *   *       *   *       *   *       *   *
|  *     *     *     *     *     *     *     *     *     *     *     *
| *       *   *       *   *       *   *       *   *       *   *       *
|*         * *         * *         * *         * *         * *         *
+----+----+----+----+----+----+----+----+----+----+----+----+----> y
   -5  -4  -3  -2  -1   0  +1  +2  +3  +4  +5
|<------------- lóbulo central de difracción (~ ±3 cm) ------------>|
     (envolvente baja hacia los costados; 11 picos finos)
```

En palabras para el dibujo del examen:

1. Dibujá una **envolvente** ancha, máxima en el centro, que llega a **cero** cerca de \(y=\pm 3\,\mathrm{cm}\).
2. Dentro, dibujá **11 picos finos** (el del centro más 5 de cada lado), cada vez un poco más bajos hacia afuera.
3. Fuera del lóbulo central pueden esbozarse lóbulos laterales de difracción mucho más débiles (opcional; el enunciado se centra en el primero).

**Resultado (a):** esquema como el de arriba (envolvente de difracción + 11 franjas de interferencia; escala \(\Delta y\sim 5\,\mathrm{mm}\), semiancho \(\sim 3\,\mathrm{cm}\)).

### Paso 5 — Ítem (c): intensidad del orden m = 3 relativa al centro

En un **máximo de interferencia**, \(d\sin\theta = m\lambda\), luego \(\phi/2 = m\pi\) y

\[
\cos^2(\phi/2) = 1.
\]

Queda solo la envolvente de difracción:

\[
\frac{I_m}{I_{\text{centro}}}
=
\left(\frac{\sin\beta_m}{\beta_m}\right)^2,
\]

con

\[
\beta_m
=
\frac{\pi a\sin\theta_m}{\lambda}
=
\frac{\pi a}{\lambda}\cdot\frac{m\lambda}{d}
=
\frac{m\pi a}{d}.
\]

Como \(d = 6a\):

\[
\beta_3
=
\frac{3\pi a}{6a}
=
\frac{\pi}{2}.
\]

Entonces

\[
\frac{\sin\beta_3}{\beta_3}
=
\frac{\sin(\pi/2)}{\pi/2}
=
\frac{1}{\pi/2}
=
\frac{2}{\pi}.
\]

\[
\frac{I_3}{I_{\text{centro}}}
=
\left(\frac{2}{\pi}\right)^2
=
\frac{4}{\pi^2}.
\]

Valor numérico (por si lo piden decimal):

\[
\frac{4}{\pi^2} \approx \frac{4}{9{,}870} \approx 0{,}405.
\]

Es decir: el máximo \(m=3\) tiene aproximadamente el **40,5 %** de la intensidad del máximo central.

**Resultado (c):**

\[
\boxed{\dfrac{I_3}{I_0} = \dfrac{4}{\pi^2} \approx 0{,}405}
\]

(usando \(I_0\) aquí como intensidad del máximo central \(m=0\); no confundir con la \(I_0\) del problema 3).

---

## 6. Resultado final (junto)

| Ítem | Respuesta |
|------|-----------|
| **(a)** | Envolvente de difracción (±~3 cm) con 11 franjas finas (Δy~4,9 mm); intensidad baja hacia los costados |
| **(b)** | \(d = 0{,}120\,\mathrm{mm}\) |
| **(c)** | \(I_3/I_{\text{centro}} = 4/\pi^2 \approx 0{,}405\) |

---

## 7. Chequeos

1. **Conteo:** \(m=0,\pm1,\ldots,\pm5\) = 11 franjas; \(m=\pm6\) en el cero. OK.  
2. **Unidades:** \(a\) en mm, \(d=6a\) en mm. OK.  
3. **\(\beta_3=\pi/2\):** está a mitad de camino hacia el primer cero de \(\sin\beta\) (que es en \(\beta=\pi\), o sea \(m=6\)). Tiene sentido que \(m=3\) aún sea brillante pero ya atenuado (~40%).  
4. **Límite \(a\to 0\):** envolvente plana; todas las franjas iguales. Acá \(a\) no es nulo, por eso hay atenuación.  
5. **Ángulos chicos:** \(\lambda/a \approx 0{,}0295\,\mathrm{rad}\approx 1{,}7^\circ\); aproximar \(\sin\theta\approx\theta\approx y/D\) es válido.

---

## 8. Errores típicos de examen

- Confundir **ancho** \(a\) con **separación** \(d\).  
- Poner \(N=2d/a\) en vez de \(N=2d/a-1\) (olvidar que los extremos caen en el cero). Con \(N=11\): \(d/a=6\), no \(5{,}5\).  
- En (c), olvidar la envolvente y decir que \(I_3=I_0\) (eso solo sería cierto si \(a\to 0\)).  
- Usar \(\beta = m\pi a/\lambda\) sin reemplazar \(\sin\theta=m\lambda/d\).  
- Mezclar la \(I_0\) del problema 3 (polarización) con el máximo central de este problema.

---

## 9. Mini-resumen

> Dos rendijas = franjas finas (\(\propto\cos^2\)) × envolvente de una rendija \((\sin\beta/\beta)^2\).  
> 11 franjas en el lóbulo central ⇒ \(2m_*-1=11\) ⇒ \(m_*=d/a=6\) ⇒ \(d=6a=0{,}120\,\mathrm{mm}\).  
> En \(m=3\): \(\beta=3\pi/6=\pi/2\) ⇒ \(I_3/I_0=(2/\pi)^2=4/\pi^2\).

---

## Siguiente paso lógico

1. Variante: calcular también \(I_5/I_0\) (debería ser más chica; \(\beta_5=5\pi/6\)).  
2. Volver a polarización con una variante \(\lambda/4\), o pedir otro ejercicio de la guía.
