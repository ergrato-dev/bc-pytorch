# 🎨 Assets Visuales - Semana 01

> Recursos visuales para apoyo del material teórico de fundamentos de Python

---

## 📊 Diagramas Incluidos

### 01. Ecosistema Python
**Archivo**: `01-python-ecosystem.svg` ✅  
**Usado en**: [1-teoria/01-introduccion-python.md](../1-teoria/01-introduccion-python.md#casos-de-uso)  
**Descripción**: Ecosistema de Python: bibliotecas, frameworks, aplicaciones principales

**Conceptos visualizados**:
- Web (Django, Flask)
- Data Science (pandas, NumPy)
- ML/AI (PyTorch, TensorFlow)
- Automatización (Selenium)

---

### 02. Tipos de Datos Básicos
**Archivo**: `02-data-types.svg` ✅  
**Usado en**: [1-teoria/02-variables-tipos-datos.md](../1-teoria/02-variables-tipos-datos.md#tipos-de-datos-básicos)  
**Descripción**: Tipos de datos primitivos en Python con ejemplos visuales

**Conceptos visualizados**:
- int: 42, -10, 0
- float: 3.14, -2.5
- str: "Hola", 'Python'
- bool: True, False
- Función type() para verificación

---

### 03. Precedencia de Operadores
**Archivo**: `03-operators-precedence.svg` ✅  
**Usado en**: [1-teoria/03-operadores.md](../1-teoria/03-operadores.md#precedencia-de-operadores)  
**Descripción**: Tabla visual de precedencia de operadores en Python

**Conceptos visualizados**:
- Orden de evaluación (6 niveles)
- Paréntesis > Exponenciación > Unarios > Multiplicación > Suma > Comparación
- Ejemplos de expresiones complejas

---

### 04. Flujo de Control
**Archivo**: `04-control-flow.svg` ✅  
**Usado en**: [1-teoria/04-estructuras-control.md](../1-teoria/04-estructuras-control.md)  
**Descripción**: Diagramas de flujo de estructuras condicionales y bucles

**Conceptos visualizados**:
- if/elif/else con diagrama de decisión
- for loops con iteración
- while loops con condición
- break, continue, pass

---

### 05. Anatomía de una Función
**Archivo**: `05-function-anatomy.svg` ✅  
**Usado en**: [1-teoria/05-funciones-basicas.md](../1-teoria/05-funciones-basicas.md#definir-funciones)  
**Descripción**: Componentes de una función Python con anotaciones visuales

**Conceptos visualizados**:
- def keyword
- nombre_funcion (snake_case)
- parámetros y type hints
- docstring documentación
- cuerpo de la función
- return statement
- ejemplo de llamada

---

## 🎨 Estándares de Diseño

Todos los assets SVG siguen estos estándares:

### Colores

```css
/* Colores principales */
--dark-bg: #1a1a2e;           /* Background oscuro */
--dark-secondary: #16213e;     /* Elementos secundarios */
--pytorch-orange: #EE4C2C;     /* Acento principal (PyTorch) */
--python-blue: #3776AB;        /* Python azul */
--python-yellow: #FFD43B;      /* Python amarillo */
--text-primary: #e2e8f0;       /* Texto principal (gris claro) */
--text-secondary: #a0aec0;     /* Texto secundario (gris medio) */
--success: #48bb78;            /* Verde (éxito) */
--error: #ef4444;              /* Rojo (error) */
--info: #4299e1;               /* Azul (info) */
```

### Tipografía

- **Fuente principal**: `system-ui, -apple-system, sans-serif`
- **Fuente código**: `'Courier New', Courier, monospace`
- **Sin degradados**: Colores sólidos únicamente

### Dimensiones

- **ViewBox estándar**: 800x400 a 800x600 (según complejidad)
- **Formato**: SVG optimizado
- **Responsive**: Escalable sin pérdida de calidad

---

## 💡 Uso en Markdown

Para incluir un asset en un archivo de teoría:

```markdown
![Descripción del diagrama](../0-assets/XX-nombre-archivo.svg)
```

**Ejemplo**:
```markdown
![Ecosistema Python](../0-assets/01-python-ecosystem.svg)
```

---

## 📝 Convenciones de Nomenclatura

```
XX-descripcion-clara.svg
│  └── Descripción en kebab-case
└── Número secuencial (01, 02, 03...)
```

**Reglas**:
- Numerar en orden lógico de aprendizaje (01, 02, 03...)
- Usar kebab-case para nombres descriptivos
- Nombres claros que reflejen el concepto
- Prefijo numérico para mantener orden

---

## 🛠️ Herramientas para Crear Diagramas

### Recomendadas

1. **[Excalidraw](https://excalidraw.com/)** - Diagramas rápidos
   - Gratis, online
   - Exporta a SVG
   - Estilo sketch intuitivo

2. **[Figma](https://figma.com/)** - Diseño profesional
   - Gratis para uso personal
   - Colaborativo
   - Componentes reutilizables

3. **[Draw.io / diagrams.net](https://app.diagrams.net/)** - Diagramas técnicos
   - Gratis, online/offline
   - Templates profesionales
   - Exporta múltiples formatos

4. **[SVGOMG](https://jakearchibald.github.io/svgomg/)** - Optimización SVG
   - Comprime SVG sin pérdida de calidad
   - Elimina código innecesario
   - Online, fácil de usar

---

## 🔧 Creación de Nuevos Assets

Al crear nuevos diagramas SVG:

1. **Seguir estándares de diseño** (colores, tipografía dark theme)
2. **Numerar secuencialmente** según orden de aparición (01, 02, 03...)
3. **Optimizar SVG** con SVGOMG (eliminar código innecesario)
4. **Probar visualización** en diferentes tamaños y dispositivos
5. **Vincular en teoría** con markdown y alt text descriptivo
6. **Actualizar este README** con descripción del asset

---

## 📊 Estado de Assets

| Asset | Estado | Formato | ViewBox | Usado en |
|-------|--------|---------|---------|----------|
| 01-python-ecosystem.svg | 🟢 Completado | SVG | 800x500 | Teoría 01 |
| 02-data-types.svg | 🟢 Completado | SVG | 800x400 | Teoría 02 |
| 03-operators-precedence.svg | 🟢 Completado | SVG | 800x500 | Teoría 03 |
| 04-control-flow.svg | 🟢 Completado | SVG | 800x600 | Teoría 04 |
| 05-function-anatomy.svg | 🟢 Completado | SVG | 800x500 | Teoría 05 |

**Leyenda**: ⚪ Por crear | 🟡 En progreso | 🟢 Completado

**Total**: 5/5 assets completados (100%)

---

## 🔗 Referencias

**Herramientas recomendadas**:
- [Excalidraw](https://excalidraw.com/) - Diagramas rápidos
- [Figma](https://figma.com/) - Diseño profesional
- [draw.io](https://draw.io/) - Diagramas técnicos
- [SVGOMG](https://jakearchibald.github.io/svgomg/) - Optimización SVG

**Inspiración**:
- [Python.org Branding](https://www.python.org/community/logos/)
- [Real Python Infographics](https://realpython.com/)
- [MDN Web Docs](https://developer.mozilla.org/) - Diagramas técnicos
- [JavaScript.info](https://javascript.info/) - Visualizaciones educativas

---

## ✅ Checklist para Nuevos Assets

- [x] SVG optimizado (sin elementos innecesarios)
- [x] Colores según estándares del bootcamp (dark theme)
- [x] Tipografía sans-serif
- [x] ViewBox apropiado (800x400 - 800x600)
- [x] Numeración secuencial correcta
- [x] Vinculado en archivo de teoría correspondiente
- [x] Descripción agregada a este README
- [x] Probado en diferentes dispositivos

---

_Assets Week 01 | Bootcamp PyTorch Zero to Hero_

**Nota**: Los assets se crean **INMEDIATAMENTE** después de completar 1-teoria/ para vincularlos correctamente con el material teórico.
