# Estructura del Bootcamp PyTorch

Este documento describe la estructura completa del bootcamp, con todas las 24 semanas organizadas.

## 📁 Estructura General

```
bc-pytorch/
├── README.md                   # Documentación principal (ES)
├── README_EN.md                # Documentación principal (EN)
├── LICENSE                     # MIT License
├── CONTRIBUTING.md             # Guía de contribución
├── CODE_OF_CONDUCT.md          # Código de conducta
├── SECURITY.md                 # Política de seguridad
├── SUPPORT.md                  # Guía de soporte
├── CONTRIBUTORS.md             # Reconocimientos
├── CHANGELOG.md                # Registro de cambios
├── .gitignore                  # Git ignore
│
├── .github/                    # Configuración de GitHub
│   ├── copilot-instructions.md
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── ISSUE_TEMPLATE/
│       ├── config.yml
│       ├── bug_report.md
│       ├── feature_request.md
│       ├── documentation.md
│       └── question.md
│
├── _docs/                      # Documentación adicional
│   ├── estructura-bootcamp.md  # Este archivo
│   └── docker-guide.md         # Guía de Docker (por crear)
│
└── bootcamp/                   # Contenido del bootcamp
    ├── week-01/                # Semana 1
    ├── week-02/                # Semana 2
    ├── ...                     # Semanas 3-23
    └── week-24/                # Semana 24
```

## 🗂️ Estructura de Cada Semana

Cada semana (`week-XX/`) sigue esta estructura estandarizada:

```
week-XX/
├── README.md                     # Descripción, objetivos, navegación
├── rubrica-evaluacion.md         # Criterios de evaluación (30/40/30)
├── Dockerfile                    # Imagen Docker personalizada
├── docker-compose.yml            # Configuración de servicios
├── requirements.txt              # Dependencias Python específicas
├── .dockerignore                 # Archivos a ignorar en build Docker
│
├── 0-assets/                     # Recursos visuales
│   ├── README.md                 # Descripción de assets
│   ├── 01-diagram.svg            # Diagramas y gráficos (SVG)
│   └── .gitkeep                  # Preservar estructura
│
├── 1-teoria/                     # Material teórico
│   ├── README.md                 # Índice de teoría
│   ├── 01-concepto.md            # Archivos markdown explicativos
│   ├── 02-concepto.md
│   ├── notebooks/                # Notebooks interactivos
│   │   ├── teoria_01.ipynb
│   │   └── .gitkeep
│   └── .gitkeep
│
├── 2-practicas/                  # Ejercicios guiados
│   ├── README.md                 # Índice de prácticas
│   ├── practica-01-nombre/
│   │   ├── README.md             # Instrucciones del ejercicio
│   │   ├── starter/              # Código inicial
│   │   │   ├── notebook.ipynb
│   │   │   └── .gitkeep
│   │   ├── solution/             # Solución (gitignored)
│   │   │   ├── notebook.ipynb
│   │   │   └── .gitkeep
│   │   └── .gitkeep
│   ├── practica-02-nombre/
│   └── .gitkeep
│
├── 3-proyecto/                   # Proyecto semanal (único entregable)
│   ├── README.md                 # Descripción detallada del proyecto
│   ├── data/                     # Datos para el proyecto
│   │   ├── README.md             # Cómo obtener/usar los datos
│   │   └── .gitkeep
│   ├── starter/                  # Código inicial
│   │   ├── notebook.ipynb
│   │   ├── utils/                # Módulos de utilidades
│   │   │   └── .gitkeep
│   │   └── .gitkeep
│   ├── solution/                 # Solución de referencia (gitignored)
│   │   ├── notebook.ipynb
│   │   └── .gitkeep
│   ├── output/                   # Outputs generados
│   │   └── .gitkeep
│   ├── results/                  # Resultados y métricas
│   │   └── .gitkeep
│   └── .gitkeep
│
├── 4-recursos/                   # Recursos adicionales
│   ├── README.md                 # Índice de recursos
│   ├── papers/                   # Papers relevantes
│   │   ├── README.md
│   │   └── .gitkeep
│   ├── videos/                   # Enlaces a videos
│   │   ├── README.md
│   │   └── .gitkeep
│   ├── webgrafia/                # Artículos y tutoriales
│   │   ├── README.md
│   │   └── .gitkeep
│   └── .gitkeep
│
└── 5-glosario/                   # Términos y referencia
    ├── README.md                 # Glosario de conceptos
    ├── cheat-sheet.md            # Referencia rápida de sintaxis
    └── .gitkeep
```

## 📅 Distribución de Semanas

### Etapa 1: Fundamentos Python/NumPy (Semanas 1-6) - 42h

| Semana | Tema Principal | Horas |
|--------|----------------|-------|
| week-01 | Introducción a Python 3.11+ | 7h |
| week-02 | Estructuras de Datos y Control de Flujo | 7h |
| week-03 | Funciones y Programación Modular | 7h |
| week-04 | NumPy: Arrays y Operaciones | 7h |
| week-05 | NumPy Avanzado y Broadcasting | 7h |
| week-06 | Visualización con Matplotlib/Seaborn | 7h |

### Etapa 2: PyTorch Básico (Semanas 7-12) - 42h

| Semana | Tema Principal | Horas |
|--------|----------------|-------|
| week-07 | Introducción a PyTorch y Tensores | 7h |
| week-08 | Autograd y Diferenciación Automática | 7h |
| week-09 | nn.Module y Construcción de Modelos | 7h |
| week-10 | Optimizadores y Loss Functions | 7h |
| week-11 | DataLoaders y Datasets | 7h |
| week-12 | Training Loops y Evaluación | 7h |

### Etapa 3: Redes Neuronales (Semanas 13-18) - 42h

| Semana | Tema Principal | Horas |
|--------|----------------|-------|
| week-13 | Redes Neuronales Feedforward | 7h |
| week-14 | Convolutional Neural Networks (CNNs) | 7h |
| week-15 | CNNs Avanzadas y Arquitecturas Modernas | 7h |
| week-16 | Recurrent Neural Networks (RNNs) | 7h |
| week-17 | LSTM y GRU para Secuencias | 7h |
| week-18 | Regularización y Normalización | 7h |

### Etapa 4: Avanzado y Deploy (Semanas 19-24) - 42h

| Semana | Tema Principal | Horas |
|--------|----------------|-------|
| week-19 | Transfer Learning | 7h |
| week-20 | Fine-tuning de Modelos Pre-entrenados | 7h |
| week-21 | Optimización de Hiperparámetros | 7h |
| week-22 | Interpretabilidad y Visualización | 7h |
| week-23 | Despliegue con Docker | 7h |
| week-24 | Proyecto Final Integrador | 7h |

## 🎯 Archivos `.gitkeep`

Los archivos `.gitkeep` se utilizan para:

1. **Preservar estructura vacía en Git**: Git no trackea carpetas vacías
2. **Documentación implícita**: Indica que la carpeta es parte de la estructura oficial
3. **Facilitar clonación**: Los estudiantes obtienen la estructura completa desde el inicio
4. **Consistencia**: Todas las semanas tienen la misma estructura

### Ubicaciones de `.gitkeep`:

- Todas las carpetas principales de cada sección (`0-assets/`, `1-teoria/`, etc.)
- Subcarpetas que pueden estar inicialmente vacías
- Carpetas `starter/` y `solution/` de ejercicios y proyectos
- Carpetas de recursos (`papers/`, `videos/`, `webgrafia/`)

## � Archivos `.dockerignore`

Los archivos `.dockerignore` optimizan la construcción de imágenes Docker:

1. **Reduce tamaño del contexto**: Excluye archivos innecesarios del build
2. **Acelera builds**: Menos archivos = transferencia más rápida
3. **Seguridad**: Evita copiar archivos sensibles al contenedor
4. **Optimización de caché**: Builds más eficientes al ignorar cambios irrelevantes

### Configuración por Ubicación:

#### Raíz del Proyecto (`/.dockerignore`)
```gitignore
# Configuración exhaustiva (79 líneas)
# Ignora: documentación, .git, CI/CD, todos los datos de semanas
```

#### Cada Semana (`week-XX/.dockerignore`)
```gitignore
# Configuración enfocada (33 líneas)
# Ignora: cache Python, Jupyter checkpoints, datos, soluciones
```

### Patrones Principales Ignorados:

- **Python**: `__pycache__/`, `*.pyc`, `.Python`
- **Jupyter**: `.ipynb_checkpoints/`, `*.ipynb_backup`
- **Datos**: `data/`, `checkpoints/`, `*.pth`, `*.pt`
- **IDE**: `.vscode/`, `.idea/`, `*.swp`
- **Soluciones**: `solution/`, `solutions/`

## �📝 Notas Importantes

1. **Las carpetas `solution/` están en `.gitignore`**: Para proteger las soluciones
2. **Los archivos `.gitkeep` pueden contener comentarios**: Opcionalmente documentar el propósito de la carpeta
3. **Cada semana tiene su `.dockerignore`**: Optimiza builds de Docker (25 archivos en total)
4. **Estructura flexible**: Algunas semanas pueden no usar todas las carpetas
5. **Datos grandes en `.gitignore` y `.dockerignore`**: Usar `data/README.md` con instrucciones de descarga

## 🔗 Referencias

- [Copilot Instructions](.github/copilot-instructions.md) - Guías completas de desarrollo
- [CONTRIBUTING.md](../CONTRIBUTING.md) - Cómo contribuir respetando la estructura
- [.gitignore](../.gitignore) - Qué archivos se excluyen del repositorio

---

*Última actualización: Febrero 2026*
