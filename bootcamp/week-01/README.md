# 📅 Semana 01: Fundamentos de Python

> Introducción a Python 3.11+, variables, tipos de datos, operadores y estructuras de control básicas. Primera toma de contacto con la programación y el entorno de desarrollo.

---

## 🎯 Objetivos de Aprendizaje

Al finalizar esta semana podrás:

1. **Configurar** el entorno de desarrollo con Docker y Jupyter Lab
2. **Comprender** la sintaxis básica de Python y su filosofía
3. **Trabajar** con variables, tipos de datos primitivos y operadores
4. **Implementar** lógica básica con estructuras de control (if, for, while)
5. **Crear** funciones simples y reutilizar código
6. **Depurar** programas básicos identificando y corrigiendo errores

---

## 📚 Contenido

### Material Teórico (1-teoria/)

- [01 - Introducción a Python](1-teoria/01-introduccion-python.md)
- [02 - Variables y Tipos de Datos](1-teoria/02-variables-tipos-datos.md)
- [03 - Operadores](1-teoria/03-operadores.md)
- [04 - Estructuras de Control](1-teoria/04-estructuras-control.md)
- [05 - Funciones Básicas](1-teoria/05-funciones-basicas.md)
- [Notebook Interactivo: Práctica Teórica](1-teoria/notebooks/01_python_fundamentals.ipynb)

### Prácticas Guiadas (2-practicas/)

- [Práctica 1: Variables y Operadores](2-practicas/practica-01-variables-operadores/)
- [Práctica 2: Condicionales y Bucles](2-practicas/practica-02-condicionales-bucles/)
- [Práctica 3: Funciones](2-practicas/practica-03-funciones/)

### Proyecto Semanal (3-proyecto/) 🚀

- [Proyecto: Calculadora Interactiva](3-proyecto/README.md)
- **Duración estimada**: 3-4 horas
- **Único entregable obligatorio**
- Aplicación de consola que realiza operaciones matemáticas con menú interactivo

---

## ⏱️ Distribución del Tiempo (7 horas)

| Actividad | Tiempo | Descripción |
|-----------|--------|-------------|
| 📖 **Teoría** | 2h | Lectura de material y notebooks interactivos |
| 💻 **Prácticas** | 2h | 3 ejercicios guiados progresivos |
| 🚀 **Proyecto** | 3h | Calculadora interactiva con funciones avanzadas |

---

## 📋 Requisitos Previos

### Conocimientos

- ✅ Ninguno - Esta semana es Zero to Hero
- ✅ Disposición para aprender y experimentar
- ✅ Comprensión lectora básica de inglés técnico (para docs)

### Software

- ✅ Docker 24+ instalado ([Guía de instalación](../../_docs/docker-guide.md))
- ✅ VS Code (recomendado) o editor de texto
- ✅ Git para control de versiones
- ✅ Navegador web moderno

---

## 🚀 Inicio Rápido

### 1. Preparar el Entorno

```bash
# Navegar a la carpeta de la semana
cd bootcamp/week-01/

# Construir la imagen Docker
docker-compose build

# Iniciar Jupyter Lab
docker-compose up
```

### 2. Acceder a Jupyter Lab

Abre tu navegador en: `http://localhost:8888`

**Token**: `bootcamp`

### 3. Ruta de Aprendizaje

```
1️⃣ Leer teoría (1-teoria/)
2️⃣ Ejecutar notebooks interactivos
3️⃣ Completar prácticas guiadas (2-practicas/)
4️⃣ Desarrollar proyecto (3-proyecto/)
5️⃣ Consultar recursos adicionales (4-recursos/)
6️⃣ Usar glosario como referencia (5-glosario/)
```

---

## 🗂️ Estructura de Archivos

```
week-01/
├── README.md                    # Este archivo
├── rubrica-evaluacion.md        # Criterios de evaluación
├── Dockerfile                   # Imagen Docker Python 3.11
├── docker-compose.yml           # Configuración de servicios
├── requirements.txt             # Dependencias Python
├── 0-assets/                    # Diagramas y recursos visuales
│   ├── 01-python-ecosystem.png
│   ├── 02-data-types.png
│   └── README.md
├── 1-teoria/                    # Material teórico
│   ├── 01-introduccion-python.md
│   ├── 02-variables-tipos-datos.md
│   ├── 03-operadores.md
│   ├── 04-estructuras-control.md
│   ├── 05-funciones-basicas.md
│   ├── notebooks/
│   │   └── 01_python_fundamentals.ipynb
│   └── README.md
├── 2-practicas/                 # Ejercicios guiados
│   ├── practica-01-variables-operadores/
│   ├── practica-02-condicionales-bucles/
│   └── practica-03-funciones/
├── 3-proyecto/                  # Proyecto integrador
│   ├── README.md
│   ├── starter/
│   │   └── calculadora.py
│   └── solution/
│       └── calculadora.py
├── 4-recursos/                  # Recursos adicionales
│   ├── papers/
│   ├── videos/
│   └── webgrafia/
├── 5-glosario/                  # Términos clave
│   ├── README.md
│   └── cheat-sheet.md
├── data/                        # Datos (si aplica)
├── output/                      # Salidas generadas
└── results/                     # Resultados de prácticas
```

---

## 🎓 Conceptos Clave

Esta semana aprenderás:

### Fundamentos de Python

- **Sintaxis básica**: Indentación, comentarios, convenciones PEP 8
- **Tipos de datos**: `int`, `float`, `str`, `bool`
- **Operadores**: Aritméticos, comparación, lógicos, asignación
- **Estructuras**: `if/elif/else`, `for`, `while`
- **Funciones**: `def`, parámetros, `return`, scope

### Filosofía Python

- **Zen of Python**: Beautiful is better than ugly, simple is better than complex
- **Legibilidad**: El código se lee más que se escribe
- **Baterías incluidas**: stdlib rica y poderosa

---

## 🔗 Navegación

| ⬅️ Anterior | 🏠 Índice | ➡️ Siguiente |
|:-----------|:----------:|-------------:|
| — | [Bootcamp](../../README.md) | [Week 02](../week-02/README.md) |

---

## 📚 Recursos Adicionales

Ver carpeta [4-recursos/](4-recursos/) para:

- 📄 **Papers**: PEP 8 - Style Guide for Python Code
- 🎥 **Videos**: Python for Everybody (Dr. Chuck)
- 📝 **Artículos**: Real Python - Python Basics
- 📖 **Documentación**: Python 3.11 Official Tutorial

---

## 💡 Tips para Esta Semana

### ✅ Mejores Prácticas

1. **Ejecuta el código**: No solo leas, practica en Jupyter
2. **Experimenta**: Cambia valores, rompe cosas, aprende del error
3. **Comenta tu código**: Explica qué hace cada bloque
4. **Usa nombres descriptivos**: `user_age` mejor que `x`
5. **Consulta la documentación**: `help()` es tu amigo

### ⚠️ Errores Comunes de Principiantes

```python
# ❌ Incorrecto: Indentación inconsistente
if True:
  print("Hola")
    print("Mundo")  # Error de indentación

# ✅ Correcto: 4 espacios consistentes
if True:
    print("Hola")
    print("Mundo")

# ❌ Incorrecto: Comparación vs asignación
if x = 5:  # Error de sintaxis
    pass

# ✅ Correcto: Operador de comparación
if x == 5:
    pass

# ❌ Incorrecto: División entera en vez de float
resultado = 5 / 2  # 2.5 (en Python 3)
resultado = 5 // 2  # 2 (división entera)

# ✅ Correcto: Saber cuál usar según contexto
precio_total = 100.0 / 3  # 33.333...
items_por_caja = 100 // 3  # 33
```

---

## ❓ Preguntas Frecuentes

### ¿Necesito experiencia previa en programación?

**No.** Esta semana está diseñada para principiantes absolutos. Si nunca has programado, este es el lugar perfecto para empezar.

### ¿Por qué Python y no otro lenguaje?

Python es:
- 🎯 **Fácil de aprender**: Sintaxis clara y legible
- 💪 **Poderoso**: Usado por Google, NASA, Netflix
- 🚀 **Versatil**: Web, datos, IA, automatización
- 👥 **Comunidad enorme**: Millones de desarrolladores

### ¿Qué hago si me quedo atascado?

1. **Lee el mensaje de error** cuidadosamente
2. **Busca en el glosario** el término que no entiendes
3. **Revisa la teoría** correspondiente
4. **Experimenta** en Jupyter con ejemplos más simples
5. **Consulta recursos adicionales** en la carpeta 4-recursos/

### ¿Puedo adelantarme a la siguiente semana?

Sí, pero **completa el proyecto** primero. Es importante consolidar las bases antes de avanzar.

---

## 📊 Evaluación

La evaluación se realiza mediante **3 tipos de evidencia**:

- 🧠 **Conocimiento** (30%): Comprensión de conceptos
- 💪 **Desempeño** (40%): Código en prácticas
- 📦 **Producto** (30%): Proyecto semanal

**Mínimo para aprobar**: 70% en cada categoría

Ver [rubrica-evaluacion.md](rubrica-evaluacion.md) para criterios detallados.

---

## 🎯 ¿Listo para Empezar?

```bash
# Paso 1: Iniciar Docker
cd bootcamp/week-01/
docker-compose up

# Paso 2: Abrir navegador
open http://localhost:8888

# Paso 3: Empezar con la teoría
# Abre 1-teoria/01-introduccion-python.md
```

---

<p align="center">
  <strong>🐍 ¡Bienvenido al mundo de Python!</strong><br>
  <em>"Code is like humor. When you have to explain it, it's bad." - Cory House</em>
</p>

---

_Week 01 | Bootcamp PyTorch Zero to Hero_

**Última actualización**: Febrero 2026
