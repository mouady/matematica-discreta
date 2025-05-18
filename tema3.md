## Tema 3

### 1. Definición de Árbol

* **Árbol**: Grafo *conexo* y *sin ciclos*.

---

### 2. Propiedades Fundamentales

1. Existe un **único camino** entre cualesquiera dos vértices.
2. Si se **añade una arista**, se forma un **ciclo**, y **deja de ser árbol**.
3. Si se **elimina una arista**, el grafo se parte en **dos componentes conexas**, cada una de ellas es un árbol.
4. Para **añadir un vértice** y que siga siendo un árbol, se debe conectar mediante **una única arista**.
5. Un árbol con $|V|$ vértices tiene $|A| = |V| - 1$ aristas.

---

### 3. Caracterizaciones Equivalentes

Las siguientes afirmaciones son equivalentes:

1. $T = (V, A)$ es un árbol.
2. Existe un único camino entre cada par de vértices de T.
3. T es conexo y $|A| = |V| - 1$.
4. T es acíclico y $|A| = |V| - 1$.

---

### 4. Bosque

* **Bosque**: Grafo *disconexo* y sin ciclos.
* Es decir, cada componente conexa de un bosque es un árbol.

---

### 5. Árbol Enraizado

* Árbol con un **vértice raíz** marcado.
* Los vértices se **organizan por niveles**. Ojo! Empezar a contar desde 0.
* Conceptos:

  * **Raíz**: vértice inicial desde donde se organiza el árbol.
  * **Padre / Hijo**: relación entre vértices conectados directamente desde un nivel superior (i) al siguiente (i+1).
  * **Ascendiente / Descendiente**: relación jerárquica entre vértices de distintos niveles.
  * **Hermanos**: vértices que tienen el mismo padre.
  * **Hoja**: vértice sin hijos (terminal).
  * **Altura**: distancia (en número de niveles) desde la raíz hasta la hoja más lejana (el mayor nivel que existe).

---

### 6. Árboles m-arios

* **Árbol m-ario**: todos los vértices internos tienen exactamente $m$ hijos.
* **Árbol m-ario completo**: si además todas las hojas están en el mismo nivel.

#### Fórmulas:

1. Número de hojas:

   $$
   x \leq m^h \quad \text{o equivalentemente} \quad h \geq \log_m x
   $$

   donde:

   * $x$: número de hojas
   * $h$: altura

2. Número total de vértices:

   $$
   |V| = mi + 1
   $$

   donde:

   * $i$: número de vértices internos

3. En un árbol binario:

   $$
   |V| = 2i + 1, \quad \text{con } i \text{ internos, } i+1 \text{ hojas}
   $$

---

### 7. Árboles de Decisión

* Árbol enraizado donde:

  * Vértices internos = **comprobaciones o decisiones**
  * Aristas = **resultados de la comprobación**
  * Hojas = **conclusiones finales**

---

### 8. Árboles Recubridores

* **Subgrafo recubridor**: subgrafo que contiene todos los vértices del grafo original. (subgrafo conexo)
* Si es un **árbol**, se llama **árbol recubridor**. (+ sin ciclos)
* Si el grafo es disconexo, obtenemos un **bosque recubridor**. (las cc son arboles recubridores)

#### Algoritmos para construir árboles recubridores:

1. **DFS (Depth First Search)**

   * Usa **pila (LIFO)**.
   * Explora hasta el fondo antes de retroceder.

2. **BFS (Breadth First Search)**

   * Usa **cola (FIFO)**.

   * Explora por niveles.

* Observación: Ambos algoritmos son válidos también para grafos dirigidos.

---

### 8.1. Algoritmo BFS (Búsqueda en anchura)

**Objetivo:** Obtener caminos más cortos desde un vértice inicial (en G no ponderado), detectar componentes conexas y recorrer grafos por niveles.

**Procedimiento:**

1. Establecer un orden en los vértices del grafo.
2. Seleccionar un vértice inicial $v$.
3. Visitar todos los vértices vecinos inmediatos de $v$.
4. Continuar con los vecinos de los vecinos, y así sucesivamente, por niveles.
5. Marcar los vértices visitados.
6. Si quedan vértices sin visitar, reiniciar desde otro vértice no visitado.

**Resultado:** Se obtiene un subgrafo llamado "árbol de expansión" o "árbol de búsqueda en anchura" correspondiente a una componente conexa del grafo.

**Observaciones:**

* Se utiliza una cola (FIFO) para gestionar los vértices pendientes de explorar.
* Ideal para encontrar caminos más cortos en grafos no ponderados.
* El recorrido depende del orden de los vértices.

---

### 8.2. Aplicaciones de DFS y BFS

**Aplicaciones del DFS (Depth First Search):**

* Determinar si un grafo es conexo / Detectar **componentes conexas** en grafos disconexos.
* Hallar **componentes fuertemente conexas** en digrafos (TARJAN).
* Encontrar **vértices de corte**: V es VDC <=>  DFS con raiz en V tiene más de un hijo.
* Recorrido útil para **escapar de un laberinto** (explora un camino hasta el final y retrocede si es necesario).

**Aplicaciones del BFS (Breadth First Search):**

* Encontrar **caminos más cortos** en grafos no ponderados.
* Resolver problemas tipo **laberinto** encontrando la salida por el CAMINO MÁS CORTO.

Los 2 sirven para:

* Hallar componentes conexas => Conseguir bosques recubridores

**Observación:** Si al aplicar DFS o BFS no se alcanzan todos los vértices, el grafo no es conexo. Los vértices alcanzados forman una **componente conexa**, y se puede aplicar el algoritmo nuevamente para encontrar las demás.

---

### 9. Árboles Recubridores en Grafos Ponderados

#### Tipos:

1. **Árbol recubridor de peso mínimo**:

   * Minimiza la suma total de pesos.
   * Algoritmo clásico: **Kruskal**: Añadimos las aristas ordenadas en orden decreciente de peso siempre que no generen ciclos hasta que sea conexo (algoritmo voraz).
   * **No garantiza caminos más cortos entre vértices.**

2. **Árbol recubridor de camino mínimo**:

   * Desde una **raíz dada**, da los caminos más cortos al resto.
   * Algoritmo: **Dijkstra**
   * **No garantiza caminos mínimos entre cualquier par de vértices.**
   añadir clase

---

### 10. Distancias en Grafos

* **Distancia** $d(u, v)$: es la longitud del camino más corto que une los vértices $u$ y $v$.

  * En grafos simples (no ponderados), la longitud del camino es el número de aristas.
  * En grafos ponderados, la longitud de un camino es la suma de los pesos de sus aristas.
* **Excentricidad** de un vértice $v \in V$:
* **Radio**: $\min_{v \in V} e(v)$
* **Diámetro**: $\max_{v \in V} e(v)$