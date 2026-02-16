# 🐳 Imágenes Docker Optimizadas - Bootcamp PyTorch

> **Estrategia**: Mínimos recursos, máxima cobertura funcional

---

## 📊 Resumen Ejecutivo

| Etapa | Imagen Recomendada | Tamaño | Uso RAM | GPU |
|:------|:-------------------|:------:|:-------:|:---:|
| **Weeks 1-6** | `python:3.11-slim` | ~120MB | ~200MB | ❌ |
| **Weeks 7-12** | `pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime` | ~4.5GB | ~500MB | ✅ |
| **Weeks 13-18** | `pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime` | ~4.5GB | ~1GB | ✅ |
| **Weeks 19-24** | `pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime` | ~4.5GB | ~1-2GB | ✅ |

---

## 🎯 Estrategia de Optimización

### Principios Clave

1. **Alpine NO recomendado para PyTorch**: Problemas de compatibilidad con NumPy y PyTorch
2. **Slim sobre Standard**: Python slim reduce ~500MB vs versión completa
3. **Runtime sobre Devel**: Imágenes runtime son ~2GB más pequeñas que devel
4. **Multi-stage builds**: Para producción (Weeks 23-24)
5. **Layer caching**: requirements.txt primero, código después

---

## 📦 Imágenes Recomendadas por Etapa

### 🐍 Etapa 1: Fundamentos Python/NumPy (Weeks 1-6)

#### Opción 1: **Python Slim** (⭐ RECOMENDADA)

```dockerfile
FROM python:3.11-slim-bookworm

# Tamaño: ~120MB base
# RAM: ~200MB en ejecución
# GPU: No necesaria
```

**Ventajas:**
- ✅ Muy ligera (~120MB)
- ✅ Debian-based (compatible con la mayoría de paquetes)
- ✅ Suficiente para NumPy, Pandas, Matplotlib
- ✅ Rápida de descargar y construir

**Desventajas:**
- ⚠️ Requiere compiladores para algunos paquetes (build-essential)

#### Opción 2: Python Standard (Fallback)

```dockerfile
FROM python:3.11-bookworm

# Tamaño: ~1GB base
# RAM: ~250MB en ejecución
```

**Solo si:** Necesitas herramientas de desarrollo adicionales.

---

### 🔥 Etapa 2-4: PyTorch (Weeks 7-24)

#### Opción 1: **PyTorch Runtime** (⭐ RECOMENDADA)

```dockerfile
FROM pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime

# Tamaño: ~4.5GB
# RAM: ~500MB-2GB según uso
# GPU: CUDA 11.8 optimizado
```

**Ventajas:**
- ✅ PyTorch 2.2.0 pre-instalado
- ✅ CUDA 11.8 + cuDNN 8 optimizados
- ✅ Runtime-only (sin herramientas de compilación)
- ✅ Menor que devel (~2GB de ahorro)
- ✅ Compatible con la mayoría de GPUs modernas

**Desventajas:**
- ⚠️ Tamaño considerable (4.5GB)
- ⚠️ Requiere NVIDIA Container Toolkit para GPU

#### Opción 2: PyTorch CPU-only (Para laptops sin GPU)

```dockerfile
FROM pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime

# Al inicio del Dockerfile, forzar instalación CPU
RUN pip uninstall -y torch torchvision torchaudio && \
    pip install --no-cache-dir \
    torch==2.2.0+cpu \
    torchvision==0.17.0+cpu \
    torchaudio==2.2.0+cpu \
    -f https://download.pytorch.org/whl/torch_stable.html

# Tamaño: ~2GB (ahorro de 2.5GB)
# RAM: ~300-800MB según uso
```

**Ventajas:**
- ✅ Mucho más ligera sin CUDA
- ✅ Funciona en cualquier máquina
- ✅ Ideal para desarrollo y pruebas

**Desventajas:**
- ⚠️ Entrenamiento 10-50x más lento que GPU

#### Opción 3: Build desde Debian Slim + PyTorch

```dockerfile
FROM python:3.11-slim-bookworm

# Instalar PyTorch CPU-only desde cero
RUN pip install --no-cache-dir \
    torch==2.2.0+cpu \
    torchvision==0.17.0+cpu \
    torchaudio==2.2.0+cpu \
    -f https://download.pytorch.org/whl/torch_stable.html

# Tamaño: ~1.8GB
# RAM: ~300-800MB
```

**Ventajas:**
- ✅ Más control sobre dependencias
- ✅ Ligeramente más pequeña que imagen oficial CPU

**Desventajas:**
- ⚠️ Más lenta de construir
- ⚠️ Potenciales problemas de compatibilidad

---

## 🏗️ Dockerfiles Optimizados

### Week 1-6: Python Fundamentos

```dockerfile
# ============================================
# STAGE: Base Image
# ============================================
FROM python:3.11-slim-bookworm AS base

LABEL maintainer="Bootcamp PyTorch"
LABEL description="Entorno optimizado Weeks 1-6"

# Variables de entorno
ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PIP_NO_CACHE_DIR=1 \
    PIP_DISABLE_PIP_VERSION_CHECK=1 \
    DEBIAN_FRONTEND=noninteractive

# ============================================
# STAGE: Builder (dependencias compiladas)
# ============================================
FROM base AS builder

# Instalar solo lo necesario para compilar
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Copiar requirements y crear venv
WORKDIR /build
COPY requirements.txt .

# Instalar en virtual environment para aislar
RUN python -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# ============================================
# STAGE: Runtime (imagen final)
# ============================================
FROM base AS runtime

# Copiar solo el venv (sin build tools)
COPY --from=builder /opt/venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# Instalar solo runtime dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /bootcamp

# Jupyter config
ENV JUPYTER_ENABLE_LAB=yes
EXPOSE 8888

CMD ["jupyter", "lab", \
     "--ip=0.0.0.0", \
     "--port=8888", \
     "--no-browser", \
     "--allow-root", \
     "--NotebookApp.token=bootcamp"]
```

**Resultado:**
- 📦 Tamaño final: ~400-500MB (vs ~1.2GB sin optimizar)
- 🚀 Ahorro: ~60% del tamaño
- ⚡ Build time: ~3-5 min primera vez, <30s con cache

---

### Week 7-24: PyTorch Optimizado

```dockerfile
# ============================================
# IMAGEN BASE: PyTorch Runtime
# ============================================
FROM pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime

LABEL maintainer="Bootcamp PyTorch"
LABEL description="Entorno optimizado Weeks 7-24"

# Variables de entorno
ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PIP_NO_CACHE_DIR=1 \
    DEBIAN_FRONTEND=noninteractive \
    TORCH_HOME=/bootcamp/.cache/torch \
    JUPYTER_ENABLE_LAB=yes

# Instalar dependencias mínimas del sistema
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /bootcamp

# Copiar requirements
COPY requirements.txt .

# Instalar dependencias Python
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Crear directorios
RUN mkdir -p data checkpoints .cache

# Exponer puerto Jupyter
EXPOSE 8888

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s \
    CMD curl -f http://localhost:8888/api || exit 1

CMD ["jupyter", "lab", \
     "--ip=0.0.0.0", \
     "--port=8888", \
     "--no-browser", \
     "--allow-root", \
     "--NotebookApp.token=bootcamp"]
```

**Resultado:**
- 📦 Tamaño: ~5GB (vs ~7GB con imagen devel)
- 🚀 Ahorro: ~28% vs devel
- ⚡ GPU-ready con CUDA

---

## 🎯 Requirements.txt Optimizados

### Weeks 1-6: Python Fundamentos

```txt
# Core científico (total ~150MB)
numpy==1.26.4
pandas==2.2.0
matplotlib==3.8.2
seaborn==0.13.2

# Jupyter
jupyterlab==4.0.13
ipywidgets==8.1.2
ipykernel==6.29.2

# Utilidades
tqdm==4.66.2
pillow==10.2.0
scikit-learn==1.4.1.post1

# Total instalado: ~150-200MB
```

### Weeks 7-24: PyTorch

```txt
# Jupyter (PyTorch ya está en imagen base)
jupyterlab==4.0.13
ipywidgets==8.1.2
ipykernel==6.29.2

# Científico adicional
numpy==1.26.4
pandas==2.2.0
matplotlib==3.8.2
seaborn==0.13.2

# ML/DL Tools
tensorboard==2.16.2
torchinfo==1.8.0
tqdm==4.66.2
scikit-learn==1.4.1.post1

# Visión (solo si es necesario)
# opencv-python-headless==4.9.0.80  # +100MB
# albumentations==1.4.0              # +50MB

# NLP (solo weeks 19-24)
# transformers==4.38.1               # +500MB
# tokenizers==0.15.2                 # +30MB

# Total adicional: ~200-300MB (sin opcionales)
# Total con opcionales: ~1GB
```

---

## 🔧 docker-compose.yml Optimizado

```yaml
version: '3.8'

services:
  jupyter:
    build:
      context: .
      dockerfile: Dockerfile
      # Cache de layers
      cache_from:
        - bootcamp-week-${WEEK_NUM:-01}:latest
    
    image: bootcamp-week-${WEEK_NUM:-01}:latest
    container_name: bootcamp-week-${WEEK_NUM:-01}
    
    ports:
      - "${JUPYTER_PORT:-8888}:8888"
    
    volumes:
      # Bind mounts específicos (no todo el directorio)
      - ./1-teoria:/bootcamp/1-teoria:ro
      - ./2-practicas:/bootcamp/2-practicas
      - ./3-proyecto:/bootcamp/3-proyecto
      - ./data:/bootcamp/data
      
      # Named volumes para cache
      - checkpoints:/bootcamp/checkpoints
      - cache:/bootcamp/.cache
    
    environment:
      - JUPYTER_TOKEN=${JUPYTER_TOKEN:-bootcamp}
      - PYTHONPATH=/bootcamp
      - WEEK_NUM=${WEEK_NUM:-01}
    
    # Recursos limitados (ajustar según máquina)
    deploy:
      resources:
        limits:
          cpus: '4'
          memory: 8G
        reservations:
          cpus: '2'
          memory: 2G
          # GPU solo si está disponible
          devices:
            - driver: nvidia
              count: 1
              capabilities: [gpu]
    
    # Restart policy
    restart: unless-stopped
    
    # Health check
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:8888/api"]
      interval: 30s
      timeout: 3s
      retries: 3
      start_period: 10s
    
    stdin_open: true
    tty: true

volumes:
  checkpoints:
    driver: local
  cache:
    driver: local

networks:
  default:
    name: bootcamp-network
```

---

## 🚀 Comandos Optimizados

### Construcción Paralela

```bash
# Build con caché y compresión
docker build \
  --build-arg BUILDKIT_INLINE_CACHE=1 \
  --compress \
  --tag bootcamp-week-01:latest \
  --file Dockerfile \
  .

# Build multi-stage con target específico
docker build \
  --target runtime \
  --tag bootcamp-week-01:latest \
  .
```

### Limpieza de Cache

```bash
# Limpiar build cache (libera ~2-5GB)
docker builder prune -a -f

# Limpiar imágenes no usadas
docker image prune -a -f

# Limpiar volúmenes huérfanos
docker volume prune -f

# Limpieza completa (¡cuidado!)
docker system prune -a --volumes -f
```

### Inspeccionar Tamaño

```bash
# Ver capas de imagen
docker history bootcamp-week-01:latest

# Ver tamaño total
docker images bootcamp-week-01

# Análisis detallado con dive
docker run --rm -it \
  -v /var/run/docker.sock:/var/run/docker.sock \
  wagoodman/dive:latest bootcamp-week-01:latest
```

---

## 📊 Comparativa de Tamaños

### Sin Optimización

```
python:3.11                          1.01GB
+ NumPy, Pandas, Jupyter            +350MB
+ Matplotlib, Seaborn               +150MB
+ Build tools (gcc, etc)            +500MB
=====================================
TOTAL Week 1-6:                      ~2GB ❌
```

### Con Optimización (Multi-stage)

```
python:3.11-slim                     120MB
+ NumPy, Pandas, Jupyter            +250MB
+ Matplotlib, Seaborn               +100MB
+ Runtime deps only                  +30MB
=====================================
TOTAL Week 1-6:                      ~500MB ✅
AHORRO:                              ~75%
```

### PyTorch

```
pytorch/pytorch:devel               ~7GB ❌
pytorch/pytorch:runtime             ~4.5GB ✅
python:slim + torch CPU             ~1.8GB ✅✅ (sin GPU)
```

---

## 🎯 Recomendaciones Finales

### Para Desarrollo Local (Laptop)

```dockerfile
# Weeks 1-6: Python slim multi-stage
FROM python:3.11-slim-bookworm
# ↳ Tamaño: ~500MB

# Weeks 7-24: PyTorch CPU-only
FROM python:3.11-slim-bookworm
RUN pip install torch torchvision --index-url https://download.pytorch.org/whl/cpu
# ↳ Tamaño: ~1.8GB
```

**Ventajas:**
- ✅ Funcionan en cualquier máquina
- ✅ Rápido de descargar y construir
- ✅ Bajo consumo de RAM

**Desventajas:**
- ⚠️ Entrenamiento lento (CPU-only)

### Para Servidor con GPU

```dockerfile
# Weeks 7-24: PyTorch Runtime GPU
FROM pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime
# ↳ Tamaño: ~5GB
```

**Ventajas:**
- ✅ GPU-ready out of the box
- ✅ CUDA optimizado
- ✅ Velocidad de entrenamiento máxima

**Desventajas:**
- ⚠️ Requiere GPU NVIDIA
- ⚠️ Imagen más grande

### Para Producción (Weeks 23-24)

```dockerfile
# Multi-stage ultra-optimizado
FROM pytorch/pytorch:2.2.0-cuda11.8-cudnn8-runtime AS builder
# ... instalar deps y entrenar modelo ...

FROM python:3.11-slim-bookworm AS runtime
COPY --from=builder /model /model
RUN pip install torch torchvision --index-url https://download.pytorch.org/whl/cpu
# ↳ Tamaño: ~800MB (solo inferencia)
```

---

## 💡 Tips de Optimización

### 1. **Layer Caching**

```dockerfile
# ❌ MAL: Cambios invalidan todo el cache
COPY . /app
RUN pip install -r requirements.txt

# ✅ BIEN: requirements primero (rara vez cambia)
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . /app
```

### 2. **Combinar RUN Commands**

```dockerfile
# ❌ MAL: Múltiples layers
RUN apt-get update
RUN apt-get install -y git
RUN apt-get install -y curl
RUN rm -rf /var/lib/apt/lists/*

# ✅ BIEN: Un solo layer
RUN apt-get update && apt-get install -y --no-install-recommends \
    git curl \
    && rm -rf /var/lib/apt/lists/*
```

### 3. **Usar .dockerignore**

> ✅ **Nota**: El bootcamp ya incluye `.dockerignore` en la raíz y en cada una de las 24 semanas.

**Ubicaciones:**
- `/.dockerignore` - Configuración exhaustiva (79 líneas) para builds desde la raíz
- `/bootcamp/week-XX/.dockerignore` - Configuración enfocada (33 líneas) por semana

**Ejemplo de contenido (configuración de semana):**

```gitignore
# Evita copiar archivos innecesarios al build context
__pycache__/
*.pyc
.git/
.vscode/
data/
checkpoints/
*.pth
*.pt
.ipynb_checkpoints/
solution/
```

**Beneficios:**
- ⚡ Reduce contexto de build en 50-90%
- 🚀 Acelera builds subsecuentes
- 🔒 Evita copiar archivos sensibles
- 💾 Optimiza uso de cache de Docker

Ver [estructura-bootcamp.md](estructura-bootcamp.md#-archivos-dockerignore) para detalles completos.

### 4. **BuildKit Features**

```bash
# Habilitar BuildKit para builds más rápidos
export DOCKER_BUILDKIT=1

# Build con cache externo
docker build \
  --build-arg BUILDKIT_INLINE_CACHE=1 \
  --cache-from bootcamp-base:latest \
  -t bootcamp-week-01 .
```

---

## 📦 Resumen de Recomendaciones

| Escenario | Imagen Base | Tamaño | RAM |
|:----------|:------------|:------:|:---:|
| **Dev local (Weeks 1-6)** | `python:3.11-slim` | ~500MB | ~200MB |
| **Dev local (Weeks 7-24, CPU)** | `python:3.11-slim` + torch CPU | ~1.8GB | ~500MB |
| **Servidor GPU (Weeks 7-24)** | `pytorch/pytorch:2.2.0-...-runtime` | ~5GB | ~1GB |
| **Producción (inference)** | Multi-stage slim | ~800MB | ~300MB |

---

## 🔗 Referencias

- [Python Official Images](https://hub.docker.com/_/python)
- [PyTorch Docker Images](https://hub.docker.com/r/pytorch/pytorch)
- [Docker Multi-stage Builds](https://docs.docker.com/build/building/multi-stage/)
- [Docker Best Practices](https://docs.docker.com/develop/dev-best-practices/)

---

_Última actualización: Febrero 2026 | Bootcamp PyTorch Zero to Hero_
