## Tema 1

### 1. Definición de Grafo

* **Grafo simple:**

  * Conjunto de vértices $V$ y conjunto de aristas $A$.
  * Sin aristas múltiples, lazos, dirección ni pesos.

### 2. Variantes de Grafos

* **Multigrafo:** Permite aristas múltiples entre los mismos vértices.
* **Pseudografo:** Multigrafo que además permite lazos (aristas de un vértice consigo mismo).
* **Grafo dirigido (Digrafo):** Las aristas tienen sentido.
* **Grafo ponderado:** Las aristas tienen pesos.

---

### 3. Grado o Valencia de un Vértice

* **$\delta(v)$**: Número de aristas incidentes en el vértice $v$.
* **Lista de grados**: lista ordenada de grados de todos los vértices.
* **Grafo k-regular**: cuando todos los vértices tienen la **k** valencia
* **Lema del apretón de manos:**
  $\sum_{v \in V} \delta(v) = 2|A|$
* **En digrafos**: grado de entrada $\delta_e(v)$ y grado de salida $\delta_s(v)$.

**Observaciones:**

* $0 \leq \delta(v) \leq n - 1$ para cualquier vértice $v$ en un grafo simple.
* No pueden coexistir vértices con grados 0 y $n-1$ simultáneamente en el mismo grafo. (Ejemplo de la fiesta)

---

### 4. Ejemplos Importantes de Grafos

* **Grafo completo $K_n$:** Todos los vértices están conectados entre sí.
* **Grafo camino $P_n$:** Vértices forman una secuencia lineal.
* **Grafo ciclo $C_n$:** Vértices forman un ciclo cerrado.
* **Grafos bipartitos:** Se pueden dividir los vértices en dos grupos, sin aristas internas.
* **Grafos bipartitos completos $K_{n,m}$:** Cada vértice de un grupo conectado con todos los vértices del otro grupo.

---

### 5. Subgrafos

* **Subgrafo inducido por S:** Si S es un subconjunto de vértices, G(S) es el subgrafo formado por los vértices de S y las aristas entre ellos.
* **Subgrafo recubridor:** Cuando G' contiene todos los vértices del G original. (Tema 3)
* **Eliminación de un vértice:** Al eliminar un vértice, se eliminan también todas las aristas incidentes a dicho vértice.
* **Eliminación de una arista:** Al eliminar una arista, se elimina únicamente dicha conexión entre los vértices que unía.

---

### 6. Suma de Grafos

* Unión de conjuntos de vértices y aristas, más todas las aristas que conectan vértices de un grafo con los del otro.

---

### 7. Grafo Complementario

* Misma cantidad de vértices; dos vértices conectados en el complementario si no lo están en el original.
* Propiedad: $G \cup \bar{G} = K_n$

---

### 8. Isomorfismo de Grafos

* Dos grafos son isomorfos ($G_1 \cong G_2$) si existe una correspondencia biyectiva entre sus vértices que preserva las aristas.
* Condiciones NECESARIAS PERO NO SUFICIENTES para isomorfismo:

  * Mismo $|V|$ y mismo $|A|$
  * Misma lista de grados.
  * Mismo número de ciclos, vértices de corte y mismas componentes conexas.

**Propiedad:** Dos grafos son isomorfos $<=>$ Sus complementarios lo son.

---

### 9. Formas de Representar un Grafo

* **Exhaustiva:** Listas explícitas de vértices y aristas.
* **Lista de adyacencias:** Cada vértice seguido de la lista de vértices adyacentes.
* **Matriz de adyacencias:** Matriz cuadrada simétrica; entrada $A_{ij} = 1$ si vértices $i,j$ adyacentes; 0 si no.
* **Matriz de incidencias:** Filas representan vértices, columnas aristas; entrada indica incidencia.

**Variantes en matrices:**

* **Aristas múltiples**: Indican número de aristas entre vértices.
* **Lazos**: Indican doble número del lazo del vértice.
* **Digrafos**: La matriz de adyacencias ya no es simétrica.
* **Grafos ponderados**: Indican peso en lugar de 1.
