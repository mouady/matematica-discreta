## Tema 5 Parte 2: Emparejamiento

### 🔹 Definiciones clave

* **Emparejamiento**: Subconjunto de aristas de G no incidentes entre sí.

* **Emparejamiento maximal**: Emparejamiento con el mayor número posible de aristas. (El mayor número de asignaciones posibles).

* **Emparejamiento completo**: Cuando "todos los trabajadores tienen una tarea asignada"

---

### 🔹 Condición y Teorema de Hall

* **Condición de Hall**: 
    * P es cualquier subconjunto de X (trabajadores).

  $$
  \forall P \subseteq X,\quad |T(P)| \geq |P|
  $$

  donde $T(P) = \{ y \in Y \mid \exists x \in P \text{ tal que } (x, y) \in E \}$

* **Teorema de Hall**:

  * Un grafo bipartito $G = (X \cup Y, E)$ tiene un emparejamiento completo si y solo si cumple la condición de Hall.

* **Observación**:

  * Comprobar la condición de Hall directamente requiere $2^{|X|}$ comprobaciones. INVIABLE!!

---

### 🔹 Caminos alternados

* **Definición**:

  * Dado un emparejamiento $M$, un **camino alternado** es una secuencia de aristas donde:

    * Las posiciones impares (1ra, 3ra, ...) no están en $M$
    * Las pares (2da, 4ta, ...) sí están en $M$
    * El camino tiene longitud impar.

* **Ventaja**:

  * Si se encuentra un camino alternado, al intercambiar las aristas en $M$ por las del camino se obtiene un nuevo emparejamiento con una arista más.

---

### 🔹 Árbol de caminos alternados

* **Construcción**:

  1. Nivel 0: trabajador libre $x_0$
  2. Nivel 1: tareas adyacentes a $x_0$
  3. Nivel 2: trabajadores emparejados con las tareas del nivel anterior
  4. Nivel 3: tareas adyacentes a los trabajadores del nivel anterior
  5. Y así sucesivamente...

* **Propiedad**:

  * Si el emparejamiento $M$ no es maximal, entonces **siempre existe** un camino alternado en G.

* **Criterio**:

  * Si hay una **hoja en un nivel impar** del árbol, entonces existe un camino alternado.

---

### 🔹 Algoritmo de mejora de emparejamiento

1. Comenzar con un emparejamiento inicial $M$.
2. Buscamos un camino alternado para M construyendo el 
**árbol de camino alternado**

* Si se encuentra un camino alternado:

   * Intercambiar aristas para obtener $M'$ con una arista más.
   * Volver al paso 2.

* Si no se encuentra camino alternado:

   * $M$ es EMPAREJAMIENTO MAXIMAL.
   * Si además $|M| = |X|$, entonces TAMBIÉN ES COMPLETO.


