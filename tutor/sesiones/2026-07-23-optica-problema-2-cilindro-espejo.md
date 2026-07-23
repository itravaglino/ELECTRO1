# Problema 2 — Cilindro + espejo cóncavo — ZERO TO HERO

---

# PARTE A — Qué dice la consigna

## El sistema (de izquierda a derecha)

1. **Objeto** (flecha de altura \(h\)) en un medio de índice \(n = 1{,}2\).
2. Distancia del objeto a la cara plana del cilindro: \(s = 5\,\mathrm{cm}\).
3. **Cilindro** de índice \(n' = 1{,}8\) y longitud \(D = 10\,\mathrm{cm}\).
   - Cara izquierda: **plana** (dioptro plano \(n \to n'\)).
   - Cara derecha: **espejo cóncavo** de radio \(R = 40\,\mathrm{cm}\) (la superficie reflectora “mira” hacia la izquierda, hacia el objeto).
4. El sistema está inmerso en el medio \(n = 1{,}2\).

## Camino de la luz (muy importante)

La luz **no** hace una sola cosa. Hace **tres etapas**:

1. Refracción en la cara **plana** (\(n \to n'\)), luz hacia la derecha.
2. Reflexión en el **espejo cóncavo** (dentro de \(n'\)), luz vuelve hacia la izquierda.
3. Refracción otra vez en la cara **plana** (\(n' \to n\)), luz hacia la izquierda, saliendo al medio exterior.

## Qué pedir

| Ítem | En criollo |
|------|------------|
| **(a)** | ¿Dónde queda la imagen final? |
| **(b)** | Si el espejo se vuelve plano (\(R\to\infty\)), ¿dónde queda la imagen? |
| **(c)** | Si \(D\) es casi cero (espejo pegado a la cara plana), ¿a qué se parece el sistema? |

---

# PARTE B — Herramientas desde cero

## 1. Dioptro plano (superficie plana entre dos índices)

Fórmula (superficie plana ⇒ radio infinito, potencia cero):

\[
\boxed{\frac{n_2}{s'} = \frac{n_1}{s}}
\quad\Leftrightarrow\quad
s' = \frac{n_2}{n_1}\,s
\]

(con distancias medidas en valor absoluto en el sentido que aclaramos en cada paso).

**Física clave (refracción plano, objeto real):**

- Objeto en el medio \(n_1\), luz que pasa a \(n_2\).
- Los rayos **siguen divergiendo** después de la cara plana (no hay convergencia real “adentro”).
- La imagen para esos rayos transmitidos es **virtual** y está del **mismo lado** que el objeto.
- Si \(n_2 > n_1\) (entra a un medio más denso), la imagen virtual queda **más lejos** de la superficie que el objeto:
  \[
  |s'| = \frac{n_2}{n_1}|s| > |s|.
  \]

## 2. Espejo esférico (mismo medio a ambos lados del “viaje” reflejado)

\[
\boxed{\frac{1}{s} + \frac{1}{s'} = \frac{1}{f}}
\qquad
\boxed{f = \frac{R}{2}}
\]

para espejo **cóncavo** (convergente), tomando \(f > 0\) y usando la convención:

- \(s > 0\): objeto **real** (rayos incidentes divergen desde un punto delante del espejo).
- \(s' > 0\): imagen **real** (rayos reflejados convergen delante del espejo).
- \(s' < 0\): imagen **virtual** (rayos reflejados divergen; la imagen parece estar **detrás** del espejo).

Si el objeto está **dentro** del foco (\(s < f\)), la imagen es virtual y detrás del espejo.

## 3. Estrategia del problema

Resolver **en cadena**: la imagen de una etapa es el objeto de la siguiente.

---

# PARTE C — Desarrollo completo

## Datos

\[
n=1{,}2,\quad n'=1{,}8,\quad s=5\,\mathrm{cm},\quad D=10\,\mathrm{cm},\quad R=40\,\mathrm{cm}.
\]

Foco del espejo cóncavo:

\[
f = \frac{R}{2} = 20\,\mathrm{cm}.
\]

Ponemos la cara plana en \(x=0\), el espejo en \(x=+D=+10\,\mathrm{cm}\), el objeto en \(x=-5\,\mathrm{cm}\).

---

## Etapa 1 — Refracción en la cara plana (\(n\to n'\))

Objeto real a \(5\,\mathrm{cm}\) a la izquierda, en medio \(n\).

\[
|s_1'| = \frac{n'}{n}\,s = \frac{1{,}8}{1{,}2}\times 5 = 1{,}5\times 5 = 7{,}5\,\mathrm{cm}.
\]

**Tipo:** imagen **virtual**, del lado del objeto (izquierda).

**Posición:** a \(7{,}5\,\mathrm{cm}\) a la **izquierda** de la cara plana (\(x = -7{,}5\,\mathrm{cm}\)).

**Por qué virtual:** la cara es plana; no concentra rayos. Dentro del cilindro, los rayos **divergen** como si vinieran de ese punto \(I_1\).

```
  I1(virtual)    objeto        cara plana
      |            |               |
   -7.5 cm      -5 cm             0
      <----7.5cm---->
```

---

## Etapa 2 — Reflexión en el espejo cóncavo

Los rayos dentro de \(n'\) divergen desde \(I_1\).  
El espejo está en \(x=10\,\mathrm{cm}\).

Distancia objeto–espejo:

\[
s_2 = D + 7{,}5\,\mathrm{cm} = 10 + 7{,}5 = 17{,}5\,\mathrm{cm}.
\]

Objeto **real** para el espejo (los rayos llegan divergiendo desde un punto delante).

Espejo cóncavo: \(f = 20\,\mathrm{cm}\).  
Como \(s_2 = 17{,}5 < 20 = f\), el objeto está **dentro del foco** ⇒ imagen **virtual detrás** del espejo.

\[
\frac{1}{s_2} + \frac{1}{s_2'} = \frac{1}{f}
\]

\[
\frac{1}{s_2'} = \frac{1}{20} - \frac{1}{17{,}5}
= \frac{17{,}5 - 20}{20\times 17{,}5}
= \frac{-2{,}5}{350}
= -\frac{1}{140}
\]

\[
s_2' = -140\,\mathrm{cm}.
\]

**Tipo:** imagen **virtual**, \(140\,\mathrm{cm}\) **detrás** del espejo (a la derecha).

**Posición:** \(x = 10 + 140 = +150\,\mathrm{cm}\).

Después de reflejar, la luz viaja hacia la **izquierda**, divergiendo como si saliera de ese punto \(I_2\) en \(x=150\,\mathrm{cm}\).

---

## Etapa 3 — Refracción de salida en la cara plana (\(n'\to n\))

Luz hacia la izquierda, de \(n'\) a \(n\).

Para la cara plana, el “objeto” es \(I_2\): está a la derecha de la cara, a distancia

\[
s_3 = 150\,\mathrm{cm} - 0 = 150\,\mathrm{cm}.
\]

Los rayos incidentes (yendo a la izquierda) divergen desde \(I_2\) ⇒ objeto **real** respecto de esta superficie (punto emisor efectivo del lado de incidencia).

Dioptro plano \(n' \to n\):

\[
|s_3'| = \frac{n}{n'}\,s_3 = \frac{1{,}2}{1{,}8}\times 150 = \frac{2}{3}\times 150 = 100\,\mathrm{cm}.
\]

**Tipo:** al pasar a un medio **menos denso**, la imagen transmitida es **virtual** y queda del **mismo lado** que el objeto \(I_2\) (lado derecho), más cerca de la superficie:

\[
|s_3'| = 100\,\mathrm{cm} < 150\,\mathrm{cm}.
\]

**Posición de la imagen final \(I\):** a \(100\,\mathrm{cm}\) a la **derecha** de la cara plana (\(x = +100\,\mathrm{cm}\)).

Un observador en el medio \(n\), a la izquierda, mirando hacia el sistema, ve la imagen **atrasada** \(100\,\mathrm{cm}\) respecto de la cara plana (como “dentro/detrás” del sistema).

### Resultado (a)

\[
\boxed{
\text{Imagen final a } 100\,\mathrm{cm} \text{ a la derecha de la cara plana}
}
\]

(virtual para la luz que sale hacia la izquierda; respecto del espejo: \(100-10=90\,\mathrm{cm}\) detrás del espejo).

---

## Ítem (b) — \(R \to \infty\) (espejo plano)

Si \(R\to\infty\), entonces \(f\to\infty\): el espejo se vuelve **plano**.

Para un espejo plano: la imagen es simétrica del objeto,

\[
s_2' = -s_2 = -17{,}5\,\mathrm{cm}.
\]

Imagen \(17{,}5\,\mathrm{cm}\) detrás del espejo ⇒ en

\[
x = 10 + 17{,}5 = 27{,}5\,\mathrm{cm}.
\]

Salida por la cara plana (\(n'\to n\)), objeto a \(s_3 = 27{,}5\,\mathrm{cm}\) a la derecha:

\[
|s_3'| = \frac{n}{n'}\cdot 27{,}5 = \frac{1{,}2}{1{,}8}\times 27{,}5 = \frac{55}{3} \approx 18{,}33\,\mathrm{cm}.
\]

### Resultado (b)

\[
\boxed{
\text{Imagen a } \dfrac{55}{3}\,\mathrm{cm} \approx 18{,}3\,\mathrm{cm}
\text{ a la derecha de la cara plana}
}
\]

---

## Ítem (c) — \(D\) muy chico, \(R\) finito, espejo pegado a la superficie

Si \(D \to 0\), la cara plana y el vértice del espejo están **casi en el mismo lugar**.

Entonces:

- casi no hay “viaje” dentro del cilindro entre refracción y reflexión;
- el sistema se comporta como un elemento **delgado catadióptrico**:  
  **dioptro plano + espejo esférico cóncavo en contacto**.

En criollo: la luz atraviesa la cara plana, se refleja de inmediato en el cóncavo y vuelve a salir por la misma cara plana.  
Es la aproximación de un “espejo cóncavo detrás de una interfaz plana”, sin espesor apreciable \(D\).

No hace falta calcular el caso límite salvo que lo pidan numérico; el punto del ítem es **reconocer** esa aproximación.

### Resultado (c)

\[
\boxed{
\text{Se aproxima a un sistema delgado: dioptro plano + espejo cóncavo pegados (catadióptrico delgado).}
}
\]

---

# Chequeos

1. Etapa 1: \(n'>n\) ⇒ imagen virtual más lejos (\(7{,}5>5\)). OK.  
2. Etapa 2: \(s<f\) ⇒ imagen virtual detrás del espejo. OK.  
3. Etapa 3: \(n<n'\) al salir ⇒ \(|s'|<|s|\) (\(100<150\)). OK.  
4. Si \(R\to\infty\), la imagen final se acerca a la cara (\(18{,}3\,\mathrm{cm}\) vs \(100\,\mathrm{cm}\)): el espejo plano “empuja” menos la imagen hacia atrás. Razonable.

---

# Errores típicos

- Tratar el cilindro como una sola lente.  
- Olvidar que la luz **vuelve** y hay que refractar otra vez al salir.  
- Poner la primera imagen como real dentro del cilindro (en dioptro plano con objeto real, es **virtual**).  
- Usar \(f=-R/2\) y mezclar signos sin criterio.  
- En (b), olvidar que \(R\to\infty\) es espejo **plano**, no “sin espejo”.

---

# Mini-resumen

> 1) Plano \(n\to n'\): \(I_1\) virtual a \(7{,}5\,\mathrm{cm}\) a la izquierda.  
> 2) Espejo cóncavo \(f=20\): objeto \(17{,}5\,\mathrm{cm}\) ⇒ \(I_2\) virtual \(140\,\mathrm{cm}\) detrás del espejo.  
> 3) Plano \(n'\to n\): objeto \(150\,\mathrm{cm}\) ⇒ imagen final a \(100\,\mathrm{cm}\) a la derecha de la cara plana.  
> (b) Espejo plano ⇒ imagen final a \(55/3\,\mathrm{cm}\) a la derecha.  
> (c) \(D\to 0\) ⇒ dioptro plano + espejo cóncavo delgados en contacto.

---

## Siguiente paso lógico

¿Querés que rehaga el (a) solo con un esquema de rayos etapa por etapa, o que calcule también el aumento lateral?
