# Sesión 2026-07-21 — Guía 7 EMI, Problema 5

**Material:** `tutor/inbox/Guia_7_EMI.pdf` (Electromagnetismo I – 2026, Magnetostática)  
**Pedido:** Problema 5, ítems a) y b)

---

## Mapeo rápido de la guía (contexto)

### Temas que cubre
1. Corrientes equivalentes de cargas en rotación (esfera, disco)
2. Ampère + superposición (cilindro con agujero)
3. Bobina / solenoide finito: B, K superficial, potencial vector A
4. Disco cargado rotante → B en eje y dipolo lejano
5. Cascarón esférico cargado rotante → A y B en todo el espacio
6. Potencial escalar magnético, contornos en cascaras
7. Cáscara de permeabilidad μ en campo externo (Jackson 5.12)
8. Imán cilíndrico: H, B, líneas
9. Esfera con M no uniforme + energía de interacción con espira
10. Identidades de energía magnetostática con M permanente

### Orden recomendado
- **Obligatorio:** 1 → 4 → 5 → 3a → 2 → 8
- **Importante:** 3b-c, 6, 9a-b
- **Si sobra tiempo:** 7, 9c-d, 10

### Por dónde empezamos
Problema 5 completo (a y b).

---

# Problema 5

**Enunciado (reformulado):** un cascarón esférico de radio \(R\) (el enunciado no escribe \(R\) explícitamente; lo introducimos nosotros: es el radio del cascarón), con densidad superficial de carga uniforme \(\sigma_0\), gira con velocidad angular constante \(\boldsymbol{\omega}\) alrededor de un eje por el centro.

- **a)** Hallar el potencial vector \(\mathbf{A}\) en todo el espacio.
- **b)** Hallar el campo de inducción \(\mathbf{B}\) en todo el espacio.

---

## 1. Qué pide

Querés el potencial vector magnético \(\mathbf{A}(\mathbf{r})\) y el campo \(\mathbf{B}(\mathbf{r})\) **adentro** y **afuera** del cascarón que gira cargado. No pide energía ni fuerzas: solo esos dos campos.

## 2. Idea central

La carga que gira se mueve → aparece una **corriente superficial** \(\mathbf{K}\) sobre la esfera.  
Esa \(\mathbf{K}\) es exactamente la misma que produciría una esfera con magnetización **uniforme** \(\mathbf{M}\).  
Con eso, \(\mathbf{A}\) se calcula (adentro lineal en \(r\), afuera como dipolo) y \(\mathbf{B}=\nabla\times\mathbf{A}\): uniforme adentro, dipolar afuera.

## 3. Herramientas previas

### (i) Corriente superficial de cargas en movimiento
Si hay carga superficial \(\sigma\) con velocidad \(\mathbf{v}\),
\[
\mathbf{K}=\sigma\,\mathbf{v}.
\]
**Por qué:** \(\mathbf{K}\) es corriente por unidad de ancho transversal; en un “anillo” de la esfera, la carga que pasa por un corte es \(\sigma\) veces la velocidad tangencial.

### (ii) Potencial vector en magnetostática (gauge de Coulomb)
\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]
**Por qué aplica:** magnetostática en el vacío, \(\nabla\cdot\mathbf{A}=0\), y acá las fuentes son solo superficiales.

### (iii) Equivalencia con magnetización uniforme
Una magnetización uniforme \(\mathbf{M}\) dentro de un volumen produce corriente de magnetización superficial
\[
\mathbf{K}_b=\mathbf{M}\times\hat{\mathbf{n}}.
\]
Si logramos que \(\mathbf{K}_b=\mathbf{K}\) del cascarón, el potencial \(\mathbf{A}\) (que solo “ve” corrientes) es el mismo.

### (iv) Rotacional en esféricas / dipolo magnético
- Si \(\mathbf{A}=A_\varphi(r,\theta)\,\hat{\boldsymbol{\varphi}}\), se usa \(\mathbf{B}=\nabla\times\mathbf{A}\) en coordenadas esféricas.
- Afuera, el campo de un dipolo \(\mathbf{m}\) es
\[
\mathbf{B}_{\mathrm{dip}}(\mathbf{r})=\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}.
\]

## 4. Setup

- **Datos:** \(\sigma_0\), \(\boldsymbol{\omega}\), radio del cascarón \(R\).
- **Hipótesis:** vacío (\(\mu_0\)); \(\sigma_0\) uniforme; \(\boldsymbol{\omega}\) constante; cascarón infinitamente fino; régimen magnetostático (velocidades no relativistas).
- **Diagrama mental:** esfera de radio \(R\); eje \(z\) = eje de rotación; un punto de la superficie en latitud \(\theta\) se mueve en dirección \(\hat{\boldsymbol{\varphi}}\).
- **Notación:**
  - \(\boldsymbol{\omega}=\omega\,\hat{\mathbf{z}}\)
  - \(\mathbf{r}=r\,\hat{\mathbf{r}}\) (punto de observación)
  - \(\mathbf{r}'\) sobre la superficie (\(r'=R\))
  - \(\theta\): ángulo polar respecto de \(\hat{\mathbf{z}}\)

## 5. Pasos numerados

1. Escribir la velocidad de cada punto de la superficie y obtener \(\mathbf{K}(\theta)\).
2. Identificar \(\mathbf{M}\) equivalente tal que \(\mathbf{M}\times\hat{\mathbf{r}}=\mathbf{K}\).
3. Calcular \(\mathbf{A}\) adentro (\(r<R\)) y afuera (\(r>R\)) usando esa equivalencia (y chequear con el rotacional).
4. Obtener \(\mathbf{B}=\nabla\times\mathbf{A}\) en ambas regiones.
5. Identificar el momento dipolar afuera y escribir \(\mathbf{B}\) en forma compacta.

## 6. Desarrollo completo

### Paso 1 — Corriente superficial \(\mathbf{K}\)

Un punto del cascarón está en \(\mathbf{r}'=R\,\hat{\mathbf{r}}'\). Su velocidad es
\[
\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}'.
\]
Con \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\) y en esféricas,
\[
|\boldsymbol{\omega}\times\mathbf{r}'|=\omega R\sin\theta,
\qquad
\hat{\mathbf{v}}=\hat{\boldsymbol{\varphi}},
\]
porque la rotación alrededor de \(z\) empuja en la dirección azimutal. Entonces
\[
\mathbf{v}=\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]
La corriente superficial es
\[
\mathbf{K}=\sigma_0\mathbf{v}=\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]
No hay corriente de volumen: \(\mathbf{J}=0\) para \(r\neq R\).

### Paso 2 — Magnetización equivalente

Para una esfera con magnetización **uniforme** \(\mathbf{M}=M\hat{\mathbf{z}}\) en \(r<R\) (y \(\mathbf{M}=0\) afuera),
\[
\mathbf{K}_b=\mathbf{M}\times\hat{\mathbf{n}}=\mathbf{M}\times\hat{\mathbf{r}}=M\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]
Igualando a nuestra \(\mathbf{K}\):
\[
M\sin\theta=\sigma_0\omega R\sin\theta
\quad\Rightarrow\quad
\mathbf{M}=\sigma_0 R\,\boldsymbol{\omega}=\sigma_0\omega R\,\hat{\mathbf{z}}.
\]
**Importante:** el cascarón real **no** está magnetizado; solo tiene \(\mathbf{K}\). Pero \(\mathbf{A}\) se obtiene integrando corrientes, así que \(\mathbf{A}\) coincide con el de esa esfera magnetizada.

### Paso 3 — Potencial vector \(\mathbf{A}\)

Para una esfera con \(\mathbf{M}\) uniforme, el potencial vector (gauge de Coulomb) es el de un dipolo “repartido”:

**Interior** (\(r<R\)):
\[
\mathbf{A}_{\mathrm{int}}(\mathbf{r})=\frac{\mu_0}{3}\,\mathbf{M}\times\mathbf{r}
=\frac{\mu_0}{3}\sigma_0 R\,(\boldsymbol{\omega}\times\mathbf{r}).
\]
En componentes esféricas (\(\boldsymbol{\omega}\times\mathbf{r}=\omega r\sin\theta\,\hat{\boldsymbol{\varphi}}\)):
\[
\mathbf{A}_{\mathrm{int}}=\frac{\mu_0\sigma_0\omega R}{3}\,r\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

**Exterior** (\(r>R\)): el momento dipolar total de la esfera magnetizada es
\[
\mathbf{m}=\frac{4\pi}{3}R^3\mathbf{M}=\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}},
\]
y
\[
\mathbf{A}_{\mathrm{ext}}(\mathbf{r})=\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\hat{\mathbf{r}}}{r^2}
=\frac{\mu_0\sigma_0\omega R^4}{3}\frac{\sin\theta}{r^2}\,\hat{\boldsymbol{\varphi}}.
\]
Equivale a
\[
\mathbf{A}_{\mathrm{ext}}=\frac{\mu_0}{3}\sigma_0 R^4\frac{\boldsymbol{\omega}\times\hat{\mathbf{r}}}{r^2}.
\]

**Por qué estas fórmulas de \(\mathbf{A}\):** salen de evaluar
\[
\mathbf{A}=\frac{\mu_0}{4\pi}\int\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'
\]
expandiendo \(1/|\mathbf{r}-\mathbf{r}'|\) en polinomios de Legendre. Por la dependencia \(\sin\theta'\) de \(\mathbf{K}\), **solo sobrevive el término dipolar** (\(l=1\)). Integrando ángulos queda exactamente lo de arriba. En el borde \(r=R\) ambas expresiones coinciden:
\[
A_\varphi\Big|_{r=R}=\frac{\mu_0\sigma_0\omega R^2}{3}\sin\theta.
\]

### Paso 4 — Campo \(\mathbf{B}=\nabla\times\mathbf{A}\)

**Interior.** Con \(A_r=A_\theta=0\) y \(A_\varphi=C\,r\sin\theta\), \(C=\mu_0\sigma_0\omega R/3\), el rotacional en esféricas da
\[
(\nabla\times\mathbf{A})_r=2C\cos\theta,
\quad
(\nabla\times\mathbf{A})_\theta=-2C\sin\theta,
\quad
(\nabla\times\mathbf{A})_\varphi=0.
\]
Como \(\hat{\mathbf{z}}=\cos\theta\,\hat{\mathbf{r}}-\sin\theta\,\hat{\boldsymbol{\theta}}\),
\[
\mathbf{B}_{\mathrm{int}}=\nabla\times\mathbf{A}_{\mathrm{int}}=2C\,\hat{\mathbf{z}}
=\frac{2\mu_0}{3}\sigma_0 R\,\boldsymbol{\omega}.
\]
Es un campo **uniforme**, paralelo a \(\boldsymbol{\omega}\).

**Exterior.** \(\mathbf{A}_{\mathrm{ext}}\) es el potencial vector de un dipolo \(\mathbf{m}\), por lo tanto
\[
\mathbf{B}_{\mathrm{ext}}(\mathbf{r})=\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3},
\]
con
\[
\mathbf{m}=\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}}.
\]
Explícitamente,
\[
\mathbf{B}_{\mathrm{ext}}=\frac{\mu_0\sigma_0\omega R^4}{3}\frac{2\cos\theta\,\hat{\mathbf{r}}+\sin\theta\,\hat{\boldsymbol{\theta}}}{r^3}.
\]

### Paso 5 — Continuidad / sentido físico

- \(A_\varphi\) es continuo en \(r=R\).
- La componente tangencial de \(\mathbf{B}/\mu_0\) salta con \(\mathbf{K}\times\hat{\mathbf{n}}\) (condición de frontera): coherente con \(\mathbf{K}=\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}\).
- A grandes distancias, \(\mathbf{B}\sim 1/r^3\): solo sobrevive el dipolo (no hay monopolo magnético).

## 7. Resultado final

Con \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\) y radio del cascarón \(R\):

**Corriente superficial**
\[
\mathbf{K}(\theta)=\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}.
\]

**a) Potencial vector**
\[
\mathbf{A}(\mathbf{r})=
\begin{cases}
\dfrac{\mu_0\sigma_0 R}{3}\,(\boldsymbol{\omega}\times\mathbf{r}), & r<R,\\[0.8em]
\dfrac{\mu_0\sigma_0 R^4}{3}\dfrac{\boldsymbol{\omega}\times\hat{\mathbf{r}}}{r^2}, & r>R.
\end{cases}
\]

**b) Campo \(\mathbf{B}\)**
\[
\mathbf{B}(\mathbf{r})=
\begin{cases}
\dfrac{2\mu_0}{3}\sigma_0 R\,\boldsymbol{\omega}, & r<R\quad\text{(uniforme)},\\[0.8em]
\dfrac{\mu_0}{4\pi}\dfrac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}, & r>R,
\end{cases}
\]
con momento dipolar
\[
\mathbf{m}=\frac{4\pi}{3}\sigma_0\omega R^4\,\hat{\mathbf{z}}.
\]

## 8. Chequeos

- **Caso \(\omega=0\):** \(\mathbf{K}=\mathbf{0}\Rightarrow\mathbf{A}=\mathbf{B}=\mathbf{0}\). OK.
- **Caso \(\sigma_0=0\):** igual. OK.
- **Eje (\(\theta=0\)):** \(K=0\) (el polo no se mueve); \(A_\varphi=0\) sobre el eje; \(\mathbf{B}_{\mathrm{int}}\) sigue paralelo a \(z\). OK.
- **Dimensiones:** \([\sigma_0\omega R]=(\mathrm{C/m^2})(1/\mathrm{s})(\mathrm{m})=\mathrm{A/m}=[K]\). \([\mathbf{B}]=\mu_0\cdot(\mathrm{A/m})\) OK.
- **Límite lejos:** \(B\sim\mu_0 m/r^3\) con \(m\sim\sigma_0\omega R^4\). Coherente con el Problema 4b (disco rotante → dipolo lejos).
- **Analogía con M:** \(\mathbf{B}_{\mathrm{int}}=\tfrac{2}{3}\mu_0\mathbf{M}\) es el resultado estándar de esfera uniformemente magnetizada.

## 9. Errores típicos de examen

- Olvidar el radio \(R\) en \(\mathbf{K}=\sigma_0(\boldsymbol{\omega}\times\mathbf{r})\) y poner \(\sigma_0\omega\sin\theta\) (faltan unidades).
- Usar \(\mathbf{B}=\mu_0\mathbf{M}\) adentro (eso sería “como en material sin desmagnetización”); acá es \(\tfrac{2}{3}\mu_0\mathbf{M}\).
- Confundir \(\mathbf{A}_{\mathrm{ext}}\propto 1/r^2\) con \(\mathbf{B}_{\mathrm{ext}}\propto 1/r^3\).
- Poner el dipolo como \(m=Q\omega R^2\) sin el factor geométrico \(\tfrac{4\pi}{3}R^4\sigma_0\).
- Calcular solo sobre el eje y decir que eso es “en todo el espacio”.
- Mezclar \(\mathbf{H}\) y \(\mathbf{B}\): en el vacío del problema, afuera \(\mathbf{B}=\mu_0\mathbf{H}\); adentro del cascarón hueco también hay vacío, \(\mathbf{B}=\mu_0\mathbf{H}\).

## 10. Mini-resumen para recordar

> Cascarón cargado que gira \(\Rightarrow\mathbf{K}=\sigma_0(\boldsymbol{\omega}\times\mathbf{R})=\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}\)  
> \(\Leftrightarrow\) esfera con \(\mathbf{M}=\sigma_0 R\boldsymbol{\omega}\)  
> \(\mathbf{A}\) dipolar (lineal adentro, \(\sim\sin\theta/r^2\) afuera)  
> \(\mathbf{B}\) **uniforme** adentro \(\tfrac{2}{3}\mu_0\mathbf{M}\), **dipolo** afuera con \(m=\tfrac{4\pi}{3}\sigma_0\omega R^4\).

---

## Siguiente paso lógico

- Si querés cerrar el círculo: **Problema 1a** (encontrar \(\mathbf{J}\) o \(\mathbf{K}\) de la esfera rotante; es el Paso 1 de este).
- Después natural: **Problema 4** (disco rotante: mismo espíritu, distinta geometría).
- O seguir con **5 → chequear condiciones de frontera** en \(r=R\) con detalle.
