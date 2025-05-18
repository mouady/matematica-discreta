## Tema 5 Parte 1: Coloreado

### 1.1 Definición:

Una k-coloración es una coloración que utiliza exactamente 𝑘 colores distintos.

Una *k-coloración por vértices* es una función $c : V \to \mathbb{N}$ tal que $c(u) \ne c(v)$ si $u$ y $v$ son adyacentes.

### 1.2 Número cromático:

$\chi(G)$ = número cromático = mínimo número de colores en una coloración válida de vértices.

### 1.3 Propiedades:

* $\chi(G) \leq |V|$
* Si $G'$ es subgrafo de $G$, entonces $\chi(G') \leq \chi(G)$
* Si $G$ no es conexo, $\chi(G) = \max\{\chi(G_1), \ldots, \chi(G_c)\}$ con $G_1,\ldots,G_c$ componentes conexas.
* $\chi(G) = 1 \iff G$ sin aristas.
* $\chi(G) = 2 \iff G$ es bipartito.

### 1.4 Casos particulares:

* **Grafo completo $K_n$**: $\chi(K_n) = n$
* **Ciclo $C_n$**:

  * Si $n$ par: $\chi(C_n) = 2$
  * Si $n$ impar: $\chi(C_n) = 3$

* **Triangulo**: Se necesitan 3 colorse para colorear un triangulo.
### 1.5 Observación:
* Una coloración por vértices induce una partición del conjunto 𝑉 de vértices en 𝑘 conjuntos independientes, donde los vértices de cada conjunto tienen el mismo color y no son adyacentes entre sí.


## ⚙️ 1.5 Algoritmo voraz (coloración de vértices)

### 1.5.1 Procedimiento:

1. Fijar orden de los vértices.
2. Asignar a cada vértice el primer color disponible.

### 1.5.2 Observaciones:

* Podemos obtener distintas coloraciones (y distinto número de colores) con distintos órdenes para el conjunto de vértices.
* Da una coloracion, pero no garantiza usar el mínimo número de colores. A no ser que ejecutemos el algoritmo $|V|!$ veces y nos quedemos con el menor número de colores.


## 📐 1.6 Caracterización de grafos bipartitos

### 1.6.1 Teoremas equivalentes:

$G$ es bipartito $\iff \chi(G) = 2$ $\iff G$ no tiene ciclos impares


### 1.6.2 [Friki] Demostración estructural (niveles):

* Representar $G$ por niveles.
* Vértices en niveles pares $\leftrightarrow$ color 1
* Vértices en niveles impares $\leftrightarrow$ color 2


## 🔺 1.7 Cotas para el número cromático

### 1.7.1 Teoremas:

* $\chi(G) \leq \Delta + 1$, donde $\Delta$ es el grado máximo de $G$.

* **Teorema de Brooks**: Si $G$ no es un grafo completo ni un ciclo impar, entonces $\chi(G) \leq \Delta$


## 🎨 2. Coloreado de aristas

### 2.1 Definición:

Una *k-coloración por aristas* es una función
$c : E \to \mathbb{N}$ tal que $c(e) \ne c(e')$ si $e$ y $e'$ son incidentes.



## 🔢 2.2 Índice cromático

### 2.2.1 Definición:

$\chi_1(G)$ = índice cromático = mínimo número de colores necesarios para una coloración por aristas.

### 2.2.2 Cotas:

**Teorema de Vizing**:
$\Delta \leq \chi_1(G) \leq \Delta + 1$

### 2.2.3 Casos particulares:

* $\chi_1(K_n) = \begin{cases} n - 1, & \text{si } n \text{ par} \\ n, & \text{si } n \text{ impar} \end{cases}$
* Para grafos bipartitos: $\chi_1(G) = \Delta$


## ⚙️ 2.3 Algoritmo voraz (coloración por aristas)

### 2.3.1 Procedimiento:

1. Establecer un orden en las aristas.
2. Asignar a cada arista el primer color disponible.

### 2.3.2 Observaciones:

* Aplican las mismas que en el caso del Algoritmo de Coloreado de Vertices pero con las aristas.


## 🔗 3. Grafo de línea $L(G)$

### 3.1 Definición:

Sea $G = (V, E)$ un grafo.

El *grafo de línea* de $G$, denotado por $L(G) = (V', E')$, es un grafo donde:

* Los vértices de $L(G)$ son las aristas de $G$: $V' = E$.
* Dos vértices $e, e' \in V'$ son adyacentes en $L(G)$ si y solo si las aristas $e$ y $e'$ son incidentes en un mismo vértice de $G$.

Es decir, $e \sim e' \iff e \cap e' \ne \emptyset$ en $G$.

### 3.2 Propiedades:

* Una coloración por aristas de $G$ es equivalente a una coloración por vértices de su grafo de línea $L(G)$.

* El índice cromático de $G$ es igual al número cromático de $L(G)$:

  $$
  \chi_1(G) = \chi(L(G))
  $$

* Nos viene a decir que el problema de encontrar una coloracion por vertices es equivalente al problema de las aristas
