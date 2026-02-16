# 📦 Variables y Tipos de Datos

> Aprende a almacenar información en variables y trabaja con los tipos de datos fundamentales de Python.

---

## 📋 Contenido

- [Variables](#variables)
- [Tipos de Datos Básicos](#tipos-de-datos-básicos)
- [Conversión de Tipos (Casting)](#conversión-de-tipos-casting)
- [Entrada y Salida](#entrada-y-salida)
- [Ejercicios](#ejercicios)

---

## Variables

### ¿Qué es una Variable?

Una **variable** es un nombre que apunta a un valor almacenado en memoria. Piensa en ella como una "etiqueta" para un dato.

```python
# Asignación de variable
nombre = "Ana"
edad = 25
altura = 1.65
```

### Reglas para Nombres de Variables

#### ✅ Permitido

```python
nombre = "Carlos"
nombre_completo = "Carlos Pérez"
edad_2024 = 30
_privado = "valor"
CONSTANTE = 100
```

#### ❌ No Permitido

```python
2nombre = "Error"      # No puede empezar con número
nombre-completo = "Error"  # No guiones, usa _
class = "Error"        # Palabra reservada
```

### Convenciones de Nombre (PEP 8)

Style: **snake_case** para variables y funciones

```python
# ✅ Bueno
nombre_usuario = "juan"
edad_maxima = 100
calcular_promedio = lambda x: sum(x) / len(x)

# ❌ Evitar
nombreUsuario = "juan"   # camelCase - para JS
NombreUsuario= "juan"    # PascalCase - para clases
```

### Múltiples Asignaciones

```python
# Asignación múltiple
x, y, z = 1, 2, 3
print(f"x={x}, y={y}, z={z}")  # x=1, y=2, z=3

# Mismo valor a múltiples variables
a = b = c = 0
print(f"a={a}, b={b}, c={c}")  # a=0, b=0, c=0

# Intercambiar valores (swap)
a, b = 10, 20
a, b = b, a  # Swap pythónico
print(f"a={a}, b={b}")  # a=20, b=10
```

---

## Tipos de Datos Básicos

Python tiene **tipos dinámicos**: no necesitas declarar el tipo, se infiere automáticamente.

![Tipos de Datos en Python](../0-assets/02-data-types.svg)

### 1. Enteros (int) 🔢

Números sin decimales, sin límite de tamaño.

```python
edad = 25
año = 2024
temperatura = -5
grande = 999_999_999_999  # Puedes usar _ para legibilidad

print(type(edad))  # <class 'int'>
```

**Operaciones comunes**:

```python
x = 10
print(x + 5)   # 15 - Suma
print(x - 3)   # 7  - Resta
print(x * 2)   # 20 - Multiplicación
print(x / 3)   # 3.333... - División (siempre retorna float)
print(x // 3)  # 3  - División entera
print(x % 3)   # 1  - Módulo (residuo)
print(x ** 2)  # 100 - Potencia
```

### 2. Flotantes (float) 🔢.🔢

Números con decimales.

```python
altura = 1.75
precio = 99.99
pi = 3.14159
temperatura = -3.5

print(type(altura))  # <class 'float'>
```

**Precisión de flotantes**:

```python
# Cuidado con precisión de punto flotante
print(0.1 + 0.2)  # 0.30000000000000004 (no exactamente 0.3)
print(0.1 + 0.2 == 0.3)  # False

# Solución: redondear
resultado = round(0.1 + 0.2, 1)
print(resultado)  # 0.3
```

### 3. Cadenas (str) 📝

Texto entre comillas simples o dobles.

```python
nombre = "Carlos"
apellido = 'Pérez'
frase = "Python es 'genial'"  # Comillas mixtas
multilinea = """
    Esto es una cadena
    de múltiples líneas
"""

print(type(nombre))  # <class 'str'>
```

**Operaciones con strings**:

```python
# Concatenación
nombre = "Ana"
apellido = "García"
nombre_completo = nombre + " " + apellido
print(nombre_completo)  # "Ana García"

# Repetición
risa = "ja" * 3
print(risa)  # "jajaja"

# Longitud
print(len(nombre))  # 3

# Indexación (empieza en 0)
print(nombre[0])   # "A"
print(nombre[-1])  # "a" (último)

# Slicing
texto = "Python"
print(texto[0:3])   # "Pyt"
print(texto[2:])    # "thon"
print(texto[:4])    # "Pyth"
```

**Métodos útiles**:

```python
texto = "  Python Programming  "

print(texto.upper())      # "  PYTHON PROGRAMMING  "
print(texto.lower())      # "  python programming  "
print(texto.strip())      # "Python Programming" (sin espacios)
print(texto.replace("Python", "Java"))  # "  Java Programming  "
print(texto.split())      # ['Python', 'Programming']
```

**F-strings (Formateo moderno)**:

```python
nombre = "Carlos"
edad = 30
altura = 1.75

# F-strings (Python 3.6+) - RECOMENDADO
mensaje = f"{nombre} tiene {edad} años y mide {altura}m"
print(mensaje)  # "Carlos tiene 30 años y mide 1.75m"

# Con expresiones
print(f"En 5 años tendrá {edad + 5} años")

# Con formato
precio = 99.99567
print(f"Precio: ${precio:.2f}")  # "Precio: $100.00"
```

### 4. Booleanos (bool) ✔️❌

Verdadero o Falso.

```python
esta_activo = True
es_mayor_edad = False

print(type(esta_activo))  # <class 'bool'>
```

**Valores que son False**:

```python
bool(0)           # False
bool(0.0)         # False
bool("")          # False (string vacío)
bool(None)        # False
bool([])          # False (lista vacía)

# Todo lo demás es True
bool(1)           # True
bool("Python")    # True
bool([1, 2])      # True
```

### 5. None Type 🚫

Representa la ausencia de valor.

```python
resultado = None
print(type(resultado))  # <class 'NoneType'>

# Útil para inicializar variables
nombre_usuario = None
if nombre_usuario is None:
    print("No hay usuario")
```

---

## Conversión de Tipos (Casting)

### Conversión Explícita

```python
# String a Int
edad_str = "25"
edad_int = int(edad_str)
print(edad_int + 5)  # 30

# String a Float
precio_str = "99.99"
precio_float = float(precio_str)
print(precio_float * 2)  # 199.98

# Int a String
numero = 42
numero_str = str(numero)
print("El número es: " + numero_str)

# Float a Int (trunca decimales)
altura = 1.75
altura_int = int(altura)
print(altura_int)  # 1

# A Booleano
print(bool(1))      # True
print(bool(0))      # False
print(bool(""))     # False
print(bool("Hola")) # True
```

### Errores Comunes

```python
# ❌ No se puede convertir string no numérico
texto = "Python"
# numero = int(texto)  # ValueError: invalid literal

# ❌ Concatenar string con número
edad = 25
# mensaje = "Tengo " + edad + " años"  # TypeError

# ✅ Soluciones
mensaje = "Tengo " + str(edad) + " años"  # Convertir
mensaje = f"Tengo {edad} años"             # F-string (mejor)
```

---

## Entrada y Salida

### Salida: print()

```python
# Básico
print("Hola mundo")

# Múltiples argumentos
print("Nombre:", "Carlos", "Edad:", 25)

# Sin salto de línea
print("Procesando", end="...")
print("Listo")  # "Procesando...Listo"

# Separador personalizado
print("Ana", "Carlos", "María", sep=" -> ")
# "Ana -> Carlos -> María"
```

### Entrada: input()

```python
# Leer texto del usuario
nombre = input("¿Cómo te llamas? ")
print(f"Hola, {nombre}!")

# input() siempre retorna string
edad_str = input("¿Cuántos años tienes? ")
edad = int(edad_str)  # Convertir a int
print(f"En 10 años tendrás {edad + 10} años")

# Una línea
edad = int(input("¿Edad? "))
```

---

## Verificar Tipos

```python
# Función type()
x = 42
print(type(x))  # <class 'int'>

# Función isinstance()
numero = 10
print(isinstance(numero, int))    # True
print(isinstance(numero, float))  # False

# Múltiples tipos
valor = 3.14
if isinstance(valor, (int, float)):
    print("Es un número")
```

---

## Ejercicios

### Ejercicio 1: Swap de Variables

```python
# Intercambia los valores de a y b
a = 10
b = 20

# Tu código aquí
a, b = b, a

print(f"a = {a}, b = {b}")  # a = 20, b = 10
```

### Ejercicio 2: Calculadora de Edad

```python
# Pide el año de nacimiento y calcula la edad
año_actual = 2024
año_nacimiento = int(input("¿Año de nacimiento? "))
edad = año_actual - año_nacimiento
print(f"Tienes {edad} años")
```

### Ejercicio 3: Conversión de Temperatura

```python
# Convierte Celsius a Fahrenheit
celsius = float(input("Temperatura en Celsius: "))
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius}°C = {fahrenheit}°F")
```

---

## ✅ Checklist

- [ ] Puedo crear y nombrar variables correctamente
- [ ] Conozco los 4 tipos básicos: int, float, str, bool
- [ ] Sé convertir entre tipos con casting
- [ ] Puedo usar f-strings para formatear
- [ ] Entiendo cómo usar input() y print()

---

## 🎯 Próximo Paso

Ahora que sabes trabajar con datos, aprende a **operar con ellos**.

[➡️ Siguiente: Operadores](03-operadores.md)

---

[⬅️ Anterior: Introducción](01-introduccion-python.md) | [🏠 Índice](README.md)
