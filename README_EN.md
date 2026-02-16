<p align="center">
  <img src="_assets/bootcamp-header.svg" alt="Bootcamp PyTorch Zero to Hero" width="800">
</p>

<p align="center">
  <a href="https://github.com/epti-dev/bc-pytorch/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License MIT"></a>
  <a href="#"><img src="https://img.shields.io/badge/weeks-24-yellow.svg" alt="24 Weeks"></a>
  <a href="#"><img src="https://img.shields.io/badge/hours-168-orange.svg" alt="168 Hours"></a>
  <a href="#"><img src="https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?logo=pytorch" alt="PyTorch 2.0+"></a>
  <a href="#"><img src="https://img.shields.io/badge/Python-3.11+-3776AB?logo=python" alt="Python 3.11+"></a>
  <a href="#"><img src="https://img.shields.io/badge/Docker-Enabled-2496ED?logo=docker" alt="Docker"></a>
  <a href="CONTRIBUTING.md"><img src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square" alt="PRs Welcome"></a>
</p>

<p align="center">
  <a href="README.md"><img src="https://img.shields.io/badge/🇪🇸_Español-DC143C?style=for-the-badge&logoColor=white" alt="Versión en Español"></a>
</p>

---

## 📋 Description

Intensive **24-week (6-month)** bootcamp designed to take students from zero to a competent level in Deep Learning with PyTorch. With a weekly commitment of **7 hours**, you'll learn from Python fundamentals to deploying advanced models in production.

### 🎯 Objectives

Upon completion of the bootcamp, students will be able to:

- ✅ Master modern Python (3.11+) and scientific libraries (NumPy, pandas, matplotlib)
- ✅ Implement neural networks from scratch with PyTorch
- ✅ Design and train CNNs for computer vision
- ✅ Create RNN/LSTM models for sequence processing
- ✅ Apply transfer learning using pre-trained architectures
- ✅ Optimize hyperparameters and improve model performance
- ✅ Deploy models to production using Docker
- ✅ Read and implement research papers in deep learning

### 🐳 Why Docker?

> **Reproducible environments from day 1** - Same environment on any machine, no dependency conflicts.

The entire bootcamp runs in Docker containers, ensuring that every student has exactly the same development environment, regardless of their operating system. Full GPU support via NVIDIA Container Toolkit.

### 🚀 Why PyTorch?

> **The preferred framework in research and production** - Dynamic, pythonic, and with a robust ecosystem.

PyTorch 2.0+ offers the development flexibility you need and the performance that real applications demand. Its intuitive syntax and easy debugging make it ideal for learning deep learning.

---

## 🗓️ Bootcamp Structure

| Stage | Weeks | Hours | Main Topics |
|:-----:|:-----:|:-----:|-------------|
| **Python/NumPy Fundamentals** | 1-6 | 42h | Modern Python, NumPy, visualization, linear algebra |
| **PyTorch Basics** | 7-12 | 42h | Tensors, autograd, nn.Module, optimization |
| **Neural Networks** | 13-18 | 42h | CNNs, RNNs, modern architectures, regularization |
| **Advanced & Deploy** | 19-24 | 42h | Transfer learning, interpretability, production |

**Total: 24 weeks** | **168 hours** of intensive practical training

---

## 📚 Weekly Content

Each week includes:

```
bootcamp/week-XX/
├── README.md                 # Description and objectives
├── rubrica-evaluacion.md     # Evaluation criteria
├── Dockerfile                # Custom Docker image
├── docker-compose.yml        # Service configuration
├── requirements.txt          # Python dependencies
├── 0-assets/                 # Images and diagrams
├── 1-teoria/                 # Theoretical material
│   ├── *.md                  # Conceptual explanations
│   └── notebooks/            # Interactive notebooks
├── 2-practicas/              # Guided exercises
│   ├── practica-01-name/
│   │   ├── README.md
│   │   ├── starter/          # Initial code
│   │   └── solution/         # Reference solution
│   └── practica-02-name/
├── 3-proyecto/               # 🎯 ONLY DELIVERABLE
│   ├── README.md
│   ├── starter/
│   │   └── notebook.ipynb
│   └── solution/
│       └── notebook.ipynb
├── 4-recursos/               # Complementary material
│   ├── papers/               # Relevant papers
│   ├── videos/               # Video links
│   └── webgrafia/            # Articles and tutorials
└── 5-glosario/               # Terms and reference
    ├── README.md             # Concept glossary
    └── cheat-sheet.md        # Quick reference
```

### 🔑 Key Components

- 📖 **Theory**: Fundamental concepts with executable interactive notebooks
- 💻 **Practice**: Progressive exercises with real datasets
- 📝 **Assessment**: Evidence of knowledge, performance, and product
- 🐳 **Docker**: Fully containerized environment with Jupyter Lab
- 🎓 **Resources**: Papers, glossaries, cheat sheets, and complementary material

---

## 🛠️ Tech Stack

| Technology | Version | Use |
|------------|---------|-----|
| Python | 3.11+ | Main language |
| PyTorch | 2.0+ | Deep learning framework |
| NumPy | 1.24+ | Scientific computing |
| pandas | 2.0+ | Data analysis |
| matplotlib | 3.7+ | Visualization |
| Jupyter Lab | 4.0+ | Interactive development |
| Docker | 24+ | Containerization |
| CUDA | 11.7+ | GPU acceleration (optional) |
| Git | 2.30+ | Version control |

**Docker base image**: `pytorch/pytorch:2.0.0-cuda11.7-cudnn8-runtime`

---

## 🚀 Quick Start

### Prerequisites

- **Docker** 24+ with Docker Compose
- **Git** for version control
- **NVIDIA Docker** (optional, for GPU)
- **VS Code** (recommended) with included extensions
- **8GB RAM minimum** (16GB recommended)

### 1. Clone the Repository

```bash
git clone https://github.com/epti-dev/bc-pytorch.git
cd bc-pytorch
```

### 2. Install VS Code Extensions

```bash
# Open in VS Code
code .

# Recommended extensions will appear automatically
# Or run: Ctrl+Shift+P → "Extensions: Show Recommended Extensions"
```

### 3. Start Week-01 with Docker

```bash
cd bootcamp/week-01

# Build Docker image
docker-compose build

# Start Jupyter Lab
docker-compose up
```

### 4. Access Jupyter Lab

Open your browser at `http://localhost:8888` with token `bootcamp`

### 5. Follow Instructions

Each week contains a `README.md` with objectives, theory, and detailed project.

---

## 📊 Learning Methodology

### Teaching Strategies

- 🎯 **Learning by Doing**: Each concept is learned by implementing it
- 🧩 **Gradual Progression**: From simple to complex, no abrupt jumps
- 🏗️ **Real Projects**: Use cases with real-world datasets
- 📊 **Visualization**: Graphics and diagrams for complex concepts
- 🔬 **Experimentation**: Interactive notebooks for exploration

### Time Distribution (7h/week)

- **Theory**: 2 hours (interactive notebooks)
- **Practice**: 2-2.5 hours (guided exercises)
- **Project**: 2.5-3 hours (**only deliverable**)

### Assessment

Each week includes three types of evidence:

1. **Knowledge 🧠** (30%): Understanding of fundamental concepts
2. **Performance 💪** (40%): Functional, organized, and documented code
3. **Product 📦** (30%): Completed weekly project

**Passing criteria**: Minimum 70% in each type of evidence

---

## 🐳 Working with Docker

### Basic Commands

```bash
# Build image for a week
cd bootcamp/week-XX
docker-compose build

# Start services
docker-compose up

# Start in background
docker-compose up -d

# View logs
docker-compose logs -f

# Access container
docker-compose exec jupyter bash

# Stop services
docker-compose down
```

### Using GPU (NVIDIA)

Uncomment the `deploy` section in `docker-compose.yml`:

```yaml
deploy:
  resources:
    reservations:
      devices:
        - driver: nvidia
          count: all
          capabilities: [gpu]
```

### Verify GPU in PyTorch

```python
import torch
print(f"CUDA available: {torch.cuda.is_available()}")
print(f"GPU: {torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'N/A'}")
```

---

## 🤝 Contributing

Contributions are welcome! This is an open-source educational project.

### How to Contribute

1. Read the [Contributing Guide](CONTRIBUTING.md)
2. Review the [Code of Conduct](CODE_OF_CONDUCT.md)
3. Fork the repository
4. Create your branch (`git checkout -b feature/new-practice`)
5. Commit with [Conventional Commits](https://www.conventionalcommits.org/) (`git commit -m 'feat: add CNN visualization exercise'`)
6. Push to the branch (`git push origin feature/new-practice`)
7. Open a Pull Request

### 📋 Contribution Areas

- ✨ Additional exercises with new datasets
- 📚 Documentation and tutorial improvements
- 🐛 Code or notebook bug fixes
- 🎨 Visual resources (architecture diagrams)
- 🌐 Translations to other languages
- 📹 Explanatory video tutorials
- 🐳 Optimizations in Docker configurations

---

## 📞 Support

- 💬 Discussions: [GitHub Discussions](https://github.com/epti-dev/bc-pytorch/discussions)
- 🐛 Issues: [GitHub Issues](https://github.com/epti-dev/bc-pytorch/issues)
- 📧 Email: [bootcamp-pytorch@epti.dev](mailto:bootcamp-pytorch@epti.dev)

---

## 📄 License

This project is under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🏆 Acknowledgments

- [PyTorch Team](https://pytorch.org/) - For the best deep learning framework
- [Fast.ai](https://www.fast.ai/) - For democratizing deep learning
- [Papers with Code](https://paperswithcode.com/) - For connecting research with implementation
- [Kaggle](https://www.kaggle.com/) - For datasets and educational competitions
- ML/DL Community - For resources, papers, and examples
- All contributors and students

---

## 📚 Additional Documentation

- [🤖 Copilot Instructions](.github/copilot-instructions.md)
- [🤝 Contributing Guide](CONTRIBUTING.md)
- [📜 Code of Conduct](CODE_OF_CONDUCT.md)
- [🔒 Security Policy](SECURITY.md)
- [🐳 Docker Guide](_docs/docker-guide.md)

---

<p align="center">
  <strong>🎓 Bootcamp PyTorch Zero to Hero</strong><br>
  <em>From zero to deep learning in 24 weeks</em>
</p>

<p align="center">
  <a href="bootcamp/week-01">Start Week 1</a> •
  <a href="_docs">View Documentation</a> •
  <a href="../../issues">Report Issue</a> •
  <a href="CONTRIBUTING.md">Contribute</a>
</p>

<p align="center">
  Made with ❤️ for the ML/DL community
</p>
