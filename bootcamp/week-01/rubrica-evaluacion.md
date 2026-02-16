# 📊 Rúbrica de Evaluación - Semana 01

> Criterios específicos para evaluar el aprendizaje de fundamentos de Python

---

## 🎯 Evidencias de Aprendizaje

Esta semana se evalúa mediante **3 tipos de evidencia**:

### 1. 🧠 Conocimiento (30%)

Demuestra comprensión de conceptos mediante:

- Notebooks de teoría completados con celdas ejecutadas
- Respuestas a preguntas conceptuales en el proyecto
- Explicaciones en comentarios del código
- Uso correcto de terminología en documentación

#### Criterios de Evaluación

| Nivel | Rango | Criterios |
|-------|-------|-----------|
| **Excelente** | 90-100% | • Explica conceptos con ejemplos propios<br>• Identifica cuándo usar cada tipo de dato<br>• Comprende diferencias entre operadores<br>• Puede predecir el resultado de código |
| **Bueno** | 80-89% | • Comprende los conceptos básicos<br>• Aplica correctamente tipos de datos<br>• Usa operadores apropiadamente<br>• Identifica errores simples |
| **Suficiente** | 70-79% | • Reconoce tipos de datos básicos<br>• Usa operadores fundamentales<br>• Comprende estructura if/else<br>• Sigue ejemplos del material |
| **Insuficiente** | <70% | • No distingue tipos de datos<br>• Confunde operadores<br>• No entiende flujo de control<br>• No ejecuta código básico |

#### Conceptos Clave a Evaluar

- [ ] **Variables**: Asignación, nombres válidos, convenciones
- [ ] **Tipos de datos**: `int`, `float`, `str`, `bool`
- [ ] **Conversión**: Casting entre tipos (`int()`, `str()`, etc.)
- [ ] **Operadores**: Aritméticos, comparación, lógicos
- [ ] **Condicionales**: `if`, `elif`, `else`
- [ ] **Bucles**: `for`, `while`, `break`, `continue`
- [ ] **Funciones**: Definición, parámetros, return
- [ ] **Scope**: Variables locales vs globales

---

### 2. 💪 Desempeño (40%)

Evaluado mediante las **3 prácticas guiadas**:

#### Criterios Generales

| Nivel | Rango | Criterios |
|-------|-------|-----------|
| **Excelente** | 90-100% | • Código limpio y bien organizado<br>• Sigue PEP 8 consistentemente<br>• Nombres de variables descriptivos<br>• Comentarios útiles y claros<br>• Manejo de casos edge |
| **Bueno** | 80-89% | • Código funcional y organizado<br>• Sigue convenciones básicas<br>• Variables con nombres razonables<br>• Comentarios presentes<br>• Funciona en casos comunes |
| **Suficiente** | 70-79% | • Código ejecuta sin errores<br>• Estructura básica correcta<br>• Variables identificables<br>• Algunos comentarios<br>• Cumple requisitos mínimos |
| **Insuficiente** | <70% | • Código con errores de sintaxis<br>• Desorganizado o ilegible<br>• Variables confusas (x, y, z)<br>• Sin comentarios<br>• No cumple requisitos |

#### Práctica 1: Variables y Operadores (30%)

- [ ] Declara variables correctamente
- [ ] Usa tipos de datos apropiados
- [ ] Aplica operadores aritméticos
- [ ] Realiza conversiones de tipo
- [ ] Formatea salidas con f-strings

#### Práctica 2: Condicionales y Bucles (35%)

- [ ] Implementa condicionales if/elif/else
- [ ] Crea bucles for funcionales
- [ ] Usa bucles while apropiadamente
- [ ] Aplica break/continue correctamente
- [ ] Evita bucles infinitos

#### Práctica 3: Funciones (35%)

- [ ] Define funciones con def
- [ ] Usa parámetros correctamente
- [ ] Implementa return apropiado
- [ ] Reutiliza funciones
- [ ] Documenta con docstrings

---

### 3. 📦 Producto: Calculadora Interactiva (30%)

El **único entregable obligatorio** es el proyecto de calculadora.

#### Distribución de Puntos

| Criterio | Peso | Descripción |
|----------|------|-------------|
| **Funcionalidad** | 40% | Todas las operaciones funcionan correctamente |
| **Código Limpio** | 25% | Organización, nombres, PEP 8 |
| **Interfaz Usuario** | 20% | Menú claro, manejo de errores, experiencia UX |
| **Documentación** | 15% | README, comentarios, instrucciones de uso |

#### Requisitos Funcionales

##### Obligatorios (70 puntos)

- [ ] **Operaciones básicas** (20 pts)
  - Suma, resta, multiplicación, división
  - Manejo de división por cero
  
- [ ] **Menú interactivo** (15 pts)
  - Mostrar opciones claramente
  - Capturar entrada del usuario
  - Validar entrada

- [ ] **Bucle principal** (15 pts)
  - Permite múltiples operaciones
  - Opción para salir
  - No termina abruptamente

- [ ] **Funciones organizadas** (10 pts)
  - Al menos una función por operación
  - Función para mostrar menú
  - Función main()

- [ ] **Manejo de errores** (10 pts)
  - Captura entradas inválidas
  - Mensajes de error claros
  - Programa no crashea

##### Opcionales (30 puntos)

- [ ] **Operaciones avanzadas** (10 pts)
  - Potencia, raíz cuadrada
  - Módulo, división entera
  - Operaciones con paréntesis

- [ ] **Historial** (10 pts)
  - Guarda operaciones anteriores
  - Permite ver historial
  - Opción de limpiar historial

- [ ] **Extras** (10 pts)
  - Colores en terminal
  - Guardado en archivo
  - Tests automatizados
  - Interfaz mejorada

#### Niveles de Calidad

| Nivel | Puntos | Descripción |
|-------|--------|-------------|
| **Excelente** | 90-100 | • Todos los obligatorios + al menos 2 opcionales<br>• Código muy limpio y profesional<br>• README completo con ejemplos<br>• Manejo robusto de errores |
| **Bueno** | 80-89 | • Todos los obligatorios + 1 opcional<br>• Código limpio y organizado<br>• README con instrucciones claras<br>• Manejo básico de errores |
| **Suficiente** | 70-79 | • Todos los obligatorios cumplidos<br>• Código funcional<br>• README básico presente<br>• Maneja errores comunes |
| **Insuficiente** | <70 | • Faltan requisitos obligatorios<br>• Código desorganizado o con errores<br>• Sin documentación<br>• Crashes frecuentes |

---

## ✅ Criterios Mínimos para Aprobar

Para aprobar la Semana 01 debes cumplir:

### Conocimiento (≥70%)

- [ ] Ejecutar todos los notebooks de teoría
- [ ] Responder correctamente preguntas conceptuales básicas
- [ ] Explicar con tus palabras al menos 3 conceptos clave

### Desempeño (≥70%)

- [ ] Completar las 3 prácticas guiadas
- [ ] Código ejecutable sin errores de sintaxis
- [ ] Seguir convenciones básicas de nombres

### Producto (≥70%)

- [ ] Proyecto entregado y funcionando
- [ ] Al menos 70 puntos en requisitos funcionales
- [ ] README presente con instrucciones
- [ ] Sin errores críticos que impidan uso

---

## 🎯 Fórmula de Calificación

```
Nota Final = (Conocimiento × 0.30) + (Desempeño × 0.40) + (Producto × 0.30)

Ejemplo:
- Conocimiento: 85% → 85 × 0.30 = 25.5
- Desempeño: 90% → 90 × 0.40 = 36.0
- Producto: 80% → 80 × 0.30 = 24.0
-----------------------------------------
Nota Final: 85.5% (Bueno)
```

---

## 📝 Formato de Entrega

### Estructura de Archivos

```
apellido-nombre-week-01/
├── README.md                 # Descripción del proyecto
├── calculadora.py            # Código principal
├── requirements.txt          # Dependencias (si aplica)
├── resultados/               # Capturas de pantalla
│   ├── menu.png
│   ├── operacion1.png
│   └── operacion2.png
└── tests/                    # Tests (opcional)
    └── test_calculadora.py
```

### README.md de Entrega (Mínimo)

```markdown
# Calculadora Interactiva - [Tu Nombre]

## Descripción
[Breve descripción de tu calculadora]

## Funcionalidades Implementadas
- [x] Operaciones básicas
- [x] Menú interactivo
- [ ] Historial (opcional)

## Instrucciones de Uso
1. Ejecutar: `python calculadora.py`
2. Seleccionar operación del menú
3. Ingresar números
4. Ver resultado

## Ejemplos
[Capturas de pantalla o ejemplo de uso]

## Reflexión
[Qué aprendiste, qué te costó más, qué mejorarías]
```

### Plataforma y Fecha

- **Plataforma**: [Especificar - GitHub/Moodle/etc]
- **Formato**: ZIP o repositorio Git
- **Fecha límite**: Domingo 23:59 de la semana correspondiente
- **Nombre de archivo**: `apellido-nombre-week-01.zip`

---

## 🔍 Proceso de Evaluación

### 1. Autoevaluación (Recomendado)

Antes de entregar, usa esta checklist:

```
CONOCIMIENTO
[ ] Puedo explicar qué es una variable
[ ] Sé la diferencia entre = y ==
[ ] Entiendo cuándo usar for vs while
[ ] Puedo crear una función simple

DESEMPEÑO
[ ] Mi código ejecuta sin errores
[ ] Usé nombres descriptivos de variables
[ ] Agregué comentarios útiles
[ ] Seguí PEP 8 básico (4 espacios)

PRODUCTO
[ ] La calculadora funciona
[ ] Maneja división por cero
[ ] Tiene menú interactivo
[ ] Incluí README
```

### 2. Evaluación por Pares (Opcional)

Intercambia tu proyecto con un compañero:
- Ejecuta su código
- Prueba casos límite
- Da feedback constructivo
- Aprende de su enfoque

### 3. Evaluación Final

Criterios de revisión:
1. **Ejecución**: ¿El código corre sin modificaciones?
2. **Funcionalidad**: ¿Cumple los requisitos?
3. **Calidad**: ¿Es legible y mantenible?
4. **Documentación**: ¿Está bien explicado?

---

## 💡 Consejos para Maximizar tu Nota

### Para Conocimiento

- ✅ Ejecuta cada celda del notebook y observa el resultado
- ✅ Experimenta modificando valores
- ✅ Toma notas en tus propias palabras
- ✅ Haz preguntas en el foro

### Para Desempeño

- ✅ Empieza simple, luego mejora
- ✅ Prueba tu código frecuentemente
- ✅ Lee mensajes de error cuidadosamente
- ✅ Usa `help()` y documentación

### Para Producto

- ✅ Planifica antes de codear
- ✅ Implementa requisitos uno por uno
- ✅ Prueba cada funcionalidad
- ✅ Documenta mientras programas
- ✅ Haz commit frecuente si usas Git

---

## ❓ Preguntas Frecuentes

### ¿Puedo usar librerías externas?

Para Week-01, intenta usar solo Python estándar. Si usas algo externo, documéntalo en `requirements.txt`.

### ¿Qué pasa si no termino a tiempo?

Entrega lo que tengas. Se evalúa el progreso. Es mejor entregar algo incompleto que nada.

### ¿Puedo rehacer si no apruebo?

Sí, tendrás una semana adicional para mejorar y volver a entregar.

### ¿El código tiene que ser perfecto?

No. Se valora el proceso de aprendizaje. Errores y código mejorable son parte del proceso.

---

## 📊 Estadísticas de Referencia

Distribución típica de notas en Week-01:

| Rango | % Estudiantes | Interpretación |
|-------|---------------|----------------|
| 90-100% | ~20% | Excelente comprensión y ejecución |
| 80-89% | ~40% | Buen dominio de fundamentos |
| 70-79% | ~30% | Aprobado, necesita reforzar |
| <70% | ~10% | Requiere repaso y práctica adicional |

**Nota promedio histórica**: 82%

---

## 🎯 Próximos Pasos

Después de completar Week-01:

1. **Repasa** conceptos que te costaron
2. **Consulta** recursos adicionales si necesitas
3. **Prepárate** para Week-02: Estructuras de Datos
4. **Celebra** tu progreso - ¡completaste la primera semana!

---

<p align="center">
  <strong>📊 Rúbrica Week 01</strong><br>
  <em>"Lo que se mide, se mejora" - Peter Drucker</em>
</p>

---

_Rúbrica de Evaluación Week 01 | Bootcamp PyTorch Zero to Hero_

**Última actualización**: Febrero 2026
