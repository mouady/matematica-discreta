## Tema 4: Transversalidad

### 📌 Definiciones

* **Recorrido euleriano**: recorre todas las aristas exactamente una vez, puede empezar y terminar en vértices distintos.
* **Circuito euleriano**: recorrido euleriano cerrado que empieza y termina en el mismo vértice.
* **Grafo semi-euleriano**: grafo conexo que admite un recorrido euleriano.
* **Grafo euleriano**: grafo conexo que admite un circuito euleriano.

---

### 🧮 Teoremas (CONDICIONES NECESARIAS Y SUFICIENTES)

* **Teorema (carácter euleriano):**

> Un grafo (o multigrafo) conexo es **euleriano si y sólo si** todos sus vértices tienen **grado par**.

* **Teorema (carácter semi-euleriano):**

> Un grafo (o multigrafo) conexo es **semi-euleriano** **si y sólo si** todos sus vértices tienen grado par **excepto dos**.

#### 🧠 Observación:

> Si en G todos los vértices tienen grado par, cada uno está contenido en al menos un ciclo.

---

### ⚙️ Algoritmo para encontrar circuito euleriano EN UN G EULERIANO

1. Sea $v$ un vértice cualquiera y $C = \{v\}$
2. Mientras haya aristas sin visitar:

   * Escoger un vértice $u \in C$ con aristas incidentes sin visitar.
   * Formar un ciclo $D$ comenzando en $u$.
   * Marcar aristas de $D$ como visitadas.
   * Reemplazar $u$ por $D$ en $C$
3. Resultado: $C$ es el circuito euleriano.

#### 🧠 Observaciones:

* Nótese que tanto en D como en C es un {} donde se comienza y termina con el mismo vértice
* Se puede escoger el mismo u varias veces.

### ⚙️ Algoritmo para encontrar recorrido euleriano EN UN G SEMI-EULERIANO

1. Identificar los dos vértices de **grado impar**, llamémoslos $u$ y $v$.
2. Añadir un nuevo vértice ficticio $w$, y conectarlo con dos nuevas aristas: $w - u$ y $w - v$.
3. Esto forma un nuevo grafo $G'$, **euleriano**, ya que ahora todos los vértices tienen grado par.
4. Aplicar el algoritmo de circuito euleriano sobre $G'$, comenzando en $w$. Obtenemos el circuito.
5. Eliminamos el vértice añadido del circuito. Lo que obtenemos es un recorrido euleriano para G.

---

### 🧠 Carácter euleriano en dígrafos

Sea G un dígrafo débilmente conexo. Entonces:

G es euleriano si y solo si todos sus vértices v cumplen:

$$δ_s(v) = δ_e(v)$$

G admite un recorrido euleriano si y solo **si cumplen la condicion anterior excepto 2 vertices**:

Uno con: $$δ_s(v) = δ_e(v) + 1$$

Otro con: $$δ_e(v) = δ_s(v) + 1$$

🔁 Esto implica que el recorrido euleriano comienza en el vértice con mayor grado de salida y termina en el vértice con mayor grado de entrada.

---

## 🔁 2. Grafos Hamiltonianos

### 📌 Definiciones

* **Camino hamiltoniano**: pasa por todos los vértices exactamente una vez.
* **Ciclo hamiltoniano**: camino hamiltoniano cerrado (empieza y termina en el mismo vértice).
* **Grafo semi-hamiltoniano**: grafo que admite un camino hamiltoniano.
* **Grafo hamiltoniano**: grafo que admite un ciclo hamiltoniano.

#### 🧠 Observación:

> Si G es hamiltoniano => también es semi-hamiltoniano. (NO PASA CON EULER)

---

### ⚠️ Cuidado

* Determinar si un grafo es hamiltoniano es **NP-completo**.
* No existen condiciones necesarias y suficientes simples ni un algoritmo eficiente general para encontrar un ciclo hamiltoniano.

---

### ❗ Condiciones necesarias para que G SEA HAMILTONIANO

* No puede haber un vértice con **grado 1**.
* Si un vértice tiene **grado 2**, sus aristas deben estar en el ciclo.
* No pueden haber **vértice de corte**.
* Si al eliminar $c$ vértices quedan más de $c$ componentes conexas → NO ES HAMILTONIANO.

---

### ✔️ Condiciones suficientes para que G SEA HAMILTONIANO

Sea G un grafo simple conexo con $n \ge 3$ vértices:

#### Condición de **Dirac**:

> Si todos los vértices tienen grado $\geq n/2$, entonces $G$ tiene ciclo hamiltoniano.

#### Condición de **Ore**:

> Si la suma de grados de cada par de vértices no adyacentes $u, v$ es $\geq n$, entonces $G$ tiene ciclo hamiltoniano.

📌 **Nota**: Estas son condiciones **suficientes pero no necesarias**. El C5 por ejemplo es un grafo hamiltoniano que no verifica ninguna de esas condiciones.

---

### 🧮 Condiciones para Caminos Hamiltonianos

#### Necesarias:

* Si hay **vértice de grado 1**, debe ser extremo del camino.
* No más de dos vértices con grado 1.
* Si hay vértice de corte cuya eliminación provoca más de 2 componentes → no hay camino.
* Si al eliminar $c$ vértices hay más de $c+1$ componentes → no hay camino.

#### Solo una suficiente (Dirac):

> Si $G$ es simple, conexo, $n \geq 3$, y todos los vértices tienen grado $\geq (n-1)/2$, entonces **admite camino hamiltoniano**.

📌 **Nota**: Es solo una condición **suficiente pero no necesaria**. El C5 - 1 arista por ejemplo es un grafo hamiltoniano que no verifica ninguna de esas condiciones.
