<p align="center">
  <img src="_assets/bootcamp-header.svg" alt="Bootcamp PyTorch Zero to Hero" width="800">
</p>

<p align="center">
  <a href="https://github.com/epti-dev/bc-pytorch/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License MIT"></a>
  <a href="#"><img src="https://img.shields.io/badge/semanas-24-yellow.svg" alt="24 Semanas"></a>
  <a href="#"><img src="https://img.shields.io/badge/horas-168-orange.svg" alt="168 Horas"></a>
  <a href="#"><img src="https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?logo=pytorch" alt="PyTorch 2.0+"></a>
  <a href="#"><img src="https://img.shields.io/badge/Python-3.11+-3776AB?logo=python" alt="Python 3.11+"></a>
  <a href="#"><img src="https://img.shields.io/badge/Docker-Enabled-2496ED?logo=docker" alt="Docker"></a>
  <a href="CONTRIBUTING.md"><img src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square" alt="PRs Welcome"></a>
</p>

<p align="center">
  <a href="README_EN.md"><img src="https://img.shields.io/badge/🇺🇸_English-0969DA?style=for-the-badge&logoColor=white" alt="English Version"></a>
</p>

---

## 📋 Descripción

Bootcamp intensivo de **24 semanas (6 meses)** diseñado para llevar a estudiantes desde cero hasta un nivel competente en Deep Learning con PyTorch. Con una dedicación de **7 horas semanales**, aprenderás desde fundamentos de Python hasta implementación de modelos avanzados en producción.

### 🎯 Objetivos

Al finalizar el bootcamp, los estudiantes serán capaces de:

- ✅ Dominar Python moderno (3.11+) y librerías científicas (NumPy, pandas, matplotlib)
- ✅ Implementar redes neuronales desde cero con PyTorch
- ✅ Diseñar y entrenar CNNs para visión computacional
- ✅ Crear modelos RNN/LSTM para procesamiento de secuencias
- ✅ Aplicar transfer learning usando arquitecturas pre-entrenadas
- ✅ Optimizar hiperparámetros y mejorar el rendimiento de modelos
- ✅ Desplegar modelos en producción usando Docker
- ✅ Leer e implementar papers de investigación en deep learning

### 🐳 ¿Por qué Docker?

> **Entornos reproducibles desde el día 1** - Mismo ambiente en cualquier máquina, sin conflictos de dependencias.

Todo el bootcamp se ejecuta en contenedores Docker, garantizando que cada estudiante tenga exactamente el mismo entorno de desarrollo, independientemente de su sistema operativo. Soporte completo para GPU mediante NVIDIA Container Toolkit.

### 🚀 ¿Por qué PyTorch?

> **El framework preferido en investigación y producción** - Dinámico, pythónico y con un ecosistema robusto.

PyTorch 2.0+ ofrece la flexibilidad de desarrollo que necesitas y el rendimiento que demandan las aplicaciones reales. Su sintaxis intuitiva y debugging sencillo lo hacen ideal para aprender deep learning.

---

## 🗓️ Estructura del Bootcamp

| Etapa | Semanas | Horas | Temas Principales |
|:-----:|:-------:|:-----:|-------------------|
| **Fundamentos Python/NumPy** | 1-6 | 42h | Python moderno, NumPy, visualización, álgebra lineal |
| **PyTorch Básico** | 7-12 | 42h | Tensores, autograd, nn.Module, optimización |
| **Redes Neuronales** | 13-18 | 42h | CNNs, RNNs, arquitecturas modernas, regularización |
| **Avanzado y Deploy** | 19-24 | 42h | Transfer learning, interpretabilidad, producción |

**Total: 24 semanas** | **168 horas** de formación práctica intensiva

---

## 📚 Contenido por Semana

Cada semana incluye:

```
bootcamp/week-XX/
├── README.md                 # Descripción y objetivos
├── rubrica-evaluacion.md     # Criterios de evaluación
├── Dockerfile                # Imagen Docker personalizada
├── docker-compose.yml        # Configuración de servicios
├── requirements.txt          # Dependencias Python
├── 0-assets/                 # Imágenes y diagramas
├── 1-teoria/                 # Material teórico
│   ├── *.md                  # Explicaciones conceptuales
│   └── notebooks/            # Notebooks interactivos
├── 2-practicas/              # Ejercicios guiados
│   ├── practica-01-nombre/
│   │   ├── README.md
│   │   ├── starter/          # Código inicial
│   │   └── solution/         # Solución de referencia
│   └── practica-02-nombre/
├── 3-proyecto/               # 🎯 ÚNICO ENTREGABLE
│   ├── README.md
│   ├── starter/
│   │   └── notebook.ipynb
│   └── solution/
│       └── notebook.ipynb
├── 4-recursos/               # Material complementario
│   ├── papers/               # Papers relevantes
│   ├── videos/               # Enlaces a videos
│   └── webgrafia/            # Artículos y tutoriales
└── 5-glosario/               # Términos y referencia
    ├── README.md             # Glosario de conceptos
    └── cheat-sheet.md        # Referencia rápida
```

### 🔑 Componentes Clave

- 📖 **Teoría**: Conceptos fundamentales con notebooks interactivos ejecutables
- 💻 **Práctica**: Ejercicios progresivos con datasets reales
- 📝 **Evaluación**: Evidencias de conocimiento, desempeño y producto
- 🐳 **Docker**: Entorno completamente containerizado con Jupyter Lab
- 🎓 **Recursos**: Papers, glosarios, cheat sheets y material complementario

---

## 🛠️ Stack Tecnológico

| Tecnología | Versión | Uso |
|------------|---------|-----|
| Python | 3.11+ | Lenguaje principal |
| PyTorch | 2.0+ | Framework de deep learning |
| NumPy | 1.24+ | Computación científica |
| pandas | 2.0+ | Análisis de datos |
| matplotlib | 3.7+ | Visualización |
| Jupyter Lab | 4.0+ | Desarrollo interactivo |
| Docker | 24+ | Containerización |
| CUDA | 11.7+ | Aceleración GPU (opcional) |
| Git | 2.30+ | Control de versiones |

**Imagen base Docker**: `pytorch/pytorch:2.0.0-cuda11.7-cudnn8-runtime`

---

## 🚀 Inicio Rápido

### Prerrequisitos

- **Docker** 24+ con Docker Compose
- **Git** para control de versiones
- **NVIDIA Docker** (opcional, para GPU)
- **VS Code** (recomendado) con extensiones incluidas
- **8GB RAM mínimo** (16GB recomendado)

### 1. Clonar el Repositorio

```bash
git clone https://github.com/epti-dev/bc-pytorch.git
cd bc-pytorch
```

### 2. Instalar Extensiones de VS Code

```bash
# Abrir en VS Code
code .

# Las extensiones recomendadas aparecerán automáticamente
# O ejecutar: Ctrl+Shift+P → "Extensions: Show Recommended Extensions"
```

### 3. Iniciar Week-01 con Docker

```bash
cd bootcamp/week-01

# Construir la imagen Docker
docker-compose build

# Iniciar Jupyter Lab
docker-compose up
```

### 4. Acceder a Jupyter Lab

Abre tu navegador en `http://localhost:8888` con token `bootcamp`

### 5. Seguir las Instrucciones

Cada semana contiene un `README.md` con objetivos, teoría y proyecto detallado.

---

## 📊 Metodología de Aprendizaje

### Estrategias Didácticas

- 🎯 **Learning by Doing**: Cada concepto se aprende implementándolo
- 🧩 **Progresión Gradual**: De simple a complejo, sin saltos abruptos
- 🏗️ **Proyectos Reales**: Casos de uso con datasets del mundo real
- 📊 **Visualización**: Gráficos y diagramas para conceptos complejos
- 🔬 **Experimentación**: Notebooks interactivos para explorar

### Distribución del Tiempo (7h/semana)

- **Teoría**: 2 horas (notebooks interactivos)
- **Prácticas**: 2-2.5 horas (ejercicios guiados)
- **Proyecto**: 2.5-3 horas (**único entregable**)

### Evaluación

Cada semana incluye tres tipos de evidencias:

1. **Conocimiento 🧠** (30%): Comprensión de conceptos fundamentales
2. **Desempeño 💪** (40%): Código funcional, organizado y documentado
3. **Producto 📦** (30%): Proyecto semanal completado

**Criterio de aprobación**: Mínimo 70% en cada tipo de evidencia

---

## 🐳 Trabajar con Docker

### Comandos Básicos

```bash
# Construir imagen de una semana
cd bootcamp/week-XX
docker-compose build

# Iniciar servicios
docker-compose up

# Iniciar en background
docker-compose up -d

# Ver logs
docker-compose logs -f

# Acceder al contenedor
docker-compose exec jupyter bash

# Detener servicios
docker-compose down
```

### Usar GPU (NVIDIA)

Descomentar la sección `deploy` en `docker-compose.yml`:

```yaml
deploy:
  resources:
    reservations:
      devices:
        - driver: nvidia
          count: all
          capabilities: [gpu]
```

### Verificar GPU en PyTorch

```python
import torch
print(f"CUDA disponible: {torch.cuda.is_available()}")
print(f"GPU: {torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'N/A'}")
```

---

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Este es un proyecto educativo de código abierto.

### Cómo Contribuir

1. Lee la [Guía de Contribución](CONTRIBUTING.md)
2. Revisa el [Código de Conducta](CODE_OF_CONDUCT.md)
3. Fork del repositorio
4. Crea tu rama (`git checkout -b feature/nueva-practica`)
5. Commit con [Conventional Commits](https://www.conventionalcommits.org/) (`git commit -m 'feat: add CNN visualization exercise'`)
6. Push a la rama (`git push origin feature/nueva-practica`)
7. Abre un Pull Request

### 📋 Áreas de Contribución

- ✨ Ejercicios adicionales con nuevos datasets
- 📚 Mejoras en documentación y tutoriales
- 🐛 Corrección de errores en código o notebooks
- 🎨 Recursos visuales (diagramas de arquitecturas)
- 🌐 Traducciones a otros idiomas
- 📹 Videos tutoriales explicativos
- 🐳 Optimizaciones en configuraciones Docker

---

## 📞 Soporte

- 💬 Discussions: [GitHub Discussions](https://github.com/epti-dev/bc-pytorch/discussions)
- 🐛 Issues: [GitHub Issues](https://github.com/epti-dev/bc-pytorch/issues)
- 📧 Email: [bootcamp-pytorch@epti.dev](mailto:bootcamp-pytorch@epti.dev)

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

---

## 🏆 Agradecimientos

- [PyTorch Team](https://pytorch.org/) - Por el mejor framework de deep learning
- [Fast.ai](https://www.fast.ai/) - Por democratizar el deep learning
- [Papers with Code](https://paperswithcode.com/) - Por conectar investigación con implementación
- [Kaggle](https://www.kaggle.com/) - Por datasets y competencias educativas
- Comunidad de ML/DL - Por recursos, papers y ejemplos
- Todos los contribuidores y estudiantes

---

## 📚 Documentación Adicional

- [🤖 Instrucciones de Copilot](.github/copilot-instructions.md)
- [🤝 Guía de Contribución](CONTRIBUTING.md)
- [📜 Código de Conducta](CODE_OF_CONDUCT.md)
- [🔒 Política de Seguridad](SECURITY.md)
- [🐳 Guía de Docker](_docs/docker-guide.md)

---

<p align="center">
  <strong>🎓 Bootcamp PyTorch Zero to Hero</strong><br>
  <em>De cero a deep learning en 24 semanas</em>
</p>

<p align="center">
  <a href="bootcamp/week-01">Comenzar Semana 1</a> •
  <a href="_docs">Ver Documentación</a> •
  <a href="../../issues">Reportar Issue</a> •
  <a href="CONTRIBUTING.md">Contribuir</a>
</p>

<p align="center">
  Hecho con ❤️ para la comunidad de ML/DL
</p>
