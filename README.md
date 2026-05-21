# 🧠 Logic Tutor

**Herramienta interactiva para aprender tablas de verdad de Lógica Proposicional, diseñada bajo los principios del Diseño Universal para el Aprendizaje (DUA).**

---

## ¿Qué es Logic Tutor?

Logic Tutor es una aplicación web de una sola página (`logiflex.html`) que guía al estudiante paso a paso en la construcción y análisis de tablas de verdad. No requiere instalación ni servidor: basta con abrir el archivo en cualquier navegador moderno.

Fue pensada para entornos educativos donde se busca:
- Andamiaje explícito del proceso lógico
- Feedback inmediato sin interrupciones (sin `alert()`)
- Accesibilidad y legibilidad (fuente Lexend, contrastes altos, ARIA básico)
- Flexibilidad en la representación (símbolos lógicos o notación de código)

---

## Funcionalidades

### 📊 Pestaña — Tablas de Verdad

| Paso | Descripción |
|------|-------------|
| **Paso 1** | Elegí un ejercicio prediseñado o escribí tu propia fórmula. El campo valida en tiempo real y solo acepta símbolos lógicos propios (¬ ∧ ∨ → ↔). |
| **Paso 2** | *Historia Formacional* — Ordená las subfórmulas de menor a mayor complejidad antes de construir la tabla. Disponible en **Nivel Asistido** (solo opciones válidas) o **Nivel Desafío** (todas las opciones mezcladas). |
| **Paso 3** | *Tabla de Verdad interactiva* — Completá las celdas haciendo clic en V o F. Las columnas se resaltan: 🟣 columna activa · 🟡 columnas dependientes · 💜 columna final. |
| **Paso Final** | *Semáforo de Clasificación* — Clasificá la fórmula como Tautología 🟢, Contradicción 🔴 o Contingencia 🟡. |

### 🔗 Pestaña — Comparar Fórmulas

- Ingresá dos fórmulas **α** y **β**
- Se genera automáticamente una tabla comparativa con ambas columnas destacadas
- Las filas donde α ≠ β se resaltan en rosa (son los casos clave)
- El estudiante decide la relación lógica entre ellas:
  - **α ≡ β** — Equivalencia lógica (α ↔ β es tautología)
  - **α ⟹ β** — Implicancia lógica (no existe fila con α=V y β=F)
  - **β ⟹ α** — Implicancia en sentido inverso
  - **Ninguna** — Existen contraejemplos en ambas direcciones
- El feedback incluye el contraejemplo exacto cuando la respuesta es incorrecta

### Otras características

- **Modo Símbolos / Código** — Alterna entre notación matemática (∧ ∨ ¬ → ↔) y notación de programación (AND OR NOT THEN IFF)
- **Variables en minúscula** — Las variables se muestran como p, q, r (no P, Q, R)
- **Contador de errores discreto** — Aparece en la barra de pestañas solo cuando hay al menos un intento incorrecto; registra errores de todas las actividades sin interrumpir el flujo
- **Validación completa de fórmulas** — Detecta paréntesis desbalanceados, operadores consecutivos, variables sin operador, y más de 10 tipos de errores con mensajes claros

---

## Uso

No requiere instalación. Simplemente abrí el archivo en tu navegador:

```
logiflex.html → doble clic → listo
```

O arrastrá `logiflex.html` a la ventana de cualquier navegador moderno (Chrome, Firefox, Edge, Safari).

---

## Fórmulas admitidas

El campo de entrada acepta directamente los símbolos lógicos estándar:

| Símbolo | Operación | Ejemplo |
|---------|-----------|---------|
| `¬` | Negación | `¬p` |
| `∧` | Conjunción | `p ∧ q` |
| `∨` | Disyunción | `p ∨ q` |
| `→` | Condicional | `p → q` |
| `↔` | Bicondicional | `p ↔ q` |
| `( )` | Agrupación | `(p ∧ q) → r` |

Variables soportadas: cualquier letra entre **p–z** (p, q, r, s, …).

---

## Tecnologías

| Tecnología | Uso |
|------------|-----|
| HTML5 / CSS3 / JavaScript (vanilla) | Base de la aplicación — sin frameworks ni bundlers |
| [Tailwind CSS](https://tailwindcss.com/) (CDN) | Estilos utilitarios |
| [Lexend](https://fonts.google.com/specimen/Lexend) | Tipografía principal (legibilidad DUA) |
| [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) | Tipografía monoespaciada para fórmulas |

No tiene dependencias de backend ni base de datos. Todo el procesamiento ocurre en el navegador.

---

## Estructura del proyecto

```
logicTutor/
├── logiflex.html   # Aplicación principal (HTML + CSS + JS en un solo archivo)
├── index.html      # Versión original de referencia
├── script.js       # Script de la versión original
├── styles.css      # Estilos de la versión original
└── README.md       # Este archivo
```

---

## Principios de diseño (DUA)

- **Sin popups ni `alert()`** — todo el feedback es inline, junto al contenido relevante
- **Código de color consistente** — Verde = Verdadero · Rojo = Falso · Ámbar = Atención
- **Andamiaje graduado** — el Paso 2 ordena las subfórmulas antes de enfrentar la tabla completa
- **Múltiples formas de representación** — Modo Símbolos y Modo Código para distintos perfiles de estudiante
- **Feedback explicativo** — los errores indican qué falta o cuál es la respuesta correcta y por qué

---

## Licencia

Uso educativo libre.
