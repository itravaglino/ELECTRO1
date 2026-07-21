# Sesión 2026-07-21 — Guía 7 EMI · Problema 5

**Materia:** Electromagnetismo I — Magnetostática  
**Material:** `tutor/inbox/Guia_7_EMI_730b.pdf`  
**Pedido:** Problema 5 completo (a y b), ZERO TO HERO, sin código

---

## Enunciado (reformulado)

Tenés un **cascarón esférico**: una esfera hueca de radio \(R\), con carga solo en la superficie, densidad superficial uniforme \(\sigma_0\). Ese cascarón **gira** alrededor de un eje que pasa por el centro, con velocidad angular constante \(\boldsymbol{\omega}\).

Pedidos:

- **(a)** potencial vector \(\mathbf{A}\) en un punto cualquiera del espacio
- **(b)** campo de inducción \(\mathbf{B}\) en un punto cualquiera del espacio

(El radio no aparece escrito en el enunciado; lo llamamos \(R\). Sin radio no hay longitud del sistema.)

---

## Temas de la guía (contexto breve)

Magnetostática: corrientes → \(\mathbf{A}\) → \(\mathbf{B}\); Ampère; multipolos magnéticos; cascarones.

### Orden recomendado (si estudian la guía entera)

- **Obligatorio:** 1, 2, 4, 5  
- **Importante:** 3, 6, 8  
- **Si sobra tiempo:** 7, 9, 10  

Acá resolvemos **solo el 5**.

---

# Problema 5 — Resolución ZERO TO HERO

## 1. Qué pide

En criollo: una esfera cargada en la superficie está girando. Eso mueve carga → hay **corriente superficial**. Esa corriente produce un campo magnético. Queremos:

1. el potencial vector \(\mathbf{A}\) (adentro y afuera),
2. el campo \(\mathbf{B}\) (adentro y afuera).

---

## 2. Idea central

La rotación convierte la carga superficial en una **corriente superficial** \(\mathbf{K}\).

En magnetostática, \(\mathbf{A}\) se obtiene integrando \(\mathbf{K}/|\mathbf{r}-\mathbf{r}'|\). Por simetría, esa corriente es “dipolar”: solo sobrevive el **momento magnético dipolar**. Entonces:

- **afuera** el sistema se ve como un **dipolo magnético**,
- **adentro** \(\mathbf{B}\) resulta **uniforme** (paralelo a \(\boldsymbol{\omega}\)).

No hace falta inventar magia: sale de la expansión de \(1/|\mathbf{r}-\mathbf{r}'|\) y de que \(\mathbf{K}\propto\sin\theta\,\hat{\boldsymbol{\varphi}}\).

---

## 3. Herramientas previas

### 3.1 Cascarón esférico y densidad superficial

Carga solo en \(r=R\). La densidad superficial \(\sigma_0\) es carga por unidad de área (C/m²), constante sobre toda la esfera.

### 3.2 Velocidad de un punto que rota

Si un punto tiene posición \(\mathbf{r}'\) y el cuerpo gira con \(\boldsymbol{\omega}\),

\[
\mathbf{v}(\mathbf{r}') = \boldsymbol{\omega}\times\mathbf{r}'.
\]

Justificación: \(\boldsymbol{\omega}\) apunta según el eje; el módulo de la velocidad es \(\omega\) veces la distancia al eje, \(\rho=R\sin\theta'\), y la dirección es tangencial (azimutal). Eso es exactamente \(\boldsymbol{\omega}\times\mathbf{r}'\).

### 3.3 Corriente superficial \(\mathbf{K}\)

\(\mathbf{K}\) es corriente por unidad de ancho transversal (A/m). Si hay carga superficial \(\sigma\) moviéndose con velocidad \(\mathbf{v}\),

\[
\mathbf{K} = \sigma\,\mathbf{v}.
\]

Intuición: en un “cortito” de ancho \(dl_\perp\), la carga que cruza por unidad de tiempo es \(\sigma\,v\,dl_\perp\), luego \(dI=\sigma v\,dl_\perp\), luego \(K=\sigma v\).

Acá: \(\mathbf{K}=\sigma_0(\boldsymbol{\omega}\times\mathbf{r}')\) sobre la superficie.

### 3.4 Potencial vector en magnetostática

En el gauge de Coulomb (\(\nabla\cdot\mathbf{A}=0\)), con corrientes estacionarias,

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{J}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,dV'.
\]

Si la corriente está solo en una superficie,

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

Y siempre:

\[
\mathbf{B}=\nabla\times\mathbf{A}.
\]

### 3.5 Expansión de \(1/|\mathbf{r}-\mathbf{r}'|\)

Con \(r_< =\min(r,r')\), \(r_>=\max(r,r')\),

\[
\frac{1}{|\mathbf{r}-\mathbf{r}'|}=\sum_{\ell=0}^{\infty}\frac{r_<^\ell}{r_>^{\ell+1}}P_\ell(\cos\gamma),
\]

donde \(\gamma\) es el ángulo entre \(\mathbf{r}\) y \(\mathbf{r}'\). En la esfera, \(r'=R\), así que:

- afuera (\(r>R\)): \(r_<=R\), \(r_>=r\) → potencias \(R^\ell/r^{\ell+1}\)
- adentro (\(r<R\)): \(r_<=r\), \(r_>=R\) → potencias \(r^\ell/R^{\ell+1}\)

### 3.6 Momento magnético de una distribución localizada

\[
\mathbf{m}=\frac{1}{2}\int\mathbf{r}'\times\mathbf{J}\,dV'
\quad\Rightarrow\quad
\mathbf{m}=\frac{1}{2}\int\mathbf{r}'\times\mathbf{K}\,da'
\]

(si solo hay corriente superficial). A grandes distancias,

\[
\mathbf{A}(\mathbf{r})\simeq\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\hat{\mathbf{r}}}{r^2}=\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\mathbf{r}}{r^3},
\]

\[
\mathbf{B}(\mathbf{r})\simeq\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}.
\]

En **este** problema, esa forma dipolar es exacta en todo el exterior (no solo “muy lejos”), porque los multipolos superiores se anulan.

---

## 4. Setup

**Datos / notación**

| Símbolo | Significado |
|--------|-------------|
| \(R\) | radio del cascarón |
| \(\sigma_0\) | densidad superficial de carga (uniforme) |
| \(\boldsymbol{\omega}\) | velocidad angular (constante); tomamos \(\boldsymbol{\omega}=\omega\,\hat{\mathbf{z}}\) |
| \(\mathbf{r}\) | punto de observación |
| \(\mathbf{r}'\) | punto fuente (sobre la esfera, \(r'=R\)) |
| \(\theta,\varphi\) | ángulos esféricos de \(\mathbf{r}\) |
| \(\mu_0\) | permeabilidad del vacío |

**Hipótesis**

- Magnetostática: \(\boldsymbol{\omega}\) constante ⇒ corriente estacionaria.
- Espacio vacío (\(\mu=\mu_0\)) adentro y afuera; el cascarón es infinitamente fino.
- No hay corrientes de volumen: solo \(\mathbf{K}\) en \(r=R\).

**Diagrama mental**

```
        ω ↑ (eje z)
          |
      .---+---.   cascarón r = R, carga σ₀
     /    |    \  puntos de la superficie van en φ̂
    |     •     | centro
     \    |    /
      '---+---'
          |
```

En el ecuador (\(\theta=\pi/2\)) la velocidad es máxima: \(v=\omega R\). En los polos, \(v=0\).

---

## 5. Pasos numerados

1. Encontrar la corriente superficial \(\mathbf{K}\).
2. Calcular el momento magnético \(\mathbf{m}\).
3. Plantear \(\mathbf{A}\) como integral de \(\mathbf{K}\) y usar simetría + expansión.
4. Obtener \(\mathbf{A}\) adentro y afuera.
5. Calcular \(\mathbf{B}=\nabla\times\mathbf{A}\) en ambas regiones.
6. Chequear continuidad / salto en \(r=R\) y el límite lejano.

---

## 6. Desarrollo completo

### Paso 1 — Corriente superficial

Sobre la superficie, \(\mathbf{r}'=R\hat{\mathbf{r}}'\). Entonces

\[
\mathbf{v}=\boldsymbol{\omega}\times\mathbf{r}'
=\omega R\sin\theta'\,\hat{\boldsymbol{\varphi}}'.
\]

Luego

\[
\mathbf{K}(\theta')=\sigma_0\mathbf{v}
=\sigma_0\omega R\sin\theta'\,\hat{\boldsymbol{\varphi}}'.
\]

Observaciones:

- \(\mathbf{K}\) apunta en \(\hat{\boldsymbol{\varphi}}\) (círculos de latitud).
- Depende de \(\theta'\): máxima en el ecuador, nula en los polos.
- Es la misma familia de corrientes que produce un dipolo a lo largo de \(z\).

En forma vectorial compacta (útil después):

\[
\mathbf{K}=\sigma_0\,(\boldsymbol{\omega}\times\mathbf{r}')\Big|_{r'=R}.
\]

---

### Paso 2 — Momento magnético \(\mathbf{m}\)

\[
\mathbf{m}=\frac{1}{2}\int\mathbf{r}'\times\mathbf{K}\,da'
=\frac{1}{2}\sigma_0\int\mathbf{r}'\times(\boldsymbol{\omega}\times\mathbf{r}')\,da'.
\]

Identidad vectorial:

\[
\mathbf{a}\times(\mathbf{b}\times\mathbf{c})=\mathbf{b}(\mathbf{a}\cdot\mathbf{c})-\mathbf{c}(\mathbf{a}\cdot\mathbf{b}),
\]

con \(\mathbf{a}=\mathbf{r}'\), \(\mathbf{b}=\boldsymbol{\omega}\), \(\mathbf{c}=\mathbf{r}'\):

\[
\mathbf{r}'\times(\boldsymbol{\omega}\times\mathbf{r}')
=\boldsymbol{\omega}\,(\mathbf{r}'\cdot\mathbf{r}')-\mathbf{r}'\,(\boldsymbol{\omega}\cdot\mathbf{r}')
=\boldsymbol{\omega}\,R^2-\mathbf{r}'\,(\boldsymbol{\omega}\cdot\mathbf{r}').
\]

Entonces

\[
\mathbf{m}=\frac{1}{2}\sigma_0\int\Big(\boldsymbol{\omega}\,R^2-\mathbf{r}'(\boldsymbol{\omega}\cdot\mathbf{r}')\Big)\,da'.
\]

Área total: \(\int da'=4\pi R^2\), luego el primer término es

\[
\frac{1}{2}\sigma_0\,\boldsymbol{\omega}\,R^2\cdot 4\pi R^2
=2\pi\sigma_0 R^4\,\boldsymbol{\omega}.
\]

Para el segundo: con \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\),

\[
\int\mathbf{r}'(\boldsymbol{\omega}\cdot\mathbf{r}')\,da'
=\omega\int\mathbf{r}'\,z'\,da'.
\]

Por simetría, \(\int x'z'\,da'=0\), \(\int y'z'\,da'=0\). Solo queda la componente \(z\):

\[
\int (z')^2\,da'
=R^4\int\cos^2\theta'\,d\Omega'
=R^4\int_0^{2\pi}d\varphi'\int_0^\pi\cos^2\theta'\sin\theta'\,d\theta'.
\]

Con \(u=\cos\theta'\), \(du=-\sin\theta'd\theta'\),

\[
\int_{-1}^{1}u^2\,du=\frac{2}{3}
\quad\Rightarrow\quad
\int\cos^2\theta'\,d\Omega'=2\pi\cdot\frac{2}{3}=\frac{4\pi}{3}.
\]

Así

\[
\int\mathbf{r}'(\boldsymbol{\omega}\cdot\mathbf{r}')\,da'=\frac{4\pi}{3}R^4\,\boldsymbol{\omega}.
\]

Luego

\[
\mathbf{m}=\frac{1}{2}\sigma_0\left(4\pi R^4\boldsymbol{\omega}-\frac{4\pi}{3}R^4\boldsymbol{\omega}\right)
=\frac{1}{2}\sigma_0\cdot\frac{8\pi}{3}R^4\boldsymbol{\omega}
=\frac{4\pi}{3}\sigma_0 R^4\,\boldsymbol{\omega}.
\]

**Resultado intermedio:**

\[
\boxed{\mathbf{m}=\dfrac{4\pi}{3}\,\sigma_0 R^4\,\boldsymbol{\omega}}
\]

---

### Paso 3 — Estrategia para \(\mathbf{A}\)

Hay que evaluar

\[
\mathbf{A}(\mathbf{r})=\frac{\mu_0}{4\pi}\int\frac{\mathbf{K}(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}\,da'.
\]

Simetría axial + \(\mathbf{K}\parallel\hat{\boldsymbol{\varphi}}\) ⇒ \(\mathbf{A}\) solo tiene componente azimutal:

\[
\mathbf{A}=A_\varphi(r,\theta)\,\hat{\boldsymbol{\varphi}}.
\]

Además, \(\mathbf{K}\propto\sin\theta'\,\hat{\boldsymbol{\varphi}}'\) es proporcional a la dependencia angular de un **dipolo**. Al expandir \(1/|\mathbf{r}-\mathbf{r}'|\) en Legendre, **solo contribuye \(\ell=1\)**. Por eso:

- el exterior es **exactamente** el de un dipolo \(\mathbf{m}\),
- el interior es lineal en \(\mathbf{r}\) (campo \(\mathbf{B}\) uniforme).

Una forma equivalente y limpia de escribir candidatos (motivados por esa simetría) es:

\[
\mathbf{A}(\mathbf{r})=
\begin{cases}
f_{\mathrm{in}}(r)\,(\boldsymbol{\omega}\times\mathbf{r}), & r<R,\\[4pt]
f_{\mathrm{out}}(r)\,(\boldsymbol{\omega}\times\mathbf{r}), & r>R.
\end{cases}
\]

Con la expansión \(\ell=1\) se fija \(f\). El atajo consistente (y estándar) es:

1. afuera: usar la fórmula dipolar exacta con el \(\mathbf{m}\) ya calculado;
2. adentro: exigir continuidad de \(\mathbf{A}\) en \(r=R\) (no hay capa infinita de \(\mathbf{A}\); \(\mathbf{A}\) es continuo) y la forma lineal que da \(\nabla\times\mathbf{A}\) uniforme.

---

### Paso 4 — Potencial vector \(\mathbf{A}\)

#### Exterior (\(r>R\))

Como solo hay dipolo,

\[
\mathbf{A}_{\mathrm{ext}}(\mathbf{r})
=\frac{\mu_0}{4\pi}\frac{\mathbf{m}\times\mathbf{r}}{r^3}
=\frac{\mu_0}{4\pi}\cdot\frac{4\pi}{3}\sigma_0 R^4\frac{\boldsymbol{\omega}\times\mathbf{r}}{r^3}
=\frac{\mu_0\sigma_0 R^4}{3}\frac{\boldsymbol{\omega}\times\mathbf{r}}{r^3}.
\]

#### Interior (\(r<R\))

La contribución \(\ell=1\) de la expansión, con \(r_<=r\) y \(r_>=R\), produce un factor \(\propto r\) (en vez de \(\propto 1/r^2\)). El resultado es

\[
\mathbf{A}_{\mathrm{int}}(\mathbf{r})
=\frac{\mu_0\sigma_0 R}{3}\,(\boldsymbol{\omega}\times\mathbf{r}).
\]

**Continuidad en \(r=R\)** (chequeo inmediato):

\[
\mathbf{A}_{\mathrm{int}}(R)
=\frac{\mu_0\sigma_0 R}{3}(\boldsymbol{\omega}\times\mathbf{r})\Big|_{r=R},
\]

\[
\mathbf{A}_{\mathrm{ext}}(R)
=\frac{\mu_0\sigma_0 R^4}{3}\frac{\boldsymbol{\omega}\times\mathbf{r}}{R^3}
=\frac{\mu_0\sigma_0 R}{3}(\boldsymbol{\omega}\times\mathbf{r})\Big|_{r=R}.
\]

Coinciden. Bien.

En componentes esféricas (\(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\)):

\[
\boldsymbol{\omega}\times\mathbf{r}=\omega r\sin\theta\,\hat{\boldsymbol{\varphi}},
\]

luego

\[
A_\varphi^{\mathrm{int}}=\frac{\mu_0\sigma_0\omega R}{3}\,r\sin\theta,
\qquad
A_\varphi^{\mathrm{ext}}=\frac{\mu_0\sigma_0\omega R^4}{3}\,\frac{\sin\theta}{r^2}.
\]

---

### Paso 5 — Campo \(\mathbf{B}=\nabla\times\mathbf{A}\)

#### Interior

Con \(\boldsymbol{\omega}=\omega\hat{\mathbf{z}}\),

\[
\mathbf{A}_{\mathrm{int}}=\frac{\mu_0\sigma_0 R\omega}{3}(-y,\,x,\,0).
\]

El rotor en cartesianas:

\[
(\nabla\times\mathbf{A})_z
=\partial_x A_y-\partial_y A_x
=\frac{\mu_0\sigma_0 R\omega}{3}-\left(-\frac{\mu_0\sigma_0 R\omega}{3}\right)
=\frac{2\mu_0\sigma_0 R\omega}{3},
\]

y las otras componentes dan cero. Por lo tanto

\[
\mathbf{B}_{\mathrm{int}}=\frac{2}{3}\mu_0\sigma_0 R\,\boldsymbol{\omega}.
\]

Campo **uniforme**, paralelo a \(\boldsymbol{\omega}\).

#### Exterior

Es el campo de un dipolo \(\mathbf{m}\):

\[
\mathbf{B}_{\mathrm{ext}}(\mathbf{r})
=\frac{\mu_0}{4\pi}\frac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3},
\]

con \(\mathbf{m}=(4\pi/3)\sigma_0 R^4\boldsymbol{\omega}\). Explícitamente:

\[
\mathbf{B}_{\mathrm{ext}}
=\frac{\mu_0\sigma_0 R^4}{3}
\frac{3(\boldsymbol{\omega}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\boldsymbol{\omega}}{r^3}.
\]

(Si preferís en \(r\): reemplazá \(\hat{\mathbf{r}}=\mathbf{r}/r\) y queda el cociente sobre \(r^5\) en la forma usual.)

---

### Paso 6 — Condiciones de borde en \(r=R\) (por qué es coherente)

Con \(\hat{\mathbf{n}}=\hat{\mathbf{r}}\) saliendo del cascarón:

1. **\(B_r\) continuo** (no hay monopolos magnéticos).  
   En \(r=R\), la componente radial del dipolo exterior coincide con la del interior uniforme proyectada: ambas dan

   \[
   B_r\Big|_{r=R}=\frac{2}{3}\mu_0\sigma_0 R\,(\boldsymbol{\omega}\cdot\hat{\mathbf{r}}).
   \]

2. **Salto de la componente tangencial** ligado a \(\mathbf{K}\):

   \[
   \hat{\mathbf{r}}\times\big(\mathbf{B}_{\mathrm{ext}}-\mathbf{B}_{\mathrm{int}}\big)=\mu_0\mathbf{K}.
   \]

   Eso se satisface con \(\mathbf{K}=\sigma_0\omega R\sin\theta\,\hat{\boldsymbol{\varphi}}\) y los \(\mathbf{B}\) de arriba (es el chequeo estándar de este problema clásico).

---

## 7. Resultado final

Con \(\displaystyle\mathbf{m}=\frac{4\pi}{3}\sigma_0 R^4\boldsymbol{\omega}\):

**(a) Potencial vector**

\[
\boxed{
\mathbf{A}(\mathbf{r})=
\begin{cases}
\dfrac{\mu_0\sigma_0 R}{3}\,(\boldsymbol{\omega}\times\mathbf{r}), & r<R,\\[10pt]
\dfrac{\mu_0\sigma_0 R^4}{3}\,\dfrac{\boldsymbol{\omega}\times\mathbf{r}}{r^3}
=\dfrac{\mu_0}{4\pi}\dfrac{\mathbf{m}\times\mathbf{r}}{r^3}, & r>R.
\end{cases}
}
\]

**(b) Campo \(\mathbf{B}\)**

\[
\boxed{
\mathbf{B}(\mathbf{r})=
\begin{cases}
\dfrac{2}{3}\mu_0\sigma_0 R\,\boldsymbol{\omega}, & r<R,\\[10pt]
\dfrac{\mu_0}{4\pi}\dfrac{3(\mathbf{m}\cdot\hat{\mathbf{r}})\hat{\mathbf{r}}-\mathbf{m}}{r^3}, & r>R.
\end{cases}
}
\]

---

## 8. Chequeos

- **Caso \(\omega=0\):** no hay corriente ⇒ \(\mathbf{A}=\mathbf{0}\), \(\mathbf{B}=\mathbf{0}\). OK.
- **Caso \(\sigma_0=0\):** igual. OK.
- **Muy lejos:** \(\mathbf{B}\sim 1/r^3\), típico de dipolo. OK.
- **Continuidad de \(\mathbf{A}\) en \(r=R\):** verificada arriba.
- **Dimensiones:** \(\sigma_0\omega R\) tiene unidades de \(K\) (A/m). \(\mu_0 K\) tiene unidades de \(B\). Adentro \(B\sim\mu_0\sigma_0\omega R\): consistente.
- **Analogía útil (no sustituye la cuenta):** una esfera uniformemente magnetizada con magnetización \(\mathbf{M}\) equivalente produce adentro \(\mathbf{B}=(2/3)\mu_0\mathbf{M}\). Acá el cascarón rotante “imita” \(M_{\mathrm{eq}}=\sigma_0 R\omega\) en el sentido de que \(B_{\mathrm{int}}=(2/3)\mu_0\sigma_0 R\omega\). La analogía se entiende después; no la uses como justificación primaria en el examen sin derivar \(\mathbf{K}\) y \(\mathbf{m}\).

---

## 9. Errores típicos de examen

- Olvidar que la velocidad es \(\boldsymbol{\omega}\times\mathbf{r}\) y poner \(v=\omega R\) en todos lados (solo vale en el ecuador).
- Confundir \(\mathbf{K}=\sigma\mathbf{v}\) con densidad volumétrica \(\mathbf{J}\).
- Usar la fórmula dipolar **adentro** (no vale): adentro \(\mathbf{B}\) es uniforme, no dipolar.
- Perder el factor \(4\pi/3\) en \(\mathbf{m}\) (suele salir mal el \(\int\cos^2\theta\,d\Omega=4\pi/3\)).
- Escribir \(\mathbf{B}=\nabla\times\mathbf{A}\) pero calcular solo \(A_\varphi\) y olvidar la expresión correcta del rotor en esféricas (por eso conviene chequear el interior en cartesianas).
- Decir “como el problema 1” y copiar \(\mathbf{J}\) de la esfera **maciza** superficial sin pasar por \(\mathbf{K}\) del cascarón (el 1a es el mismo \(\mathbf{K}\); el 5 pide \(\mathbf{A}\) y \(\mathbf{B}\)).

---

## 10. Mini-resumen para recordar

1. Cascarón cargado que gira ⇒ \(\mathbf{K}=\sigma_0(\boldsymbol{\omega}\times\mathbf{r})\).  
2. Eso tiene momento \(\mathbf{m}=(4\pi/3)\sigma_0 R^4\boldsymbol{\omega}\).  
3. Afuera: dipolo puro en \(\mathbf{A}\) y \(\mathbf{B}\).  
4. Adentro: \(\mathbf{A}\propto\boldsymbol{\omega}\times\mathbf{r}\) y \(\mathbf{B}=(2/3)\mu_0\sigma_0 R\boldsymbol{\omega}\) (uniforme).

---

## Siguiente paso lógico

- Si querés afianzar: rehacer **solo el cálculo de \(\mathbf{m}\)** y el \(\mathbf{B}\) interior a partir de \(\mathbf{A}\), sin mirar.  
- Siguiente de la guía que encaja: **Problema 6** (cascarón con \(\mathbf{B}\) interior dado; Maxwell + \(\Phi\) magnético + corrientes).  
- Variante: comparar con el **Problema 4** (disco rotante) en el eje: misma idea “carga que se mueve ⇒ corriente ⇒ \(\mathbf{B}\)”, geometría distinta.
