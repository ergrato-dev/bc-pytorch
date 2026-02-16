# 🔄 Workflow de Creación de Contenido

> **Referencia rápida del orden de creación de contenido semanal**

---

## 📋 Orden de Creación

```
┌─────────────────────────────────────────────────┐
│  1️⃣  README.md de la semana      (1h)          │
│      └─ Marco general y objetivos               │
├─────────────────────────────────────────────────┤
│  2️⃣  rubrica-evaluacion.md      (30min)        │
│      └─ Criterios de evaluación claros          │
├─────────────────────────────────────────────────┤
│  3️⃣  1-teoria/                  (2-3h)         │
│      ├─ README.md (índice)                      │
│      ├─ 01-concepto.md                          │
│      ├─ 02-concepto.md                          │
│      └─ notebooks/                              │
├─────────────────────────────────────────────────┤
│  4️⃣  0-assets/                  (30-60min)     │
│      ├─ README.md                               │
│      ├─ 01-diagram.png     ← Vincular con      │
│      └─ 02-diagram.png       teoría            │
├─────────────────────────────────────────────────┤
│  5️⃣  2-practicas/               (2-3h)         │
│      ├─ practica-01/                            │
│      ├─ practica-02/                            │
│      └─ practica-03/                            │
├─────────────────────────────────────────────────┤
│  6️⃣  3-proyecto/                (3-4h)         │
│      ├─ README.md (ultra-detallado)             │
│      ├─ data/                                   │
│      ├─ starter/                                │
│      └─ solution/                               │
├─────────────────────────────────────────────────┤
│  7️⃣  4-recursos/ completos      (1h)           │
│      ├─ README.md                               │
│      ├─ papers/                                 │
│      ├─ videos/                                 │
│      └─ webgrafia/                              │
├─────────────────────────────────────────────────┤
│  8️⃣  5-glosario/                (45min)        │
│      ├─ README.md (definiciones)                │
│      └─ cheat-sheet.md (sintaxis)               │
└─────────────────────────────────────────────────┘

TIEMPO TOTAL: 12-16 horas
```

---

## 🎯 Principios Clave

### 1. **Planifica antes de crear**
README primero → define el marco completo de la semana

### 2. **Establece criterios claros**
Rúbrica temprano → tanto tú como los estudiantes saben qué esperar

### 3. **Contenido antes que forma**
Teoría primero → luego creas los assets que la apoyan

### 4. **De lo simple a lo complejo**
Prácticas → refuerzan conceptos antes del proyecto grande

### 5. **Documenta todo**
Recursos y glosario → apoyo para el aprendizaje continuo

---

## ⚡ Quick Commands

```bash
# Iniciar una nueva semana
cd bootcamp/
mkdir -p week-XX/{0-assets,1-teoria/notebooks,2-practicas,3-proyecto,4-recursos,5-glosario}

# Copiar templates (si existen)
cp templates/README-week-template.md week-XX/README.md
cp templates/rubrica-template.md week-XX/rubrica-evaluacion.md

# Crear estructura de proyecto
cd week-XX/3-proyecto/
mkdir -p data/{raw,processed} starter solution checkpoints results
```

---

## 📚 Documentación Completa

Para guía detallada con templates y ejemplos:

👉 **[_docs/workflow-creacion-semanal.md](_docs/workflow-creacion-semanal.md)**

Incluye:
- ✅ Templates completos de cada archivo
- ✅ Ejemplos de código
- ✅ Checklists de verificación
- ✅ Tips y best practices
- ✅ Basado en [bc-javascript-es2023](https://github.com/ergrato-dev/bc-javascript-es2023)

---

## ✅ Checklist Rápido

Antes de publicar una semana:

- [ ] README con objetivos claros
- [ ] Rúbrica con criterios específicos
- [ ] 3+ archivos de teoría
- [ ] Assets vinculados
- [ ] 3-4 prácticas completas
- [ ] Proyecto con README ultra-detallado
- [ ] Recursos curados (papers, videos, artículos)
- [ ] Glosario y cheat sheet
- [ ] Todo el código ejecuta sin errores
- [ ] Un estudiante puede completar en ~7 horas

---

## 🔗 Ver También

- [Estructura del Bootcamp](_docs/estructura-bootcamp.md)
- [Imágenes Docker Optimizadas](_docs/docker-images-optimized.md)
- [Instrucciones para Copilot](.github/copilot-instructions.md)

---

_Bootcamp PyTorch Zero to Hero_
