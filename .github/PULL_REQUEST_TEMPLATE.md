# Pull Request

## 📋 Descripción

<!-- Descripción clara de los cambios realizados -->

## 🎯 Tipo de Cambio

<!-- Marca las que apliquen -->

- [ ] 🐛 Bug fix (cambio no breaking que corrige un issue)
- [ ] ✨ Nueva característica (cambio no breaking que agrega funcionalidad)
- [ ] 💥 Breaking change (fix o feature que causaría que funcionalidad existente no funcione como esperado)
- [ ] 📚 Documentación (cambios solo en documentación)
- [ ] 🎨 Estilo (formateo, punto y coma faltantes, etc; sin cambios de código)
- [ ] ♻️ Refactorización (ni fix ni feature, mejora de código)
- [ ] ⚡ Performance (mejora de rendimiento)
- [ ] ✅ Tests (agregar tests faltantes o corregir existentes)
- [ ] 🐳 Docker (cambios en Dockerfiles o configuraciones)
- [ ] 🔧 Chore (cambios en el proceso de build, herramientas auxiliares, etc.)

## 📍 Ubicación de Cambios

<!-- Marca las áreas afectadas -->

- [ ] week-01 hasta week-06 (Fundamentos Python/NumPy)
- [ ] week-07 hasta week-12 (PyTorch Básico)
- [ ] week-13 hasta week-18 (Redes Neuronales)
- [ ] week-19 hasta week-24 (Avanzado y Deploy)
- [ ] Documentación raíz
- [ ] Configuraciones Docker
- [ ] Scripts y herramientas

## 🔗 Issues Relacionados

<!-- Referencia a issues que este PR cierra o aborda -->

Closes #(issue)
Fixes #(issue)
Addresses #(issue)

## 📝 Cambios Realizados

<!-- Lista detallada de cambios -->

- Cambio 1
- Cambio 2
- Cambio 3

## 🧪 Cómo se ha Probado

<!-- Describe las pruebas realizadas -->

- [ ] Probado en Docker (CPU)
- [ ] Probado en Docker (GPU)
- [ ] Todos los notebooks ejecutan sin errores
- [ ] Tests pasan (si aplica)
- [ ] Ejecutado en diferentes sistemas operativos

**Detalles de prueba:**

```bash
# Comandos ejecutados para probar
cd bootcamp/week-XX
docker-compose build
docker-compose up
# ... probado notebook X, Y, Z
```

**Resultado esperado:** (describe qué debería pasar)

**Resultado obtenido:** (confirma que funcionó)

## 📸 Screenshots (si aplica)

<!-- Si hay cambios visuales, agrega screenshots -->

**Antes:**
<!-- Screenshot before -->

**Después:**
<!-- Screenshot after -->

## ✅ Checklist

<!-- Marca las casillas completadas -->

### Código

- [ ] Mi código sigue el estilo del proyecto (PEP 8, type hints)
- [ ] He agregado docstrings a funciones/clases nuevas
- [ ] He comentado mi código, especialmente en partes complejas
- [ ] Los comentarios educativos están en español
- [ ] Los nombres de variables/funciones están en inglés

### Notebooks (si aplica)

- [ ] Los notebooks ejecutan de inicio a fin sin errores
- [ ] He limpiado los outputs innecesarios
- [ ] Las visualizaciones tienen títulos y etiquetas en español
- [ ] He incluido explicaciones en celdas markdown

### Docker (si aplica)

- [ ] El Dockerfile construye sin errores
- [ ] He optimizado las capas de Docker
- [ ] He probado que el contenedor inicia correctamente
- [ ] requirements.txt está actualizado

### Documentación

- [ ] He actualizado la documentación relacionada
- [ ] He actualizado el README si es necesario
- [ ] Los enlaces funcionan correctamente

### Tests

- [ ] He agregado tests que prueban mi funcionalidad (si aplica)
- [ ] Todos los tests existentes pasan

## 🎓 Beneficio Educativo

<!-- ¿Cómo beneficia este cambio a los estudiantes? -->

Este cambio ayuda a los estudiantes a:
- ...
- ...

## 📚 Referencias

<!-- Papers, tutoriales, documentación consultada -->

- [Título](URL)
- [Título](URL)

## 📝 Notas Adicionales

<!-- Cualquier información adicional para los revisores -->

## 👀 Áreas de Enfoque para Revisión

<!-- ¿En qué áreas específicas quieres feedback? -->

- [ ] Corrección técnica del contenido
- [ ] Claridad de las explicaciones
- [ ] Calidad del código
- [ ] Configuración Docker
- [ ] Otro: _______

---

**Para los Mantenedores:**

- [ ] El contenido se alinea con el nivel del bootcamp
- [ ] La implementación sigue las mejores prácticas de PyTorch
- [ ] La documentación es clara y educativa
- [ ] El código es reproducible en Docker
