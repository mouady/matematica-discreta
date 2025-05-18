## Tema 2

### 1. Grafos Conexos

**Definiciones:**

* Camino: Secuencia de aristas en la que cada una es incidente en el siguiente vértice.
* Grafo conexo: Un grafo G es conexo si existe un camino entre cualquier par de vértices.

**Observaciones:**

* Si no es conexo, se dice disconexo.
* Los subgrafos conexos máximos de G se llaman componentes conexas.
* (si G es conexo entonces tiene una única componente conexa que es el propio G)

---

### 2. Conexión en la Matriz de Adyacencia

* $A[i][j] = 1$ si los vértices $i$ y $j$ son adyacentes; $0$ en caso contrario.
* $A^k[i][j]$: Número de caminos de longitud $k$ entre $i$ y $j$. (Recordar  Lab 2)

**Propiedad:**

* $G$ es conexo $\Leftrightarrow$ Para toda pareja de vértices $i, j$, existe $k$ tal que $A^k[i][j] != 0$.

---

### 3. Algoritmo DFS (Búsqueda en profundidad)

**Objetivo:** Detectar componentes conexas. También es la misma estrategia para escapar de un laberinto

**Procedimiento:**

1. Establecer un orden en los vértices del grafo.
2. Selecciona un vértice $v$.
3. Explora los vértices en ese orden hasta que te ves obligado a retroceder.
4. Marca los vértices visitados.
5. Repetir desde otro vértice si quedan sin visitar.

**Resultado:** Se obtiene un subgrafo del grafo original $G$ que contiene todos sus vértices, llamado "árbol de expansión" o "árbol de búsqueda en profundidad", correspondiente a una componente conexa.

**Observaciones:**

* Los subgrafos obtenidos mediante DFS dependen del orden elegido en los vértices.
* Si al terminar un recorrido DFS no se han visitado todos los vértices, es necesario iniciar otro DFS desde un vértice no visitado. Esto indica que el grafo es disconexo.

---

### 4. Conexión en Dígrafos

**Tipos:**

* Fuertemente conexo: Hay camino de i a j y de j a i. (Dos sentidos)
* Unilateralmente conexo: Hay camino de i a j o de j a i. (Un solo sentido)
* Débilmente conexo: Es conexo si nos olvidamos del sentido de las aristas.

**Observación:**

* Estas definiciones no son excluyentes; un mismo dígrafo puede ser, por ejemplo, débil y unilateralmente conexo pero no fuertemente conexo.&#x20;

---

### 5. Algoritmo de Tarjan

**Objetivo:** Sirve para hallar las componentes fuertemente conexas de un dígrafo

**Pasos:**

1. Realizar DFS sobre G, creando una lista L (de inicio a final) en la que se van añadiendo los vértices conforme se quedan sin vecinos no visitados ("o cuando tengo que retroceder").
2. Calcular el grafo traspuesto $G^T$: invirtiendo sentido de las aristas en G.
3. Realizar DFS en $G^T$, usando el orden inverso de L (desde el final hasta el inicio).

**Resultado:** Componentes fuertemente conexas.

---

### 6. k-Conectividad por Vértices

**Definiciones:**

* Vértice de corte (V.D.C): Su eliminación desconecta G o lo trivializa.
* $k(G)$: Mínimo número (exacto) de vértices que hay que eliminar para desconectar G (o para que G sea trivial).
* Bloques de un grafo: son los mayores subgrafos que son 2-conexos (Recordar Lab 2)
* Caminos disjuntos: Dos caminos entre dos vértices x,y si no tienen vértices en común (excepto x,y)

**Propiedades:**

* Si G es disconexo, entonces $k(G) = 0$.
* G es $r$-conexo si $k(G) \geq r$: es decir, si elimino MENOS DE r vértices G sigue siendo conexo

**Observación:**

* No se debe decir "v₁ y v₂ son vdc's". En su lugar, se debe decir "{v₁, v₂} es un conjunto  de corte".

**Teorema de Menger:**

* $G$ es $r$-conexo $\Leftrightarrow$ hay al menos $r$ caminos disjuntos entre cada par de vértices.

---

### 7. k-Conectividad por Aristas

**Definiciones:**

* Arista puente: Su eliminación desconecta G o lo trivializa.
* $\lambda(G)$: Mínimo número de aristas necesarias para desconectar G.

**Propiedades:**

* Si G es disconexo, entonces $λ(G) = 0$.

* G es $r$-conexo por aristas si $\lambda(G) \geq r$.

**Teorema de Menger (por aristas):**

* $G$ es $r$-linealmente conexo $\Leftrightarrow$ entre cada dos vértices siempre 
hay al menos r caminos 
disjuntos por aristas. 


---

### 8. Teorema de Whitney

**Relación:**

$k(G) \leq \lambda(G) \leq \delta(G)$

Donde:

* $k(G)$: índice de conectividad por vértices.
* $\lambda(G)$: índice de conectividad por aristas.
* $\delta(G)$: mín(lista_grados(G))

**Observación:**

* Alta conectividad requiere grados altos, pero grados altos no aseguran alta conectividad.
