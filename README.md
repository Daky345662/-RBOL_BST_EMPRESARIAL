# Árbol BST Empresarial en C++

> **Asignatura:** Estructura de Datos  
> **Tema:** Árboles Binarios de Búsqueda en C++  
> **Modalidad:** Individual

---

## Descripción

Este proyecto implementa un **Árbol Binario de Búsqueda (BST)** en C++ para organizar empleados de una empresa de forma jerárquica, usando el código numérico de cada empleado como clave de ordenamiento.

La estructura del árbol refleja un organigrama empresarial donde es posible insertar, buscar y recorrer los registros de forma eficiente.

---

## Objetivo

Implementar en C++ un Árbol Binario de Búsqueda que permita:

- Organizar empleados mediante su código numérico.
- Realizar búsquedas eficientes en tiempo **O(log n)** en árboles balanceados.
- Visualizar la jerarquía mediante los tres tipos de recorrido.
- Identificar la estructura del árbol: raíz, nodos internos, hojas y altura.

---

## Funcionalidades

| # | Funcionalidad | Descripción |
|---|---------------|-------------|
| 1 | **Insertar empleado** | Agrega un nuevo nodo con código, nombre y cargo |
| 2 | **Buscar empleado** | Localiza un empleado por su código numérico |
| 3 | **Mostrar raíz** | Muestra el primer nodo insertado (nodo raíz del árbol) |
| 4 | **Recorrido Inorden** | Muestra empleados ordenados de menor a mayor código |
| 5 | **Recorrido Preorden** | Muestra raíz → izquierda → derecha |
| 6 | **Recorrido Postorden** | Muestra izquierda → derecha → raíz |
| 7 | **Altura y total de nodos** | Calcula el número de niveles y nodos totales |
| 8 | **Nodos hoja** | Muestra los nodos que no tienen hijos |

---

## Conceptos clave del árbol

### ¿Qué es un BST?
Un **Árbol Binario de Búsqueda** es una estructura de datos jerárquica donde cada nodo tiene como máximo dos hijos. La regla fundamental es:
- Los nodos con **código menor** van al **subárbol izquierdo**.
- Los nodos con **código mayor** van al **subárbol derecho**.

### Terminología utilizada

| Término | Definición | Ejemplo en los datos de prueba |
|---------|------------|-------------------------------|
| **Raíz** | Nodo inicial del árbol; no tiene padre | Código 50 (Empresa UTA) |
| **Nodo interno** | Tiene al menos un hijo | Códigos 30 y 70 (Gerentes) |
| **Hoja** | No tiene ningún hijo | Códigos 20, 40, 60, 80 |
| **Nivel** | Distancia desde la raíz hasta un nodo | Raíz = nivel 0; hojas = nivel 2 |
| **Altura** | Número de niveles del árbol | 3 (con los datos de prueba) |

---

## Estructura del árbol con datos de prueba

Insertando en el orden: `50 → 30 → 70 → 20 → 40 → 60 → 80`

```
              50          <- Raíz (Empresa UTA)
             /  \
           30    70       <- Nodos internos (Gerentes)
          / \   / \
         20 40 60  80     <- Hojas (Empleados)
```

### Resultados esperados

| Recorrido | Resultado |
|-----------|-----------|
| **Inorden** | 20 → 30 → 40 → 50 → 60 → 70 → 80 |
| **Preorden** | 50 → 30 → 20 → 40 → 70 → 60 → 80 |
| **Postorden** | 20 → 40 → 30 → 60 → 80 → 70 → 50 |
| **Altura** | 3 niveles |
| **Hojas** | 20, 40, 60, 80 |

---

## Estructura del repositorio

```
arbol-bst-empresa-cpp/
│
├── src/
│   └── main.cpp          <- Código fuente principal
│
├── capturas/
│   ├── 01_menu.png
│   ├── 02_insercion.png
│   ├── 03_busqueda.png
│   ├── 04_recorridos.png
│   └── 05_altura_hojas.png
│
└── README.md             <- Este archivo
```

---

## Compilación y ejecución

### Requisitos
- Compilador `g++` instalado (viene con MinGW en Windows o gcc en Linux/Mac).

### Pasos

**1. Clonar el repositorio:**
```bash
git clone https://github.com/tu-usuario/arbol-bst-empresa-cpp.git
cd arbol-bst-empresa-cpp
```

**2. Compilar:**
```bash
g++ src/main.cpp -o arbol
```

**3. Ejecutar:**
```bash
# Linux / Mac
./arbol

# Windows
arbol.exe
```

---

## Datos de prueba

Usa el menú opción `1` para insertar los siguientes empleados **en este orden exacto**:

| Código | Nombre | Cargo |
|--------|--------|-------|
| 50 | Empresa UTA | Raiz |
| 30 | Gerente Ventas | Nodo interno |
| 70 | Gerente Finanzas | Nodo interno |
| 20 | Emp 1 | Hoja |
| 40 | Emp 2 | Hoja |
| 60 | Emp 3 | Hoja |
| 80 | Emp 4 | Hoja |

> **Importante:** El orden de inserción determina la forma del árbol. Insertando 50 primero, este será la raíz.

---

## Capturas de ejecución

> Reemplaza las imágenes con tus propias capturas de pantalla al ejecutar el programa.

### Menú principal
![Menu principal](capturas/01_menu.png)

### Inserción de empleados
![Insercion](capturas/02_insercion.png)

### Búsqueda de empleado
![Busqueda](capturas/03_busqueda.png)

### Recorridos del árbol
![Recorridos](capturas/04_recorridos.png)

### Altura y nodos hoja
![Altura y hojas](capturas/05_altura_hojas.png)

---

## Explicación del código

### Struct `Empleado`
Almacena los datos de cada persona: `codigo` (clave de búsqueda), `nombre` y `cargo`.

### Struct `Nodo`
Representa cada elemento del árbol. Contiene un `Empleado` y dos punteros: `izquierdo` y `derecho`.

### Clase `ArbolBST`
Encapsula toda la lógica del árbol con métodos privados recursivos y métodos públicos para el menú. Incluye destructor `~ArbolBST()` para liberar memoria automáticamente.

### Lógica de inserción
```
Si el código es menor al nodo actual → ir a la izquierda
Si el código es mayor al nodo actual → ir a la derecha
Si el árbol está vacío → crear nuevo nodo aquí
```

---

## Conclusión

El Árbol Binario de Búsqueda permite organizar información jerárquica de manera eficiente. En este proyecto se comprobó que:

- La **estructura BST** organiza automáticamente los datos por clave numérica.
- El **recorrido inorden** siempre produce los elementos en orden ascendente.
- La **búsqueda** es más rápida que en listas lineales al descartar la mitad del árbol en cada paso.
- Los conceptos de **raíz, nodo interno, hoja y altura** son visibles directamente al ejecutar el programa con los datos de prueba.

---

## Tecnologías

![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat&logo=c%2B%2B&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)
