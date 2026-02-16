# 🤖 Instrucciones para GitHub Copilot - Bootcamp PyTorch

## 🎯 Contexto del Proyecto

Este es un **Bootcamp Zero to Hero de PyTorch** estructurado para llevar a estudiantes desde cero hasta un nivel competente en deep learning con PyTorch en **24 semanas** con una dedicación de **7 horas semanales** (168 horas totales).

### Características del Bootcamp

- **Duración**: 24 semanas
- **Tiempo semanal**: 7 horas
- **Nivel**: Zero to Hero (principiantes absolutos → competentes)
- **Enfoque**: Aprendizaje práctico basado en proyectos
- **Lenguaje**: Python 3.11+ con PyTorch 2.0+
- **Tecnología**: Docker para entornos reproducibles
- **Idioma**: Código en inglés, comentarios y documentación en español

---

## 📚 Estructura del Bootcamp

### Etapas de Aprendizaje

| Etapa | Semanas | Horas | Temas Principales |
|:-----:|:-------:|:-----:|-------------------|
| **Fundamentos Python/NumPy** | 1-6 | 42h | Python moderno, NumPy, visualización |
| **PyTorch Básico** | 7-12 | 42h | Tensores, autograd, modelos básicos |
| **Redes Neuronales** | 13-18 | 42h | CNNs, RNNs, arquitecturas modernas |
| **Avanzado y Deploy** | 19-24 | 42h | Transfer learning, optimización, producción |

### Estructura Semanal Estándar

```
bootcamp/week-XX/
├── README.md                 # Descripción y objetivos
├── rubrica-evaluacion.md     # Criterios de evaluación
├── Dockerfile                # Imagen Docker para la semana
├── docker-compose.yml        # Servicios y configuración
├── requirements.txt          # Dependencias Python
├── 0-assets/                 # Imágenes y diagramas (SVG)
│   ├── 01-diagram.svg
│   └── README.md
├── 1-teoria/                 # Material teórico
│   ├── 01-concepto.md
│   ├── 02-concepto.md
│   └── notebooks/
│       └── teoria_01.ipynb
├── 2-practicas/              # Ejercicios guiados
│   ├── practica-01-nombre/
│   │   ├── README.md
│   │   ├── starter/
│   │   │   └── ejercicio.ipynb
│   │   └── solution/
│   │       └── ejercicio.ipynb
│   └── practica-02-nombre/
├── 3-proyecto/               # Proyecto semanal
│   ├── README.md
│   ├── starter/
│   │   ├── notebook.ipynb
│   │   └── utils/
│   └── solution/
│       └── notebook.ipynb
├── 4-recursos/               # Recursos adicionales
│   ├── papers/               # Papers relevantes
│   ├── videos/               # Enlaces a videos
│   └── webgrafia/            # Artículos y tutoriales
└── 5-glosario/               # Términos clave
    ├── README.md             # Definiciones y conceptos
    └── cheat-sheet.md        # Referencia rápida de sintaxis
```

---

## 🎓 Filosofía Pedagógica

### Principios de Enseñanza

1. **Learning by Doing**: Cada concepto se aprende implementándolo
2. **Progresión Gradual**: De simple a complejo, sin saltos abruptos
3. **Proyectos Reales**: Casos de uso del mundo real desde el inicio
4. **Visualización**: Gráficos y diagramas para conceptos complejos
5. **Experimentación**: Notebooks interactivos para explorar

### Tipos de Contenido

#### 📖 Teoría
- Notebooks interactivos con explicaciones
- Ejemplos ejecutables paso a paso
- Visualizaciones de conceptos
- Referencias a papers y documentación

#### 💻 Prácticas
- Ejercicios guiados con notebooks
- Código comentado para completar
- Tests automatizados cuando sea posible
- NO usar TODOs, usar secciones comentadas para descomentar

#### 🏗️ Proyectos
- Un proyecto integrador por semana
- **ÚNICO ENTREGABLE** obligatorio
- Aplicación práctica de conceptos de la semana
- Datasets reales y bien documentados

---

## 📝 Guías de Estilo

### Python/PyTorch

**✅ Convenciones a Seguir:**

```python
# Imports organizados
import numpy as np
import torch
import torch.nn as nn
import torch.nn.functional as F
from torch.utils.data import Dataset, DataLoader

# Nombres descriptivos en inglés
class ConvolutionalNetwork(nn.Module):
    """Red convolucional para clasificación de imágenes."""
    
    def __init__(self, num_classes: int = 10):
        super().__init__()
        self.conv1 = nn.Conv2d(3, 32, kernel_size=3)
        self.conv2 = nn.Conv2d(32, 64, kernel_size=3)
        self.fc = nn.Linear(64 * 6 * 6, num_classes)
    
    def forward(self, x: torch.Tensor) -> torch.Tensor:
        # Comentarios en español explicando el flujo
        x = F.relu(self.conv1(x))  # Primera capa convolucional
        x = F.max_pool2d(x, 2)     # Pooling para reducir dimensiones
        x = F.relu(self.conv2(x))  # Segunda capa convolucional
        x = F.max_pool2d(x, 2)
        x = x.flatten(1)           # Aplanar para fully connected
        x = self.fc(x)
        return x

# Type hints siempre
def train_epoch(
    model: nn.Module,
    dataloader: DataLoader,
    criterion: nn.Module,
    optimizer: torch.optim.Optimizer,
    device: torch.device
) -> float:
    """Entrena el modelo por una época."""
    model.train()
    total_loss = 0.0
    
    for batch_idx, (data, target) in enumerate(dataloader):
        data, target = data.to(device), target.to(device)
        
        optimizer.zero_grad()
        output = model(data)
        loss = criterion(output, target)
        loss.backward()
        optimizer.step()
        
        total_loss += loss.item()
    
    return total_loss / len(dataloader)
```

**❌ Evitar:**

```python
# Sin type hints
def train(m, d, c, o):
    pass

# Nombres no descriptivos
x = nn.Conv2d(3, 32, 3)
fc1 = nn.Linear(1000, 10)

# Sin comentarios explicativos
class Net(nn.Module):
    def __init__(self):
        super().__init__()
        self.c1 = nn.Conv2d(3, 32, 3)
    
    def forward(self, x):
        x = self.c1(x)
        return x

# Comentarios obvios
x = 5  # asigna 5 a x
```

### Notebooks

**Estructura de Celdas:**

```python
# ============================================
# SECCIÓN 1: Nombre Descriptivo
# ============================================

# %% [markdown]
# ## Título de la Sección
# 
# Explicación del concepto que se va a aprender.
# Incluir contexto, motivación y aplicaciones.

# %% [code]
# Código ejecutable con comentarios explicativos
import torch

# Crear tensor de ejemplo
tensor = torch.randn(3, 4)
print(f"Shape: {tensor.shape}")
print(f"Device: {tensor.device}")

# %% [markdown]
# **Resultado esperado**: Deberías ver un tensor de 3x4 con valores aleatorios.
# 
# 💡 **Tip**: Los tensores son la estructura fundamental en PyTorch.
```

**Elementos Visuales:**

```python
# Siempre incluir visualizaciones
import matplotlib.pyplot as plt
import seaborn as sns

# Configurar estilo consistente
plt.style.use('seaborn-v0_8-darkgrid')
sns.set_palette("husl")

# Gráfico con título y etiquetas en español
plt.figure(figsize=(10, 6))
plt.plot(train_losses, label='Pérdida de Entrenamiento')
plt.plot(val_losses, label='Pérdida de Validación')
plt.xlabel('Época')
plt.ylabel('Pérdida')
plt.title('Curvas de Aprendizaje')
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()
```

---

## 🗂️ Nomenclatura y Convenciones

### Archivos y Carpetas

```
# Carpetas en inglés con guiones
week-01/
week-12/
2-practicas/
3-proyecto/

# Archivos Python en snake_case
train_model.py
data_preprocessing.py
model_architectures.py

# Notebooks descriptivos
01_intro_tensors.ipynb
02_autograd_basics.ipynb
proyecto_clasificacion_imagenes.ipynb

# Archivos de configuración
requirements.txt
config.yaml
.gitignore
```

### Variables y Funciones

```python
# Variables: snake_case descriptivo
learning_rate = 0.001
num_epochs = 50
batch_size = 32
train_loader = DataLoader(...)

# Funciones: snake_case con verbos
def load_dataset(path: str) -> Dataset:
    """Carga el dataset desde la ruta especificada."""
    pass

def train_model(model: nn.Module, epochs: int) -> dict:
    """Entrena el modelo y retorna métricas."""
    pass

def evaluate_performance(model: nn.Module, test_loader: DataLoader) -> float:
    """Evalúa el modelo en el conjunto de test."""
    pass

# Clases: PascalCase
class CustomDataset(Dataset):
    """Dataset personalizado para carga de datos."""
    pass

class ConvolutionalClassifier(nn.Module):
    """Clasificador basado en CNNs."""
    pass
```

### Constantes y Configuración

```python
# Constantes en UPPER_CASE
NUM_CLASSES = 10
IMAGE_SIZE = 224
DEFAULT_DEVICE = torch.device('cuda' if torch.cuda.is_available() else 'cpu')

# Configuración en diccionarios o dataclasses
from dataclasses import dataclass

@dataclass
class TrainingConfig:
    """Configuración para entrenamiento."""
    learning_rate: float = 1e-3
    batch_size: int = 32
    num_epochs: int = 50
    device: str = 'cuda'
    save_path: str = './checkpoints'
```

---

## 🎯 Creación de Contenido

### Al crear material teórico (1-teoria/)

```markdown
# Título del Concepto

## 🎯 Objetivos de Aprendizaje

Al finalizar esta lección podrás:
- Objetivo claro y medible 1
- Objetivo claro y medible 2
- Objetivo claro y medible 3

## 📋 Contenido

### Introducción

Explicación del concepto con contexto del mundo real.

### ¿Por qué es importante?

Motivación y aplicaciones prácticas.

### Implementación

\`\`\`python
# Código ejecutable con explicaciones
import torch

# Ejemplo simple pero ilustrativo
tensor = torch.tensor([1, 2, 3])
print(tensor)
\`\`\`

### Visualización

![Diagrama Explicativo](../0-assets/01-concept.svg)

## ✅ Checklist de Verificación

- [ ] Entiendo el concepto fundamental
- [ ] Puedo explicarlo con mis propias palabras
- [ ] He ejecutado todos los ejemplos
- [ ] Sé cuándo usar esta técnica

## 🔗 Recursos Adicionales

- [PyTorch Docs - Concepto](url)
- [Paper Original](url)
- [Tutorial Complementario](url)
```

### Al crear prácticas (2-practicas/)

**README.md del ejercicio:**

```markdown
# 🏋️ Práctica XX: Nombre Descriptivo

## 🎯 Objetivo

Descripción clara de qué se va a aprender.

## 📋 Conceptos Clave

- Concepto 1
- Concepto 2
- Concepto 3

## ⏱️ Duración Estimada

45 minutos

## 📝 Instrucciones

### Paso 1: Configuración

Abre el notebook `starter/ejercicio.ipynb`.

### Paso 2: Implementación

Completa las secciones marcadas descomentando y completando el código.

### Paso 3: Verificación

Ejecuta las celdas de test para verificar tu implementación.

## ✅ Criterios de Éxito

- [ ] Todos los tests pasan
- [ ] El código es claro y está comentado
- [ ] Se visualizan correctamente los resultados

## 🔗 Recursos

- [Documentación PyTorch](url)
- [Tutorial relacionado](url)
```

**Notebook starter:**

```python
# ============================================
# PRÁCTICA: Nombre Descriptivo
# ============================================

# %% [markdown]
# # Práctica XX: Título
# 
# **Objetivo**: Describir claramente qué se va a aprender.
# 
# **Tiempo estimado**: 45 minutos

# %% [markdown]
# ## Paso 1: Imports y Configuración
# 
# Importa las librerías necesarias.

# %% [code]
import torch
import torch.nn as nn
import matplotlib.pyplot as plt
import numpy as np

# Configurar semilla para reproducibilidad
torch.manual_seed(42)
np.random.seed(42)

# Configurar device
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
print(f"Using device: {device}")

# %% [markdown]
# ## Paso 2: Ejercicio Principal
# 
# Explicación del ejercicio con contexto.
# 
# **Tarea**: Implementa la siguiente función descomentando y completando.

# %% [code]
# ============================================
# TODO: Completa esta función
# ============================================

# def mi_funcion(x: torch.Tensor) -> torch.Tensor:
#     """
#     Descripción de qué debe hacer la función.
#     
#     Args:
#         x: Tensor de entrada de shape (batch, features)
#     
#     Returns:
#         Tensor procesado de shape (batch, output_features)
#     """
#     # Tu código aquí
#     pass

# %% [markdown]
# ## Paso 3: Verificación
# 
# Ejecuta esta celda para verificar tu implementación.

# %% [code]
# Test básico
# x_test = torch.randn(10, 5)
# result = mi_funcion(x_test)
# assert result.shape == (10, 10), "Shape incorrecto"
# print("✅ Test pasado!")

# %% [markdown]
# 🎉 **¡Felicitaciones!** Has completado la práctica.
```

### Al crear proyectos (3-proyecto/)

**README.md del proyecto:**

```markdown
# 🚀 Proyecto Semana XX: Título del Proyecto

> **🎯 ÚNICO ENTREGABLE**: Este proyecto es el único entregable obligatorio para aprobar la semana.

## 🎯 Objetivos

- Objetivo específico 1
- Objetivo específico 2  
- Objetivo específico 3

## 📋 Descripción

Descripción detallada del proyecto, contexto y aplicación real.

## 🗂️ Estructura del Proyecto

\`\`\`
3-proyecto/
├── README.md              # Este archivo
├── requirements.txt       # Dependencias
├── data/                  # Datos (incluir .gitkeep)
│   └── README.md         # Cómo obtener los datos
├── starter/               # Código inicial
│   ├── notebook.ipynb    # Notebook principal
│   ├── models.py         # Definiciones de modelos
│   ├── data_loader.py    # Carga de datos
│   └── utils.py          # Utilidades
└── solution/              # Solución completa (gitignored)
    └── notebook.ipynb
\`\`\`

## ✅ Requisitos Funcionales

### Obligatorios (70%)

- [ ] Carga de datos correcta
- [ ] Implementación del modelo
- [ ] Loop de entrenamiento
- [ ] Evaluación con métricas
- [ ] Visualización de resultados

### Extras (30%)

- [ ] Experimentación con hiperparámetros
- [ ] Análisis de errores
- [ ] Documentación detallada

## 📊 Criterios de Evaluación

| Criterio | Peso | Descripción |
|----------|------|-------------|
| **Funcionalidad** | 40% | El código ejecuta correctamente |
| **Código Limpio** | 20% | Organización, comentarios, PEP 8 |
| **Resultados** | 20% | Métricas y visualizaciones |
| **Documentación** | 20% | README y comentarios explicativos |

## 🚀 Instrucciones de Desarrollo

### 1. Preparación (30 min)

- Leer este README completo
- Revisar documentación de PyTorch relevante
- Explorar el dataset

### 2. Implementación (4 horas)

Orden recomendado:
1. Cargar y explorar datos (45 min)
2. Implementar modelo (60 min)
3. Loop de entrenamiento (60 min)
4. Evaluación y métricas (45 min)
5. Visualización (30 min)

### 3. Testing y Refinamiento (1.5 horas)

- Ejecutar todo el notebook de inicio a fin
- Verificar que todas las visualizaciones son claras
- Revisar que todos los comentarios están en español

### 4. Documentación (30 min)

- Completar secciones del notebook
- Añadir conclusiones
- Preparar entrega

## 🎓 Conceptos Aplicados

Esta semana integras:
- Concepto 1 de la teoría
- Concepto 2 de las prácticas
- Concepto 3 nuevo en el proyecto

## 💡 Tips

1. **Empieza simple**: Implementa la versión básica primero
2. **Prueba frecuentemente**: No esperes al final para ejecutar
3. **Visualiza todo**: Los gráficos ayudan a entender
4. **Documenta mientras codificas**: No dejes comentarios para el final
5. **Consulta la documentación**: PyTorch docs son muy claras

## 🔗 Recursos de Apoyo

- [PyTorch Tutorial - Tema](url)
- [Paper Relevante](url)
- [Dataset Documentation](url)

## 📦 Entrega

```bash
# Estructura de entrega
apellido-nombre-week-XX/
├── notebook.ipynb         # Notebook completado
├── models.py             # Si creaste módulos separados
├── requirements.txt      # Versiones exactas
└── README.md            # Con conclusiones y resultados
```

**Fecha límite**: [Especificar]

---

_Proyecto Week XX | Bootcamp PyTorch Zero to Hero_
```

---

## 📊 Evaluación del Aprendizaje

### Rúbrica General

Cada semana se evalúa mediante **3 tipos de evidencia**:

#### 1. 🧠 Conocimiento (30%)
- **Excelente (90-100%)**: Comprende conceptos profundamente, puede explicarlos
- **Bueno (80-89%)**: Comprende conceptos, puede aplicarlos
- **Suficiente (70-79%)**: Comprende lo básico
- **Insuficiente (<70%)**: No demuestra comprensión

#### 2. 💪 Desempeño (40%)
- **Excelente (90-100%)**: Código eficiente, bien estructurado, sigue best practices
- **Bueno (80-89%)**: Código funcional y organizado
- **Suficiente (70-79%)**: Código funciona pero mejorable
- **Insuficiente (<70%)**: Código no funciona o muy desorganizado

#### 3. 📦 Producto (30%)
- **Excelente (90-100%)**: Proyecto completo, documentado, con extras
- **Bueno (80-89%)**: Proyecto completo y funcional
- **Suficiente (70-79%)**: Cumple requisitos mínimos
- **Insuficiente (<70%)**: No cumple requisitos

**Mínimo para aprobar**: 70% en cada tipo de evidencia.

---

## 🎨 Assets y Recursos Visuales

### Diagramas (0-assets/)

```markdown
# 📊 Assets - Semana XX

## Diagramas Incluidos

### 01. Nombre del Concepto
**Archivo**: `01-architecture-diagram.svg`  
**Usado en**: [1-teoria/01-concepto.md](../1-teoria/01-concepto.md)  
**Descripción**: Arquitectura de la red neuronal usada esta semana

**Conceptos visualizados**:
- Componente 1
- Componente 2
- Flujo de datos

---

### 02. Flujo de Datos
**Archivo**: `02-data-flow.svg`  
**Usado en**: Proyecto, sección "Pipeline"  
**Descripción**: Flujo de datos en el pipeline de entrenamiento

**Conceptos visualizados**:
- Input → Preprocessing
- Model → Training
- Output → Evaluation

## Estándares de Diseño

### Colores
- **Background**: `#1a1a2e` (dark theme)
- **Texto principal**: `#e2e8f0` (gris claro)
- **Texto secundario**: `#a0aec0` (gris medio)
- **Accent PyTorch**: `#EE4C2C` (naranja PyTorch)
- **Success**: `#48bb78` (verde)
- **Error**: `#ef4444` (rojo)

### Tipografía
- **Fuente principal**: `system-ui, sans-serif`
- **Fuente código**: `Courier, monospace`
- **Sin degradados**: Colores sólidos únicamente

### Dimensiones
- **ViewBox**: 800x400 a 800x600 (según complejidad)
- **Formato**: SVG optimizado
- **Responsive**: Escalable sin pérdida
```

### Notebooks de Teoría

- Incluir celdas markdown con secciones claras
- Gráficos con matplotlib/seaborn
- Ejemplos interactivos
- Ejercicios rápidos inline

### Cheat Sheet (5-glosario/cheat-sheet.md)

**Propósito**: Documento de referencia rápida con sintaxis y ejemplos concisos.

**Estructura:**

```markdown
# 📋 Cheat Sheet - Semana XX: [Tema]

> Referencia rápida de sintaxis y comandos clave de la semana.

---

## 🎯 Conceptos Principales

### [Concepto 1]

```python
# Sintaxis básica
import torch

# Ejemplo mínimo
tensor = torch.tensor([1, 2, 3])
print(tensor.shape)  # torch.Size([3])
```

**Casos de uso:**
- Uso 1: Descripción breve
- Uso 2: Descripción breve

### [Concepto 2]

```python
# Otro ejemplo conciso
model = nn.Linear(10, 5)
output = model(input_tensor)
```

---

## 🔧 Funciones y Métodos Clave

| Función | Sintaxis | Retorna | Uso |
|---------|----------|---------|-----|
| `torch.tensor()` | `torch.tensor(data)` | Tensor | Crear tensor desde datos |
| `tensor.shape` | `tensor.shape` | torch.Size | Obtener dimensiones |
| `tensor.to()` | `tensor.to(device)` | Tensor | Mover a dispositivo |

---

## 💡 Tips y Trucos

```python
# Tip 1: Usar device para compatibilidad CPU/GPU
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
tensor = tensor.to(device)

# Tip 2: Broadcasting automático
a = torch.tensor([1, 2, 3])  # shape: (3,)
b = torch.tensor([[1], [2]])  # shape: (2, 1)
result = a + b  # shape: (2, 3) - broadcasting!
```

---

## ⚠️ Errores Comunes

### Error 1: Shape mismatch

```python
# ❌ Incorrecto
a = torch.randn(3, 4)
b = torch.randn(5, 6)
result = a @ b  # Error: dimensiones incompatibles

# ✅ Correcto
a = torch.randn(3, 4)
b = torch.randn(4, 5)
result = a @ b  # (3, 5) - matriz multiplicación válida
```

### Error 2: Device mismatch

```python
# ❌ Incorrecto
model = model.to('cuda')
input_data = torch.randn(10, 5)  # En CPU
output = model(input_data)  # Error: tensores en dispositivos diferentes

# ✅ Correcto
model = model.to('cuda')
input_data = torch.randn(10, 5).to('cuda')  # Mover a GPU también
output = model(input_data)
```

---

## 🔗 Referencias Rápidas

- [PyTorch Docs - Tema](url)
- [Tutorial Oficial](url)
- [README Teoría](../1-teoria/)

---

_Cheat Sheet Week XX | Bootcamp PyTorch_
```

**Características del Cheat Sheet:**

- ✅ **Conciso**: Solo sintaxis esencial, sin explicaciones extensas
- ✅ **Ejemplos ejecutables**: Código que se puede copiar y ejecutar directamente
- ✅ **Tabla de referencia**: Métodos y funciones en formato tabla
- ✅ **Errores comunes**: Mostrar qué NO hacer y la forma correcta
- ✅ **Tips prácticos**: Trucos útiles que ahorran tiempo
- ✅ **Diferente del glosario**: El glosario define conceptos, el cheat sheet muestra sintaxis

**Diferencia entre README.md y cheat-sheet.md:**

| Aspecto | README.md (Glosario) | cheat-sheet.md |
|---------|---------------------|----------------|
| **Objetivo** | Definir términos y conceptos | Referencia rápida de sintaxis |
| **Contenido** | Definiciones extensas | Código y ejemplos concisos |
| **Uso** | Aprender conceptos nuevos | Recordar sintaxis durante práctica |
| **Estilo** | Educativo, detallado | Directo, copy-paste ready |

---

## 🔄 Workflow de Desarrollo

> 📌 **Para workflow completo y detallado**: Ver [WORKFLOW.md](../WORKFLOW.md) y [_docs/workflow-creacion-semanal.md](../_docs/workflow-creacion-semanal.md)  
> Incluye orden de creación, templates completos, checklists y ejemplos basados en [bc-javascript-es2023](https://github.com/ergrato-dev/bc-javascript-es2023).

### Resumen del Orden de Creación

1. **README.md** de la semana → Marco general
2. **rubrica-evaluacion.md** → Criterios de evaluación
3. **1-teoria/** → Material teórico
4. **0-assets/** → Assets vinculados (DESPUÉS de teoría)
5. **2-practicas/** → 3-4 ejercicios guiados
6. **3-proyecto/** → Proyecto integrador
7. **4-recursos/** → Recursos completos
8. **5-glosario/** → Glosario y cheat sheet

### Para Teoría

1. **Planificar objetivos** claros de aprendizaje
2. **Escribir** contenido markdown con explicaciones
3. **Crear** notebook interactivo con ejemplos
4. **Agregar** visualizaciones y diagramas
5. **Revisar** que fluye de simple a complejo
6. **Probar** que todos los ejemplos funcionan en Docker

### Para Prácticas

1. **Diseñar** ejercicio con objetivo claro
2. **Implementar** solución completa primero
3. **Crear** versión starter comentada
4. **Agregar** tests de verificación
5. **Escribir** README con instrucciones paso a paso
6. **Probar** que un estudiante puede seguirlo en Docker

### Para Proyectos

1. **Seleccionar** dataset interesante y apropiado
2. **Definir** requisitos funcionales claros
3. **Implementar** solución de referencia
4. **Crear** starter con structure y TODOs
5. **Documentar** exhaustivamente en README
6. **Probar** en Docker que es completable en 5-6 horas

---

## � Entorno de Desarrollo con Docker

### Filosofía Docker

**TODO el bootcamp se ejecuta en contenedores Docker** para garantizar:

- ✅ **Reproducibilidad**: Mismo entorno en todas las máquinas
- ✅ **Aislamiento**: No contaminar el sistema host
- ✅ **Portabilidad**: Funciona en Linux, macOS, Windows
- ✅ **Gestión de GPU**: Soporte CUDA mediante NVIDIA Container Toolkit
- ✅ **Versionado**: Cada semana tiene su imagen específica

### Estructura Docker por Semana

Cada semana incluye:

```
week-XX/
├── Dockerfile              # Imagen personalizada para la semana
├── docker-compose.yml      # Configuración de servicios
├── requirements.txt        # Dependencias Python específicas
└── .dockerignore          # Archivos a ignorar
```

### Dockerfile Base

**Para semanas 1-6 (Fundamentos Python/NumPy):**

```dockerfile
# Dockerfile para Semanas 1-6: Fundamentos Python
FROM python:3.11-slim

# Metadata
LABEL maintainer="Bootcamp PyTorch"
LABEL description="Entorno para Week XX - [Tema]"

# Variables de entorno
ENV PYTHONUNBUFFERED=1 \
    DEBIAN_FRONTEND=noninteractive \
    JUPYTER_ENABLE_LAB=yes

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    git \
    curl \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Crear directorio de trabajo
WORKDIR /bootcamp

# Copiar requirements
COPY requirements.txt .

# Instalar dependencias Python
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Exponer puerto de Jupyter
EXPOSE 8888

# Comando por defecto
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
```

**Para semanas 7-24 (PyTorch):**

```dockerfile
# Dockerfile para Semanas 7-24: PyTorch
FROM pytorch/pytorch:2.0.0-cuda11.7-cudnn8-runtime

# Metadata
LABEL maintainer="Bootcamp PyTorch"
LABEL description="Entorno para Week XX - [Tema]"

# Variables de entorno
ENV PYTHONUNBUFFERED=1 \
    DEBIAN_FRONTEND=noninteractive \
    JUPYTER_ENABLE_LAB=yes \
    TORCH_HOME=/bootcamp/.cache/torch

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    git \
    curl \
    build-essential \
    graphviz \
    && rm -rf /var/lib/apt/lists/*

# Crear directorio de trabajo
WORKDIR /bootcamp

# Copiar requirements
COPY requirements.txt .

# Instalar dependencias Python adicionales
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Crear directorios para datos y checkpoints
RUN mkdir -p /bootcamp/data /bootcamp/checkpoints /bootcamp/.cache

# Exponer puerto de Jupyter
EXPOSE 8888

# Comando por defecto
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
```

### docker-compose.yml

**Configuración estándar:**

```yaml
version: '3.8'

services:
  jupyter:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: bootcamp-week-XX
    ports:
      - "8888:8888"  # Jupyter Lab
    volumes:
      - ./1-teoria:/bootcamp/1-teoria
      - ./2-practicas:/bootcamp/2-practicas
      - ./3-proyecto:/bootcamp/3-proyecto
      - ./data:/bootcamp/data
      - checkpoints:/bootcamp/checkpoints
      - cache:/bootcamp/.cache
    environment:
      - JUPYTER_TOKEN=bootcamp
      - PYTHONPATH=/bootcamp
    # Descomentar para uso de GPU (requiere nvidia-docker)
    # deploy:
    #   resources:
    #     reservations:
    #       devices:
    #         - driver: nvidia
    #           count: all
    #           capabilities: [gpu]
    stdin_open: true
    tty: true

volumes:
  checkpoints:
  cache:
```

### requirements.txt

**Semanas 1-6 (Fundamentos):**

```txt
# Python Fundamentals (Weeks 1-6)
numpy>=1.24.0
pandas>=2.0.0
matplotlib>=3.7.0
seaborn>=0.12.0
jupyterlab>=4.0.0
ipywidgets>=8.0.0
scikit-learn>=1.3.0
pillow>=10.0.0
tqdm>=4.65.0
```

**Semanas 7-24 (PyTorch):**

```txt
# PyTorch Ecosystem (Weeks 7-24)
# torch y torchvision ya están en la imagen base
jupyterlab>=4.0.0
ipywidgets>=8.0.0
numpy>=1.24.0
pandas>=2.0.0
matplotlib>=3.7.0
seaborn>=0.12.0
scikit-learn>=1.3.0
pillow>=10.0.0
tqdm>=4.65.0
tensorboard>=2.13.0
torchsummary>=1.5.1
torchinfo>=1.8.0

# Extras según semana
# opencv-python>=4.8.0  # Para visión computacional
# transformers>=4.30.0   # Para NLP (semanas avanzadas)
```

### Comandos Docker Esenciales

**Construir la imagen:**

```bash
# Desde la carpeta de la semana
cd bootcamp/week-XX/

# Construir imagen
docker-compose build

# O construir sin caché
docker-compose build --no-cache
```

**Iniciar el entorno:**

```bash
# Iniciar Jupyter Lab
docker-compose up

# Iniciar en background
docker-compose up -d

# Ver logs
docker-compose logs -f
```

**Acceder al contenedor:**

```bash
# Abrir shell en el contenedor
docker-compose exec jupyter bash

# Ejecutar comando específico
docker-compose exec jupyter python script.py
```

**Detener y limpiar:**

```bash
# Detener servicios
docker-compose down

# Detener y eliminar volúmenes
docker-compose down -v

# Limpiar imágenes no usadas
docker system prune -a
```

### Configuración de Notebooks

```python
# Snippet estándar al inicio de cada notebook
# ============================================
# CONFIGURACIÓN DEL ENTORNO
# ============================================

import warnings
warnings.filterwarnings('ignore')

import torch
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Configurar matplotlib
%matplotlib inline
plt.style.use('seaborn-v0_8-darkgrid')
plt.rcParams['figure.figsize'] = (10, 6)

# Configurar pandas
pd.set_option('display.max_columns', None)
pd.set_option('display.max_rows', 100)

# Configurar numpy
np.set_printoptions(precision=4, suppress=True)

# Configurar torch (si aplica)
if 'torch' in dir():
    torch.set_printoptions(precision=4, sci_mode=False)
    device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
    print(f"Device: {device}")
    if torch.cuda.is_available():
        print(f"GPU: {torch.cuda.get_device_name(0)}")

# Semilla para reproducibilidad
def set_seed(seed=42):
    """Configura semillas para reproducibilidad."""
    np.random.seed(seed)
    if 'torch' in dir():
        torch.manual_seed(seed)
        torch.cuda.manual_seed_all(seed)
        torch.backends.cudnn.deterministic = True
        torch.backends.cudnn.benchmark = False

set_seed(42)
print("✅ Entorno configurado correctamente")
```

### GPU Support (NVIDIA)

**Requisitos previos:**

```bash
# 1. Instalar NVIDIA Docker Toolkit
# Ubuntu/Debian:
sudo apt-get install -y nvidia-docker2
sudo systemctl restart docker

# 2. Verificar que funciona
docker run --rm --gpus all nvidia/cuda:11.7.0-base-ubuntu20.04 nvidia-smi
```

**Habilitar GPU en docker-compose:**

Descomentar la sección `deploy` en `docker-compose.yml`.

### .dockerignore

```gitignore
# Python
__pycache__/
*.py[cod]
*$py.class
*.so
.Python

# Jupyter
.ipynb_checkpoints/
*.ipynb_backup

# Cache
.cache/
*.egg-info/

# Data (para no copiar al build)
data/
checkpoints/
*.pth
*.pt
*.h5

# OS
.DS_Store
Thumbs.db

# IDE
.vscode/
.idea/
*.swp

# Solution folders
solution/
```

### Buenas Prácticas Docker

#### ✅ Hacer

```dockerfile
# Usar imágenes oficiales
FROM pytorch/pytorch:2.0.0-cuda11.7-cudnn8-runtime

# Mantener capas pequeñas
RUN apt-get update && apt-get install -y \
    git curl \
    && rm -rf /var/lib/apt/lists/*

# Copiar requirements primero (layer caching)
COPY requirements.txt .
RUN pip install -r requirements.txt

# Código al final
COPY . .
```

#### ❌ Evitar

```dockerfile
# No instalar todo junto
RUN apt-get update
RUN apt-get install git  # Múltiples capas innecesarias
RUN apt-get install curl

# No usar :latest
FROM pytorch/pytorch:latest  # ❌ No reproducible

# No instalar dependencias innecesarias
RUN pip install tensorflow keras  # Si solo usas PyTorch
```

---

## 🎓 Progresión de Dificultad

### Semanas 1-6: Fundamentos
- **Enfoque**: Python, NumPy, pandas, visualización
- **Proyectos**: Análisis de datos, visualizaciones
- **Sin PyTorch aún**: Preparar bases sólidas

### Semanas 7-12: PyTorch Básico
- **Enfoque**: Tensores, autograd, nn.Module básico
- **Proyectos**: Regresión, clasificación simple
- **Datasets**: MNIST, Fashion-MNIST

### Semanas 13-18: Redes Neuronales
- **Enfoque**: CNNs, RNNs, arquitecturas modernas
- **Proyectos**: Clasificación de imágenes, secuencias
- **Datasets**: CIFAR-10, datasets de texto

### Semanas 19-24: Avanzado
- **Enfoque**: Transfer learning, GANs, optimización, deploy
- **Proyectos**: Aplicaciones reales completas
- **Datasets**: Datasets personalizados, Kaggle

---

## 💡 Mejores Prácticas al Usar Copilot

### ✅ Hacer

- **Solicita explicaciones**: "Explica cómo funciona backward() en PyTorch"
- **Pide ejemplos**: "Muestra un ejemplo de custom Dataset con transformaciones"
- **Refactoriza**: "Mejora este código para seguir PEP 8"
- **Documenta**: "Añade docstrings a esta clase según Google style"
- **Optimiza**: "¿Cómo puedo hacer más eficiente este forward pass?"

### ❌ Evitar

- Copiar código sin entender
- No revisar código generado
- Ignorar warnings o errores
- Usar código desactualizado
- No probar el código generado

### 🎯 Interacciones Efectivas

```python
# Mal: Prompt vago
# "Crea una red neuronal"

# Bien: Prompt específico
# "Crea una CNN para clasificación de 10 clases con:
# - 2 capas convolucionales (3x3)
# - Max pooling después de cada conv
# - 2 capas fully connected
# - Dropout de 0.5
# - Incluye forward pass y comentarios explicativos"
```

---

## 📚 Referencias y Documentación

### Documentación Oficial

- [PyTorch Documentation](https://pytorch.org/docs/)
- [PyTorch Tutorials](https://pytorch.org/tutorials/)
- [Python 3.11+ Docs](https://docs.python.org/3/)
- [NumPy Documentation](https://numpy.org/doc/)

### Papers Fundamentales

Incluir en carpetas de recursos semanales:
- Paper original de la técnica
- Surveys y revisiones
- Implementaciones de referencia

### Estilo y Formato

- **PEP 8** para Python
- **Google Style** para docstrings
- **Markdown** estándar para documentación
- **Jupyter** best practices para notebooks

---

## 🔗 Navegación y Enlaces

### En READMEs

```markdown
## 🔗 Navegación

| ⬅️ Anterior | 🏠 Semana | ➡️ Siguiente |
|:-----------|:----------:|-------------:|
| [Week 11](../week-11/) | [README](README.md) | [Week 13](../week-13/) |
```

### En Notebooks

```python
# %% [markdown]
# ## 📚 Recursos
# 
# - [⬅️ Lección anterior](./01_concepto_previo.ipynb)
# - [➡️ Siguiente lección](./03_concepto_siguiente.ipynb)
# - [🏠 Índice de la semana](../README.md)
# - [📖 Documentación PyTorch](https://pytorch.org/docs/)
```

---

## ✅ Checklist de Verificación

### Al Crear una Semana Nueva

- [ ] README.md completo con objetivos y estructura
- [ ] Rúbrica de evaluación definida
- [ ] Dockerfile configurado para la semana
- [ ] docker-compose.yml con servicios necesarios
- [ ] requirements.txt con dependencias específicas
- [ ] .dockerignore configurado
- [ ] Material teórico (notebooks + markdown)
- [ ] Al menos 3-4 prácticas guiadas
- [ ] Proyecto integrador con README detallado
- [ ] Assets visuales (diagramas SVG)
- [ ] Recursos adicionales (papers, videos, links)
- [ ] Glosario de términos de la semana (README.md)
- [ ] Cheat Sheet de referencia rápida (cheat-sheet.md)
- [ ] Todo probado en Docker
- [ ] Código sigue convenciones
- [ ] Documentación completa en español

### Al Crear Material

- [ ] Código en inglés, comentarios en español
- [ ] Type hints en todas las funciones
- [ ] Docstrings en funciones y clases
- [ ] Ejemplos ejecutables y probados
- [ ] Visualizaciones claras y etiquetadas
- [ ] Tests o verificación cuando aplique
- [ ] Referencias a documentación oficial
- [ ] Progresión lógica de dificultad

---

## 🚀 Objetivos de Aprendizaje por Etapa

### Etapa 1: Fundamentos (Weeks 1-6)

**Al finalizar podrás:**
- Programar en Python moderno (3.11+)
- Manipular arrays con NumPy eficientemente
- Visualizar datos con matplotlib/seaborn
- Trabajar con pandas para análisis de datos
- Entender conceptos de álgebra lineal aplicados

### Etapa 2: PyTorch Básico (Weeks 7-12)

**Al finalizar podrás:**
- Crear y manipular tensores en PyTorch
- Implementar modelos con nn.Module
- Usar autograd para diferenciación automática
- Entrenar modelos con loops personalizados
- Implementar regresión y clasificación básicos

### Etapa 3: Redes Neuronales (Weeks 13-18)

**Al finalizar podrás:**
- Diseñar e implementar CNNs
- Crear RNNs para datos secuenciales
- Usar arquitecturas pre-entrenadas
- Implementar regularización y normalización
- Aplicar técnicas de data augmentation

### Etapa 4: Avanzado (Weeks 19-24)

**Al finalizar podrás:**
- Aplicar transfer learning efectivamente
- Optimizar hiperparámetros sistemáticamente
- Implementar modelos para producción
- Visualizar e interpretar modelos
- Trabajar con datasets reales y complejos

---

## 🎯 Resultado Esperado

Al completar las 24 semanas, el estudiante será capaz de:

1. **Implementar** modelos de deep learning desde cero en PyTorch
2. **Entrenar** redes neuronales con diferentes arquitecturas
3. **Evaluar** y optimizar modelos sistemáticamente
4. **Aplicar** técnicas modernas (transfer learning, regularización, etc.)
5. **Desplegar** modelos en entornos de producción
6. **Leer e implementar** papers de investigación
7. **Contribuir** a proyectos de ML/DL reales

---

## 📌 Notas Finales

- **Consistencia** en estilo y estructura es clave
- **Documentación** es tan importante como el código
- **Progresión gradual** evita frustración
- **Proyectos reales** motivan el aprendizaje
- **Comunidad** y colaboración enriquecen la experiencia

---

**Última actualización**: Febrero 2026  
**Versión**: 1.0  
**Mantenido por**: Equipo Bootcamp PyTorch

---

<p align="center">
  <strong>🎓 Bootcamp PyTorch Zero to Hero</strong><br>
  <em>De cero a deep learning en 24 semanas</em>
</p>

<p align="center">
  Hecho con ❤️ para la comunidad de ML/DL
</p>
