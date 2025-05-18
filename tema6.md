## Tema 6: Planaridad

### 🔹 **Inmersiones y Grafos Planos**

* **Inmersión**: Representación de un grafo donde **no se cruzan las aristas**.
* **Grafo plano**: Un grafo que **admite una inmersión**.

---

### 🔹 **Propiedades de los grafos planos**

* Las **caras** de una inmersión pueden ser **interiores** o **exteriores**.
* Las **aristas puente**: Conectan caras con otras caras o con nada.
* Las **aristas frontera** cumplen que:

  * Forman **ciclos**.
  * Si una arista pertenece a un ciclo ⇒ es arista frontera.
  * Bordean **dos caras**.
* En un G plano con $|E|> 2$, **cada cara tiene al menos tres aristas frontera**. (Pensar en el triangulo)

#### ➤ Fórmulas:

* Si $G$ tiene $c$ caras y $a$ aristas:
  **$3c \le 2a$**
* Si **además** cada cara tiene al menos $b$ aristas frontera:
  **$bc \le 2a$**
* Si **G no tiene triangulos**:
  **$4c \le 2a$**

---

### 🔹 **Fórmula de Euler**

* Para un $G$ **plano conexo** con $v$ vértices, $a$ aristas y $c$ caras:
    $$v + c = a + 2$$
* Para un $G$ **plano conexo** con **$d$ componentes conexas**:
  $$v + c = a + d + 1$$

---

### 🔹 **Un test de Planaridad (NECESARIA PERO NO SUFICIENTE)**

* Para un $G$ **conexo** con $v > 2$, si $G$ es plano, entonces:
  
  $$a \le 3v - 6$$
* Consecuencia:

  * Si $a > 3v - 6$ ⇒ **No es plano**.
  * Si $a \le 3v - 6$ ⇒ **Solo sabemos que PUEDE ser plano**. Por ejemplo, el K3,3 satisface la condición pero NO es plano.

---

### 🔹 **Grafos Planos Maximales**

* Un $G$ plano es **maximal** si **añadir cualquier arista lo hace no plano**.
* **Propiedades**:

  * Cada cara está rodeada por **exactamente 3 aristas** (caras triangulares).
  * No tienen **aristas puente**.
  * Siempre son **conexos**.
  * Cumplen:
    **$a = 3v - 6$**

---

### 🔹 **Teorema de Kuratowski**

* **Un grafo es plano ⇔ no contiene una subdivisión de $K_5$ o $K_{3,3}$**.

---

### 🔹 **Teorema de Wagner**

* **Un grafo es plano ⇔ no contiene un subgrafo que pueda contraerse a $K_5$ o $K_{3,3}$**.

