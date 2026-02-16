# Guía de Contribución

¡Gracias por tu interés en contribuir al Bootcamp PyTorch Zero to Hero! 🎉

Este documento proporciona las directrices para contribuir al proyecto.

## 📋 Tabla de Contenidos

- [Código de Conducta](#código-de-conducta)
- [¿Cómo puedo contribuir?](#cómo-puedo-contribuir)
- [Configuración del entorno](#configuración-del-entorno)
- [Flujo de trabajo](#flujo-de-trabajo)
- [Guías de estilo](#guías-de-estilo)
- [Commits](#commits)
- [¿Preguntas?](#preguntas)

---

## Código de Conducta

Este proyecto se adhiere al [Código de Conducta](CODE_OF_CONDUCT.md). Al participar, se espera que mantengas este código. Por favor, reporta comportamientos inaceptables a [bootcamp-pytorch@epti.dev](mailto:bootcamp-pytorch@epti.dev).

---

## ¿Cómo puedo contribuir?

### 🐛 Reportar Bugs

Antes de crear un reporte de bug, por favor:

1. **Verifica** si ya existe un issue similar
2. **Usa** la plantilla de issue para bugs
3. **Incluye** toda la información solicitada

**Información necesaria:**
- Descripción clara del problema
- Pasos para reproducirlo (incluyendo comandos Docker)
- Comportamiento esperado vs real
- Versión de PyTorch, Python, CUDA (si aplica)
- Screenshots o outputs de error
- Información del sistema (OS, Docker version)

### ✨ Sugerir Mejoras

Para sugerir nuevas características o mejoras:

1. **Abre un issue** describiendo tu propuesta
2. **Explica** por qué sería útil para el bootcamp
3. **Proporciona** ejemplos de uso cuando sea posible
4. **Considera** el nivel de dificultad apropiado para estudiantes

### 📝 Mejorar Documentación

La documentación es crucial para un proyecto educativo:

- Corregir errores tipográficos o técnicos
- Clarificar explicaciones confusas en notebooks
- Agregar ejemplos adicionales con explicaciones
- Traducir contenido
- Mejorar diagramas de arquitecturas de redes
- Documentar casos de uso reales

### 💻 Contribuir Código

#### Áreas de contribución:

1. **Notebooks y Ejercicios**
   - Nuevos notebooks de teoría con explicaciones claras
   - Ejercicios prácticos adicionales
   - Soluciones alternativas comentadas
   - Visualizaciones de conceptos complejos

2. **Proyectos**
   - Nuevos proyectos integradores con datasets
   - Mejoras a proyectos existentes
   - Notebooks starter con TODOs educativos

3. **Recursos**
   - Papers relevantes con resúmenes
   - Videos tutoriales (enlaces)
   - Datasets interesantes y bien documentados
   - Enlaces a documentación útil

4. **Docker y Herramientas**
   - Optimizaciones de Dockerfiles
   - Scripts de automatización
   - Utilidades para estudiantes
   - Configuraciones de desarrollo

5. **Modelos y Arquitecturas**
   - Implementaciones de arquitecturas modernas
   - Ejemplos de transfer learning
   - Técnicas de optimización
   - Interpretabilidad de modelos

---

## Configuración del entorno

### 1. Fork y Clone

```bash
# Fork el repositorio en GitHub
# Luego clona tu fork
git clone https://github.com/TU-USUARIO/bc-pytorch.git
cd bc-pytorch

# Agrega el repositorio original como upstream
git remote add upstream https://github.com/epti-dev/bc-pytorch.git
```

### 2. Instalar Docker

Asegúrate de tener Docker y Docker Compose instalados:

```bash
# Verificar instalación
docker --version
docker-compose --version

# Para GPU (opcional)
docker run --rm --gpus all nvidia/cuda:11.7.0-base-ubuntu20.04 nvidia-smi
```

### 3. Configurar VS Code

Las extensiones recomendadas se instalarán automáticamente al abrir el proyecto.

Extensiones clave:
- Python
- Jupyter
- Docker
- Pylance

---

## Flujo de trabajo

### 1. Sincronizar con upstream

```bash
git checkout main
git fetch upstream
git merge upstream/main
```

### 2. Crear una rama

```bash
# Usar nomenclatura descriptiva
git checkout -b feature/week-05-cnn-visualization
git checkout -b fix/week-12-tensor-shape-error
git checkout -b docs/improve-readme-week-08
```

### 3. Hacer cambios

#### Para Notebooks:

```bash
# Navegar a la semana
cd bootcamp/week-XX

# Iniciar Docker
docker-compose up

# Editar notebooks en Jupyter Lab (localhost:8888)
# Token: bootcamp
```

#### Para Código Python:

- Escribe código limpio y bien documentado
- Usa type hints en todas las funciones
- Sigue PEP 8
- Agrega docstrings estilo Google
- Comenta secciones educativas en español

#### Para Dockerfile:

- Optimiza capas para reducir tamaño
- Documenta cambios importantes
- Prueba la construcción localmente

### 4. Commit

```bash
# Usar Conventional Commits
git add .
git commit -m "feat(week-05): add CNN visualization with GradCAM"
```

**Tipos de commit:**
- `feat`: Nueva característica (notebook, ejercicio, proyecto)
- `fix`: Corrección de bug
- `docs`: Solo documentación
- `style`: Formateo, sin cambios funcionales
- `refactor`: Refactorización de código
- `perf`: Mejoras de rendimiento
- `test`: Agregar tests
- `chore`: Mantenimiento (Docker, dependencias)

### 5. Push y Pull Request

```bash
git push origin feature/tu-rama
```

Luego:
- Abre un Pull Request en GitHub
- Describe tus cambios claramente
- Referencia issues relacionados
- Espera revisión de los mantenedores

---

## Guías de estilo

### Python/PyTorch

**✅ Hacer:**

```python
# Type hints siempre
def train_model(
    model: nn.Module,
    train_loader: DataLoader,
    criterion: nn.Module,
    optimizer: torch.optim.Optimizer,
    epochs: int
) -> dict:
    """Entrena el modelo por el número de épocas especificado.
    
    Args:
        model: Modelo de PyTorch a entrenar
        train_loader: DataLoader con datos de entrenamiento
        criterion: Función de pérdida
        optimizer: Optimizador
        epochs: Número de épocas
    
    Returns:
        dict: Métricas de entrenamiento por época
    """
    pass

# Nombres descriptivos en inglés
class ConvolutionalNetwork(nn.Module):
    """Red convolucional para clasificación de imágenes."""
    
    def __init__(self, num_classes: int = 10):
        super().__init__()
        self.conv1 = nn.Conv2d(3, 32, kernel_size=3)
        self.fc = nn.Linear(32 * 6 * 6, num_classes)
    
    def forward(self, x: torch.Tensor) -> torch.Tensor:
        # Comentarios explicativos en español
        x = F.relu(self.conv1(x))  # Primera capa convolucional
        return self.fc(x.flatten(1))

# Usar device apropiadamente
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
model = model.to(device)
```

**❌ Evitar:**

```python
# Sin type hints
def train(m, d, c, o, e):
    pass

# Nombres no descriptivos
x = nn.Conv2d(3, 32, 3)
fc1 = nn.Linear(1000, 10)

# Sin comentarios educativos
class Net(nn.Module):
    def __init__(self):
        super().__init__()
        self.c1 = nn.Conv2d(3, 32, 3)

# Hardcodear device
model = model.to('cuda')  # ❌ Usar variable device
```

### Notebooks Jupyter

**Estructura de celdas:**

```python
# %% [markdown]
# ## Sección X: Título Descriptivo
# 
# Explicación del concepto que se va a aprender.
# Incluir contexto y motivación.

# %% [code]
import torch
import torch.nn as nn
import matplotlib.pyplot as plt

# Configurar para reproducibilidad
torch.manual_seed(42)

# Crear ejemplo
tensor = torch.randn(3, 4, device=device)
print(f"Shape: {tensor.shape}")

# %% [markdown]
# **Resultado esperado**: Tensor de 3x4 con valores aleatorios.
# 
# 💡 **Tip**: Los tensores son la estructura fundamental en PyTorch.
```

### Markdown

- Usar headers jerárquicos (#, ##, ###)
- Incluir emojis para mejorar legibilidad (con moderación)
- Code blocks con lenguaje especificado
- Enlaces descriptivos
- Listas con viñetas o numeración consistente

### Nomenclatura

| Tipo | Convención | Ejemplo |
|------|-----------|---------|
| Variables/Funciones | snake_case | `train_model()` |
| Constantes | UPPER_SNAKE_CASE | `LEARNING_RATE` |
| Clases | PascalCase | `ConvolutionalNetwork` |
| Archivos Python | snake_case | `model_architectures.py` |
| Notebooks | kebab-case | `01-intro-tensors.ipynb` |
| Carpetas | kebab-case | `2-practicas/` |

### Comentarios

```python
# ❌ Comentarios obvios
x = 5  # asigna 5 a x

# ✅ Comentarios educativos
# Usamos CrossEntropyLoss porque combina LogSoftmax y NLLLoss.
# Esto es más estable numéricamente que aplicarlos por separado.
criterion = nn.CrossEntropyLoss()
```

### Dockerfiles

```dockerfile
# ✅ Buenas prácticas
FROM pytorch/pytorch:2.0.0-cuda11.7-cudnn8-runtime

# Metadata
LABEL maintainer="Bootcamp PyTorch"
LABEL description="Week XX - Tema"

# Combinar comandos para reducir capas
RUN apt-get update && apt-get install -y \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Copiar requirements primero (layer caching)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
```

---

## Commits

### Conventional Commits

Usamos [Conventional Commits](https://www.conventionalcommits.org/) para mensajes claros:

```
<tipo>(<alcance>): <descripción>

[cuerpo opcional]

[footer opcional]
```

#### Tipos:

- `feat`: Nueva característica
- `fix`: Corrección de bug
- `docs`: Solo documentación
- `style`: Formateo (no afecta código)
- `refactor`: Refactorización
- `perf`: Mejoras de rendimiento
- `test`: Agregar tests
- `chore`: Mantenimiento (Docker, dependencias)

#### Ejemplos:

```bash
feat(week-13): add RNN sentiment analysis project
fix(week-07): correct autograd backward propagation example
docs(readme): update Docker GPU instructions
style(week-10): format notebooks with black
refactor(week-15): simplify transfer learning implementation
perf(week-18): optimize data loading with num_workers
test(week-09): add unit tests for custom Dataset
chore(deps): update PyTorch to 2.1.0
```

### Alcance

El alcance debe indicar la semana o área afectada:

- `week-01`, `week-02`, etc. para semanas específicas
- `docs` para documentación general
- `docker` para configuraciones Docker
- `deps` para dependencias
- `ci` para continuous integration

---

## Proceso de revisión

### Pull Requests

Tu PR será revisado por los mantenedores. Esperamos:

1. **Código funcional**: Sin errores, ejecutable en Docker
2. **Tests**: Si aplica (notebooks ejecutables)
3. **Documentación**: Actualizada y clara
4. **Estilo**: Siguiendo las guías (PEP 8, type hints)
5. **Commits**: Con mensajes claros y descriptivos

### Feedback

- Sé receptivo a comentarios
- Haz cambios solicitados
- Participa en la discusión
- Prueba sugerencias en Docker

### Checklist PR

- [ ] El código ejecuta sin errores en Docker
- [ ] Los notebooks están limpios (sin outputs si no son necesarios)
- [ ] Seguí PEP 8 y agregué type hints
- [ ] Documenté funciones con docstrings
- [ ] Actualicé README si es necesario
- [ ] Probé con CPU y GPU (si applica)
- [ ] Los commits siguen Conventional Commits

---

## ¿Preguntas?

Si tienes dudas:

- 💬 [GitHub Discussions](https://github.com/epti-dev/bc-pytorch/discussions)
- 🐛 [GitHub Issues](https://github.com/epti-dev/bc-pytorch/issues)
- 📧 Email: [bootcamp-pytorch@epti.dev](mailto:bootcamp-pytorch@epti.dev)

---

## Reconocimiento

Todos los contribuidores serán reconocidos en:

- README principal
- Página de agradecimientos
- Release notes
- CONTRIBUTORS.md

¡Gracias por contribuir! 🎉

---

*Última actualización: Febrero 2026*
