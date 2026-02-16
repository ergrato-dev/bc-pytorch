# 🚀 Proyecto Semana 01: Calculadora Interactiva

> **🎯 ÚNICO ENTREGABLE OBLIGATORIO**: Este proyecto es el único entregable para aprobar la semana.

---

## 📋 Tabla de Contenidos

- [Objetivos](#-objetivos)
- [Descripción](#-descripción)
- [Requisitos](#-requisitos)
- [Instrucciones](#-instrucciones)
- [Evaluación](#-evaluación)
- [Entrega](#-entrega)
- [Tips](#-tips)

---

## 🎯 Objetivos

Al completar este proyecto serás capaz de:

1. **Aplicar variables y tipos de datos** para almacenar información
2. **Usar operadores aritméticos** para cálculos
3. **Implementar estructuras de control** (if/elif/else, while)
4. **Crear funciones** para organizar el código
5. **Manejar entrada/salida** del usuario
6. **Validar datos** y manejar errores básicos

---

## 📄 Descripción

Crearás una **calculadora interactiva** que funcione en la terminal, permitiendo al usuario realizar operaciones matemáticas mediante un menú.

### Problema a Resolver

Los usuarios necesitan una herramienta simple para realizar cálculos matemáticos sin salir de la terminal. Tu calculadora debe ser intuitiva, robusta y fácil de usar.

### Solución Propuesta

Una aplicación de consola con:
- Menú de opciones claro
- Operaciones matemáticas básicas y avanzadas
- Manejo de errores (división por cero, entradas inválidas)
- Opción de hacer múltiples cálculos
- Historial opcional

---

## ✅ Requisitos

### Obligatorios (70 puntos)

#### R1: Operaciones Básicas (20 pts)

Implementar las 4 operaciones fundamentales:

```python
def sumar(a, b):
    """Retorna la suma de a y b"""
    return a + b

def restar(a, b):
    """Retorna a - b"""
    return a - b

def multiplicar(a, b):
    """Retorna a * b"""
    return a * b

def dividir(a, b):
    """Retorna a / b, maneja división por cero"""
    if b == 0:
        return "Error: No se puede dividir por cero"
    return a / b
```

**Criterios**:
- [ ] Función `sumar()` correcta
- [ ] Función `restar()` correcta
- [ ] Función `multiplicar()` correcta
- [ ] Función `dividir()` con validación de cero
- [ ] Todas retornan valores correctos

#### R2: Menú Interactivo (15 pts)

Mostrar opciones al usuario:

```
================================
   CALCULADORA INTERACTIVA
================================
1. Sumar
2. Restar
3. Multiplicar
4. Dividir
5. Salir
================================
Elige una opción (1-5):
```

**Criterios**:
- [ ] Menú claro y bien formateado
- [ ] Muestra todas las opciones
- [ ] Solicita elección del usuario
- [ ] Diseño visual atractivo

#### R3: Bucle Principal (15 pts)

Permite múltiples operaciones sin reiniciar:

```python
def main():
    while True:
        mostrar_menu()
        opcion = input("Elige opción: ")
        
        if opcion == '5':
            print("¡Hasta luego!")
            break
        
        # Procesar operación
        # ...
```

**Criterios**:
- [ ] Bucle permite múltiples operaciones
- [ ] Opción de salir funciona correctamente
- [ ] No termina abruptamente
- [ ] Flujo lógico claro

#### R4: Captura de Entrada (10 pts)

Solicitar números al usuario:

```python
try:
    num1 = float(input("Primer número: "))
    num2 = float(input("Segundo número: "))
except ValueError:
    print("Error: Ingresa un número válido")
```

**Criterios**:
- [ ] Solicita dos números
- [ ] Maneja entradas no numéricas
- [ ] Mensajes claros al usuario
- [ ] Usa `try/except` para validación

#### R5: Manejo de Errores (10 pts)

Robusto ante errores comunes:

**Criterios**:
- [ ] Maneja división por cero
- [ ] Valida opciones del menú
- [ ] Captura entradas inválidas
- [ ] Mensajes de error informativos
- [ ] Programa no crashea

### Opcionales (30 puntos) 🌟

#### O1: Operaciones Avanzadas (10 pts)

```python
def potencia(base, exponente):
    """Calcula base^exponente"""
    return base ** exponente

def raiz_cuadrada(numero):
    """Calcula raíz cuadrada"""
    if numero < 0:
        return "Error: No se puede calcular raíz de negativo"
    return numero ** 0.5

def modulo(a, b):
    """Retorna el residuo de a / b"""
    return a % b
```

#### O2: Historial (10 pts)

```python
historial = []

def agregar_al_historial(operacion, resultado):
    """Guarda operación en historial"""
    historial.append(f"{operacion} = {resultado}")

def mostrar_historial():
    """Muestra todas las operaciones realizadas"""
    if not historial:
        print("No hay operaciones en el historial")
        return
    
    print("\n--- HISTORIAL ---")
    for i, operacion in enumerate(historial, 1):
        print(f"{i}. {operacion}")
```

#### O3: Extras (10 pts)

- Colores en terminal con ANSI codes
- Guardar historial en archivo
- Modo científico con `math` library
- Interfaz mejorada ASCII art
- Tests automatizados

---

## 🚀 Instrucciones de Desarrollo

### Fase 1: Setup (15 min)

1. Crear archivo `calculadora.py`
2. Agregar estructura básica:

```python
# calculadora.py

def mostrar_menu():
    """Muestra el menú de opciones"""
    pass

def main():
    """Función principal"""
    pass

if __name__ == "__main__":
    main()
```

3. Probar que ejecuta: `python calculadora.py`

### Fase 2: Funciones de Operaciones (30 min)

1. Implementar las 4 operaciones básicas
2. Probar cada función individualmente:

```python
# Pruebas rápidas
print(sumar(5, 3))      # 8
print(restar(10, 4))    # 6
print(multiplicar(3, 7)) # 21
print(dividir(10, 2))   # 5.0
print(dividir(10, 0))   # Error mensaje
```

### Fase 3: Menú y Entrada (45 min)

1. Crear función `mostrar_menu()`
2. Implementar captura de opción
3. Implementar captura de números
4. Conectar con funciones de operaciones

### Fase 4: Bucle Principal (30 min)

1. Implementar bucle `while`
2. Agregar lógica según opción elegida
3. Implementar opción de salida

### Fase 5: Manejo de Errores (30 min)

1. Agregar `try/except` para entrada de números
2. Validar opción del menú
3. Manejar casos especiales (división por cero)
4. Probar todos los casos edge

### Fase 6: Testing(20 min)

1. Probar todas las operaciones
2. Intentar romper el programa con entradas inválidas
3. Verificar que los mensajes sean claros
4. Asegurar que nunca crashea

### Fase 7: Documentación (20 min)

1. Agregar docstrings a todas las funciones
2. Comentar secciones complejas
3. Crear README.md de entrega

---

## 📊 Evaluación

Ver [rubrica-evaluacion.md](../rubrica-evaluacion.md#3--producto-calculadora-interactiva-30) para detalles completos.

### Distribución de Puntos

| Criterio | Peso | Puntos |
|----------|------|--------|
| **Funcionalidad** | 40% | 40 pts |
| **Código Limpio** | 25% | 25 pts |
| **Interfaz Usuario** | 20% | 20 pts |
| **Documentación** | 15% | 15 pts |
| **Total** | 100% | **100 pts** |

### Niveles de Calidad

- **90-100 pts**: Excelente - Todos los obligatorios + opcionales
- **80-89 pts**: Bueno - Todos los obligatorios + 1 opcional
- **70-79 pts**: Suficiente - Todos los obligatorios cumplidos
- **<70 pts**: Insuficiente - Faltan requisitos obligatorios

---

## 📦 Entrega

### Estructura de Archivos

```
apellido-nombre-week-01/
├── README.md                 # Descripción y reflexión
├── calculadora.py            # Código principal
├── requirements.txt          # Dependencias (si aplica)
└── capturas/                 # Screenshots (opcional)
    ├── menu.png
    └── operacion.png
```

### README.md de Entrega (Template)

```markdown
# Calculadora Interactiva - [Tu Nombre]

## Descripción
Calculadora de consola que permite realizar operaciones matemáticas básicas mediante un menú interactivo.

## Funcionalidades Implementadas

### Obligatorias
- [x] Suma
- [x] Resta
- [x] Multiplicación
- [x] División con validación
- [x] Menú interactivo
- [x] Bucle principal
- [x] Manejo de errores

### Opcionales
- [ ] Operaciones avanzadas
- [ ] Historial
- [ ] Extras

## Instrucciones de Uso

1. Ejecutar el programa:
   ```bash
   python calculadora.py
   ```

2. Elegir opción del menú (1-5)

3. Ingresar los números cuando sea solicitado

4. Ver resultado

5. Opción 5 para salir

## Ejemplo de Uso

```
================================
   CALCULADORA INTERACTIVA
================================
1. Sumar
2. Restar
3. Multiplicar
4. Dividir
5. Salir
================================
Elige una opción (1-5): 1
Primer número: 10
Segundo número: 5
Resultado: 10 + 5 = 15

¿Realizar otra operación? (s/n):
```

## Reflexión

### ¿Qué aprendí?
[Tu respuesta: conceptos clave que dominaste]

### ¿Qué fue lo más difícil?
[Tu respuesta: retos que enfrentaste]

### ¿Qué mejoraría?
[Tu respuesta: ideas para versión futura]

## Autor
[Tu Nombre] - Week 01 Bootcamp PyTorch
```

### Plataforma y Fecha

- **Formato**: ZIP o repositorio Git
- **Nombre**: `apellido-nombre-week-01.zip`
- **Fecha límite**: Domingo 23:59
- **Plataforma**: [Especificar]

---

## 💡 Tips y Consejos

### Estrategia de Desarrollo

1. **Empieza simple**: Version mínima primero, luego mejora
2. **Prueba frecuentemente**: Ejecuta después de cada cambio
3. **Una función a la vez**: No intentes todo junto
4. **Usa print() para debugging**: Ver qué valores tienen las variables

### Errores Comunes

#### 1. División por Cero

```python
# ❌ Sin validación
resultado = a / b

# ✅ Con validación
if b == 0:
    print("Error: No puedes dividir por cero")
else:
    resultado = a / b
```

#### 2. Input No Numérico

```python
# ❌ Sin manejo de error
numero = float(input("Número: "))

# ✅ Con try/except
try:
    numero = float(input("Número: "))
except ValueError:
    print("Error: Ingresa un número válido")
```

#### 3. Bucle Infinito

```python
# ❌ Sin condición de salida
while True:
    # ... nunca sale

# ✅ Con opción de salir
while True:
    opcion = input("Opción (0 para salir): ")
    if opcion == '0':
        break
```

### Debugging

```python
# Agregar prints temporales
print(f"DEBUG: opcion = {opcion}")
print(f"DEBUG: num1 = {num1}, num2 = {num2}")

# Verificar tipos
print(f"DEBUG: type(num1) = {type(num1)}")
```

---

## 🔗 Recursos de Apoyo

### Material del Curso

- [Teoría: Variables](../1-teoria/02-variables-tipos-datos.md)
- [Teoría: Operadores](../1-teoria/03-operadores.md)
- [Teoría: Estructuras de Control](../1-teoria/04-estructuras-control.md)
- [Teoría: Funciones](../1-teoria/05-funciones-basicas.md)

### Documentación Python

- [Built-in Functions](https://docs.python.org/3/library/functions.html)
- [Input/Output](https://docs.python.org/3/tutorial/inputoutput.html)
- [Errors and Exceptions](https://docs.python.org/3/tutorial/errors.html)

### Ejemplos de Referencia

```python
# Estructura recomendada del programa
def mostrar_menu():
    # Código del menú
    pass

def obtener_opcion():
    # Capturar y validar opción
    pass

def obtener_numeros():
    # Capturar y validar números
    pass

def procesar_operacion(opcion, num1, num2):
    # Ejecutar operación según opción
    pass

def main():
    print("¡Bienvenido a la Calculadora!")
    
    while True:
        mostrar_menu()
        opcion = obtener_opcion()
        
        if opcion == '5':
            print("¡Hasta luego!")
            break
        
        num1, num2 = obtener_numeros()
        resultado = procesar_operacion(opcion, num1, num2)
        print(f"Resultado: {resultado}")
        
        continuar = input("\n¿Otra operación? (s/n): ")
        if continuar.lower() != 's':
            break

if __name__ == "__main__":
    main()
```

---

## ❓ FAQ

### ¿Puedo usar librerías externas?

Para este proyecto, usa solo Python estándar (sin librerías externas). Si quieres usar `math` para operaciones avanzadas, está permitido.

### ¿Cuántas líneas debe tener mi código?

No hay un mínimo o máximo. Un código bien estructurado podría tener 100-200 líneas. Calidad > Cantidad.

### ¿Debo crear un archivo separado para funciones?

No es necesario para este proyecto. Un solo archivo `calculadora.py` está bien.

### Si termino antes, ¿qué hago?

1. Implementa opcionales
2. Mejora la interfaz
3. Agrega más validaciones
4. Escribe tests
5. Ayuda a compañeros en el foro

---

## 🎓 Criterios de Éxito

Antes de entregar, verifica:

- [ ] El programa ejecuta sin errores
- [ ] Todas las operaciones funcionan
- [ ] División por cero está manejada
- [ ] Entradas inválidas no crashean el programa
- [ ] El menú es claro y fácil de usar
- [ ] Hay al menos un comentario por función
- [ ] El código sigue PEP 8 básico (nombres, indentación)
- [ ] README.md completado con reflexión
- [ ] Has probado casos edge (números negativos, decimales, cero)

---

<p align="center">
  <strong>🚀 ¡Éxito con tu Proyecto!</strong><br>
  <em>"El código es como el humor. Si tienes que explicarlo, no es bueno." - Cory House</em>
</p>

---

_Proyecto Week 01 | Bootcamp PyTorch Zero to Hero_

**Última actualización**: Febrero 2026
