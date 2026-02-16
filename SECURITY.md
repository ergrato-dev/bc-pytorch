# Política de Seguridad

## 🔒 Versiones Soportadas

Este proyecto educativo está en desarrollo activo. Mantenemos las siguientes versiones:

| Versión | Soportada          |
| ------- | ------------------ |
| main    | :white_check_mark: |
| develop | :white_check_mark: |
| < 1.0   | :x:                |

---

## 🐛 Reportar una Vulnerabilidad

La seguridad de nuestros estudiantes y contribuidores es nuestra prioridad. Si descubres una vulnerabilidad de seguridad en el bootcamp, por favor repórtala de manera responsable.

### ¿Qué es una Vulnerabilidad de Seguridad?

En el contexto de este bootcamp educativo de ML/DL, consideramos vulnerabilidades:

#### 🚨 Críticas

- Exposición de credenciales o API keys en código o notebooks
- Malware o código malicioso en datasets descargables
- Dockerfiles con configuraciones inseguras que expongan el sistema host
- Inyección de código en notebooks que pueda ejecutarse en el contenedor
- Modelos pre-entrenados de fuentes no confiables con código embebido malicioso
- Enlaces a datasets o recursos comprometidos
- Dependencias de PyTorch/Python con vulnerabilidades conocidas críticas

#### ⚠️ Moderadas

- Prácticas de código inseguras en ejemplos (path traversal, ejecución arbitraria)
- Falta de validación de inputs en notebooks de ejemplo
- Uso de URLs no HTTPS para descargar datasets
- Almacenamiento inseguro de checkpoints o modelos
- Configuraciones Docker que expongan puertos innecesariamente
- Pickle de modelos sin verificación (riesgo de ejecución de código)

#### ℹ️ Informativas

- Mejoras en la enseñanza de seguridad en ML
- Sugerencias de mejores prácticas
- Actualizaciones de documentación de seguridad
- Recomendaciones para manejo seguro de datasets sensibles

---

## 📧 Cómo Reportar

### Opción 1: Email Privado (Preferido para vulnerabilidades críticas)

Envía un email a: **[security@epti.dev](mailto:security@epti.dev)**

**Incluye:**
- Descripción de la vulnerabilidad
- Pasos para reproducirla (incluyendo Docker, notebooks, datasets)
- Impacto potencial (ej: ejecución de código, exposición de datos)
- Ubicación en el código (archivo, línea, semana)
- Tu sugerencia de solución (opcional)
- Versión de PyTorch, Python, Docker afectada

### Opción 2: GitHub Security Advisory (Para vulnerabilidades moderadas)

1. Ve a la pestaña "Security" del repositorio
2. Click en "Report a vulnerability"
3. Completa el formulario con detalles técnicos

### Opción 3: Issue Privado

Para problemas de seguridad menores:
- Crea un issue con la etiqueta `security`
- **NO incluyas detalles sensibles** en el título
- Menciona `@mantenedores` para atención inmediata

---

## ⏱️ Tiempo de Respuesta

| Severidad | Tiempo de Respuesta | Tiempo de Resolución |
| --------- | ------------------- | -------------------- |
| Crítica   | 24 horas            | 48-72 horas          |
| Moderada  | 48 horas            | 1-2 semanas          |
| Baja      | 1 semana            | Próximo release      |

---

## 🔄 Proceso de Manejo

1. **Acuse de Recibo**
   - Confirmaremos la recepción en el tiempo establecido
   - Asignaremos un identificador de seguimiento

2. **Evaluación**
   - Verificaremos y reproduciremos la vulnerabilidad
   - Evaluaremos el impacto y severidad

3. **Desarrollo de Fix**
   - Crearemos un fix en una rama privada
   - Probaremos la solución en Docker/notebooks

4. **Divulgación**
   - Coordinaremos la divulgación contigo
   - Publicaremos un Security Advisory
   - Actualizaremos el código y Dockerfiles

5. **Reconocimiento**
   - Te acreditaremos en el CHANGELOG (si lo deseas)
   - Incluiremos tu nombre en el Security Advisory

---

## 🏆 Programa de Reconocimiento

Aunque este es un proyecto educativo sin recompensas monetarias, reconocemos públicamente a quienes reportan vulnerabilidades:

### Hall of Fame

Los contribuidores de seguridad serán listados en:
- `SECURITY_HALL_OF_FAME.md`
- Release notes
- README principal

### Niveles de Reconocimiento

- 🥇 **Gold**: Vulnerabilidades críticas (código malicioso, exposición de datos)
- 🥈 **Silver**: Vulnerabilidades moderadas (configuraciones inseguras)
- 🥉 **Bronze**: Vulnerabilidades menores o mejoras de seguridad

---

## 🛡️ Mejores Prácticas de Seguridad para Estudiantes

### Al Trabajar con el Bootcamp

1. **Variables de Entorno**
   ```python
   # ❌ NUNCA hagas esto
   KAGGLE_KEY = 'mi-clave-secreta-123'
   
   # ✅ Usa variables de entorno
   import os
   KAGGLE_KEY = os.getenv('KAGGLE_KEY')
   ```

2. **No Commitear Secretos**
   - Usa `.env` para API keys (Kaggle, HuggingFace, etc.)
   - Verifica que `.gitignore` incluya `.env`, `*.pth`, `*.pt`
   - Proporciona `.env.example` sin valores reales

3. **Descarga Segura de Datasets**
   ```python
   # ❌ HTTP inseguro
   url = 'http://example.com/dataset.zip'
   
   # ✅ HTTPS siempre
   url = 'https://example.com/dataset.zip'
   
   # ✅ Verifica checksums
   import hashlib
   assert hashlib.sha256(data).hexdigest() == expected_hash
   ```

4. **Carga Segura de Modelos**
   ```python
   # ❌ Pickle sin verificación (riesgo de ejecución de código)
   import pickle
   model = pickle.load(open('model.pkl', 'rb'))
   
   # ✅ Usa torch.load con weights_only (PyTorch 2.0+)
   import torch
   model = torch.load('model.pth', weights_only=True)
   
   # ✅ O usa safetensors
   from safetensors.torch import load_model
   load_model(model, 'model.safetensors')
   ```

5. **Docker: No Ejecutar como Root**
   ```dockerfile
   # ✅ Crear usuario no privilegiado
   RUN useradd -m -u 1000 bootcamp
   USER bootcamp
   ```

6. **Validación de Inputs**
   ```python
   # ✅ Valida paths antes de cargar
   import os
   from pathlib import Path
   
   def load_image(file_path: str):
       path = Path(file_path).resolve()
       if not path.is_file() or path.suffix not in ['.jpg', '.png']:
           raise ValueError("Invalid image file")
       return Image.open(path)
   ```

7. **Manejo Seguro de Datasets Sensibles**
   - No compartas datasets con información personal sin anonimizar
   - Usa differential privacy cuando sea apropiado
   - Verifica licencias de datasets antes de usar

---

## 📚 Recursos de Seguridad

### Para Aprender

- [OWASP Machine Learning Security](https://owasp.org/www-project-machine-learning-security-top-10/)
- [PyTorch Security Best Practices](https://pytorch.org/docs/stable/notes/security.html)
- [Docker Security](https://docs.docker.com/engine/security/)
- [ML Model Security](https://arxiv.org/abs/2005.12183) (Paper)

### Herramientas

- [pip-audit](https://github.com/pypa/pip-audit) - Auditar dependencias Python
- [Safety](https://pyup.io/safety/) - Escaneo de vulnerabilidades en paquetes
- [Bandit](https://github.com/PyCQA/bandit) - Security linter para Python
- [Trivy](https://github.com/aquasecurity/trivy) - Escaneo de imágenes Docker

---

## 🔐 Dependencias

Mantenemos actualizadas las dependencias del proyecto:

```bash
# Auditar dependencias
pip-audit

# En Dockerfile, siempre especifica versiones
RUN pip install torch==2.0.0 torchvision==0.15.0

# Actualizar requirements.txt regularmente
pip list --outdated
```

**Frecuencia de Revisión**: Mensual o cuando se descubra una vulnerabilidad crítica

---

## ⚖️ Divulgación Responsable

Solicitamos:

- **No divulgar públicamente** la vulnerabilidad hasta que hayamos publicado un fix
- **Dar tiempo razonable** para resolver el problema (48-72h para críticas)
- **No explotar** la vulnerabilidad más allá de lo necesario para demostrarla
- **No acceder** a datos de otros usuarios o sistemas

Nos comprometemos a:

- **Responder rápidamente** a tu reporte
- **Mantener comunicación** sobre el progreso
- **Acreditar tu descubrimiento** (si lo deseas)
- **Publicar un fix** en el tiempo acordado
- **Documentar** la vulnerabilidad y solución para educar a la comunidad

---

## 📞 Contacto de Seguridad

- **Email Principal**: [security@epti.dev](mailto:security@epti.dev)
- **Email Alternativo**: [bootcamp-pytorch@epti.dev](mailto:bootcamp-pytorch@epti.dev)
- **Respuesta esperada**: 24-48 horas

---

## 📋 Checklist para Reportar

Antes de enviar tu reporte, asegúrate de incluir:

- [ ] Descripción clara de la vulnerabilidad
- [ ] Pasos detallados para reproducirla
- [ ] Impacto potencial (qué podría comprometerse)
- [ ] Versión afectada (PyTorch, Python, Docker, semana)
- [ ] Archivos/líneas específicas o Dockerfiles
- [ ] Captura de pantalla o log de error (si aplica)
- [ ] Sugerencia de fix (opcional pero apreciado)
- [ ] Tu información de contacto para seguimiento

---

## 🙏 Agradecimientos

Agradecemos a todos los investigadores de seguridad y contribuidores que nos ayudan a mantener este proyecto seguro para nuestra comunidad de estudiantes de ML/DL.

---

*Última actualización: Febrero 2026*
*Versión: 1.0*

**Para consultas urgentes de seguridad, contacta: [security@epti.dev](mailto:security@epti.dev)**
