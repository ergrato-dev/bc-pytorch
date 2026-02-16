# 🎨 Assets del Bootcamp PyTorch

Este directorio contiene los recursos visuales y multimedia del bootcamp.

---

## 📁 Contenido

### Banners

#### `bootcamp-header.svg`
- **Tipo**: Banner principal para README
- **Dimensiones**: 1200x300px
- **Formato**: SVG (escalable)
- **Colores**: 
  - Background: `#1a1a2e` (dark blue)
  - Accent: `#EE4C2C` (PyTorch orange)
  - Text: `#ffffff` (white), `#a8a8a8` (gray)
- **Tipografía**: Arial, Helvetica, sans-serif
- **Uso**: Encabezado de README.md y README_EN.md

**Características del diseño:**
- ✅ Tema dark sin degradados
- ✅ Fuentes sin serifas
- ✅ Iconografía inspirada en PyTorch (llama)
- ✅ Pills tecnológicos (Python 3.11+, PyTorch 2.0+, Docker, 168 hrs)
- ✅ Acentos decorativos en esquinas
- ✅ Diseño minimalista y profesional

---

## 🎨 Guía de Estilo Visual

### Paleta de Colores

```css
/* Colores principales */
--dark-bg: #1a1a2e;           /* Background oscuro */
--dark-secondary: #16213e;     /* Elementos secundarios */
--pytorch-orange: #EE4C2C;     /* Acento principal (PyTorch) */
--text-primary: #ffffff;       /* Texto principal */
--text-secondary: #a8a8a8;     /* Texto secundario */
```

### Tipografía

- **Títulos**: Arial, Helvetica, sans-serif - Bold (700)
- **Subtítulos**: Arial, Helvetica, sans-serif - Light (300)
- **Cuerpo**: Arial, Helvetica, sans-serif - Regular (400)

### Iconografía

- Estilo minimalista y geométrico
- Líneas de 2-3px de grosor
- Colores sólidos sin degradados
- Inspiración: Logo de PyTorch (llama)

---

## 📝 Cómo Usar

### En Markdown

```markdown
<!-- Banner principal -->
![Bootcamp PyTorch Zero to Hero](_assets/bootcamp-header.svg)

<!-- Con control de tamaño -->
<p align="center">
  <img src="_assets/bootcamp-header.svg" alt="Bootcamp PyTorch" width="800">
</p>
```

### En HTML

```html
<!-- Responsive -->
<img src="_assets/bootcamp-header.svg" 
     alt="Bootcamp PyTorch Zero to Hero" 
     style="max-width: 100%; height: auto;">
```

---

## 🔧 Edición

### Editar SVG

El archivo SVG es código XML plano y puede editarse con:
- **Editores de texto**: VS Code, Sublime Text
- **Editores visuales**: Inkscape, Figma, Adobe Illustrator
- **Online**: Boxy SVG, Vectr

### Exportar a PNG

```bash
# Usando Inkscape (CLI)
inkscape --export-type=png \
         --export-width=1200 \
         --export-height=300 \
         _assets/bootcamp-header.svg \
         -o _assets/bootcamp-header.png

# Usando ImageMagick
convert -density 300 \
        -background none \
        _assets/bootcamp-header.svg \
        _assets/bootcamp-header.png
```

---

## 📚 Próximos Assets

### Pendientes de crear:

- [ ] **Diagramas de arquitectura**
  - CNN architecture diagram
  - RNN/LSTM flow diagram
  - Training pipeline diagram
  
- [ ] **Infografías**
  - Roadmap visual de 24 semanas
  - Comparativa PyTorch vs TensorFlow
  - GPU vs CPU performance
  
- [ ] **Icons**
  - Folder icons por sección (teoría, práctica, proyecto)
  - Icons para tipos de ejercicios
  - Status badges personalizados

- [ ] **Social Media**
  - Banner para LinkedIn (1200x627)
  - Banner para Twitter (1500x500)
  - Thumbnail para YouTube (1280x720)

---

## 📐 Especificaciones Técnicas

### Banner Header

| Propiedad | Valor |
|:----------|:------|
| Ancho | 1200px |
| Alto | 300px |
| Ratio | 4:1 |
| Formato | SVG |
| Tamaño archivo | ~3.7KB |
| Compatibilidad | Todos los navegadores modernos |

### Convenciones de Nombres

```
nombre-descriptivo.extension
├── bootcamp-header.svg      ✅ Correcto
├── architecture-cnn.svg     ✅ Correcto
├── Banner_Final.svg         ❌ Incorrecto (capitalización)
└── img001.svg               ❌ Incorrecto (no descriptivo)
```

---

## 🎯 Guidelines de Diseño

### ✅ Hacer

- Usar colores de la paleta oficial
- Mantener consistencia tipográfica
- Diseñar pensando en dark mode
- Optimizar tamaño de archivos
- Usar formato SVG cuando sea posible
- Nombres descriptivos en kebab-case

### ❌ Evitar

- Degradados (no requeridos)
- Fuentes con serifas
- Colores fuera de la paleta
- Archivos no optimizados
- Imágenes rasterizadas para logos/iconos
- Diseños demasiado complejos

---

## 📜 Licencia

Los assets de este proyecto están bajo la misma licencia que el proyecto principal (MIT License). Ver [LICENSE](../LICENSE) para más detalles.

---

## 🤝 Contribuir

Para contribuir nuevos assets:

1. **Seguir la guía de estilo** definida arriba
2. **Optimizar archivos** antes de commit
3. **Documentar en este README** el nuevo asset
4. **Usar nombres descriptivos** en kebab-case
5. **Incluir múltiples formatos** si es necesario (SVG + PNG)

Ver [CONTRIBUTING.md](../CONTRIBUTING.md) para más información.

---

_Assets del Bootcamp PyTorch Zero to Hero | Febrero 2026_
