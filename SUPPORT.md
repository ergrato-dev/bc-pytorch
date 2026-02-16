# Soporte / Support

¿Necesitas ayuda con el Bootcamp PyTorch Zero to Hero? Estamos aquí para ayudarte! 🚀

## 📋 Antes de Preguntar

Antes de buscar ayuda, por favor:

1. **Lee la documentación** del tema en cuestión
2. **Revisa los issues existentes** - tal vez alguien ya preguntó lo mismo
3. **Consulta el glosario** de la semana correspondiente
4. **Revisa el cheat-sheet** para referencia rápida de sintaxis
5. **Intenta reproducir** el problema en un entorno limpio (nuevo contenedor Docker)

## 💬 Canales de Soporte

### GitHub Discussions (Recomendado)

Para preguntas generales, discusiones y ayuda con conceptos:

👉 [GitHub Discussions](https://github.com/epti-dev/bc-pytorch/discussions)

**Categorías:**
- **Q&A**: Preguntas y respuestas sobre PyTorch, conceptos de ML/DL
- **Show and Tell**: Comparte tus proyectos y experimentos
- **Ideas**: Sugerencias para mejorar el bootcamp
- **General**: Discusiones generales sobre el bootcamp

**Ventajas:**
- ✅ Respuestas visibles para toda la comunidad
- ✅ Otros pueden beneficiarse de la pregunta
- ✅ Participación de la comunidad

### GitHub Issues

Para reportar bugs o solicitar características específicas:

👉 [GitHub Issues](https://github.com/epti-dev/bc-pytorch/issues)

**Usa Issues para:**
- 🐛 Reportar errores en código o notebooks
- ✨ Solicitar nuevas características
- 📚 Mejorar documentación
- 🐳 Problemas con Docker

**No uses Issues para:**
- ❌ Preguntas generales (usa Discussions)
- ❌ Ayuda con ejercicios (usa Discussions)
- ❌ Dudas sobre conceptos (usa Discussions)

### Email

Para consultas privadas o asuntos sensibles:

📧 [bootcamp-pytorch@epti.dev](mailto:bootcamp-pytorch@epti.dev)

**Usa Email para:**
- Reportar vulnerabilidades de seguridad (o usa Security Advisory)
- Asuntos privados o sensibles
- Colaboraciones institucionales

**Tiempo de respuesta:** 2-3 días hábiles

## 🆘 Tipos de Ayuda

### 1. Problemas con Docker

**Antes de preguntar:**
```bash
# Verificar versión de Docker
docker --version
docker-compose --version

# Ver logs del contenedor
docker-compose logs

# Reconstruir imagen limpia
docker-compose down -v
docker-compose build --no-cache
docker-compose up
```

**Incluye en tu pregunta:**
- Sistema operativo y versión
- Versión de Docker
- El comando exacto que ejecutaste
- El error completo con logs

### 2. Errores en Notebooks

**Antes de preguntar:**
- Reinicia el kernel del notebook
- Ejecuta las celdas en orden desde el inicio
- Verifica que todas las dependencias estén instaladas

**Incluye en tu pregunta:**
- Semana y notebook específico
- Celda donde ocurre el error
- El error completo (traceback)
- Versión de PyTorch: `torch.__version__`

### 3. Conceptos de ML/DL

Para preguntas conceptuales:

**Buenos ejemplos:**
- "¿Por qué usamos ReLU en lugar de sigmoid en capas ocultas?"
- "¿Cuándo usar BatchNorm vs LayerNorm?"
- "¿Cómo funciona backpropagation a través de una capa convolucional?"

**Incluye:**
- Qué ya intentaste entender
- Qué material consultaste
- Dónde específicamente te confundes

### 4. Problemas con GPU/CUDA

**Antes de preguntar:**
```bash
# Verificar CUDA en el sistema
nvidia-smi

# Verificar CUDA en PyTorch
python -c "import torch; print(torch.cuda.is_available())"
python -c "import torch; print(torch.cuda.get_device_name(0))"
```

**Incluye en tu pregunta:**
- Modelo de GPU
- Versión de driver NVIDIA
- Versión de CUDA
- Si el código funciona en CPU

### 5. Proyectos y Ejercicios

Para ayuda con proyectos semanales:

**Qué puedes preguntar:**
- ✅ Conceptos que no entiendes
- ✅ Por qué tu enfoque no funciona
- ✅ Comparación entre diferentes técnicas
- ✅ Interpretación de resultados

**Qué NO debes pedir:**
- ❌ La solución completa
- ❌ Que alguien haga tu proyecto
- ❌ Código sin esfuerzo previo

**Comparte:**
- Tu código actual
- Qué has intentado
- Qué error obtienes (si aplica)
- Tu razonamiento

## 📚 Recursos de Auto-Ayuda

### Documentación Oficial

- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [PyTorch Tutorials](https://pytorch.org/tutorials/)
- [Python Documentation](https://docs.python.org/3/)

### Comunidades de ML/DL

- [PyTorch Forums](https://discuss.pytorch.org/)
- [r/MachineLearning](https://www.reddit.com/r/MachineLearning/)
- [r/learnmachinelearning](https://www.reddit.com/r/learnmachinelearning/)
- [Stack Overflow - PyTorch Tag](https://stackoverflow.com/questions/tagged/pytorch)

### Debugging Tips

1. **Lee el error completo** - El traceback te dice dónde está el problema
2. **Imprime shapes** - Muchos errores vienen de shapes incorrectos
   ```python
   print(f"Input shape: {x.shape}")
   print(f"Weight shape: {model.weight.shape}")
   ```
3. **Usa un debugger** - VS Code tiene excelente soporte para Python
4. **Simplifica** - Crea un ejemplo mínimo que reproduzca el error
5. **Google el error** - Probablemente alguien ya tuvo ese error

## ⚠️ No Recibirás Soporte Para

- Versiones no soportadas de PyTorch, Python o Docker
- Modificaciones no documentadas del código base
- Entornos que no siguen la configuración Docker del bootcamp
- Proyectos personales no relacionados con el bootcamp
- Solicitudes para hacer tu tarea completa

## 🤝 Contribuir al Soporte

¿Quieres ayudar a otros?

- 👀 Revisa [GitHub Discussions](https://github.com/epti-dev/bc-pytorch/discussions) y responde preguntas
- 🐛 Ayuda a reproducir bugs reportados en Issues
- 📚 Mejora la documentación cuando encuentres algo confuso
- ✨ Comparte tus soluciones creativas en Show and Tell

## 📞 Información de Contacto

- **Discussions**: https://github.com/epti-dev/bc-pytorch/discussions
- **Issues**: https://github.com/epti-dev/bc-pytorch/issues
- **Email**: bootcamp-pytorch@epti.dev
- **Security**: security@epti.dev

---

**Recuerda**: Todos estamos aprendiendo. No hay preguntas tontas. Sé respetuoso y paciente. 💙

*Última actualización: Febrero 2026*
