# 📋 Cheat Sheet - Semana 01: Fundamentos de Python

> Referencia rápida de sintaxis Python. Copy-paste ready!

---

## 🎯 Variables y Tipos

```python
# Asignación
nombre = "Ana"
edad = 25
altura = 1.75
es_activo = True

# Múltiples asignaciones
x, y, z = 1, 2, 3
a = b = c = 0

# Tipos básicos
type(42)        # <class 'int'>
type(3.14)      # <class 'float'>
type("Hola")    # <class 'str'>
type(True)      # <class 'bool'>
```

---

## ⚙️ Operadores

### Aritméticos

```python
5 + 3   # 8   - Suma
5 - 3   # 2   - Resta
5 * 3   # 15  - Multiplicación
5 / 2   # 2.5 - División
5 // 2  # 2   - División entera
5 % 2   # 1   - Módulo (residuo)
5 ** 2  # 25  - Potencia
```

### Comparación

```python
5 == 5  # True  - Igual
5 != 3  # True  - Diferente
5 > 3   # True  - Mayor que
5 < 3   # False - Menor que
5 >= 5  # True  - Mayor o igual
5 <= 3  # False - Menor o igual
```

### Lógicos

```python
True and True    # True
True and False   # False
True or False    # True
False or False   # False
not True         # False
not False        # True
```

### Asignación Compuesta

```python
x = 10
x += 5   # x = x + 5 → 15
x -= 3   # x = x - 3 → 12
x *= 2   # x = x * 2 → 24
x /= 4   # x = x / 4 → 6.0
```

---

## 📝 Strings

```python
# Creación
nombre = "Python"
apellido = 'Programming'
multilínea = """
    Varias
    líneas
"""

# Concatenación
nombre + " " + apellido  #"Python Programming"

# F-strings (Python 3.6+)
edad = 25
f"{nombre} tiene {edad} años"  # "Python tiene 25 años"

# Métodos útiles
texto = "  Python  "
texto.upper()      # "  PYTHON  "
texto.lower()      # "  python  "
texto.strip()      # "Python"
texto.replace("P", "J")  # "  Jython  "

# Indexación
palabra = "Python"
palabra[0]    # "P"
palabra[-1]   # "n"
palabra[0:3]  # "Pyt"
```

---

## 🔀 Condicionales

```python
# if simple
if edad >= 18:
    print("Mayor de edad")

# if-else
if temperatura > 25:
    print("Calor")
else:
    print("Frío")

# if-elif-else
if nota >= 90:
    print("A")
elif nota >= 80:
    print("B")
elif nota >= 70:
    print("C")
else:
    print("D")

# Operador ternario
mensaje = "Mayor" if edad >= 18 else "Menor"
```

---

## 🔄 Bucles

### for

```python
# Con range
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

for i in range(2, 6):
    print(i)  # 2, 3, 4, 5

for i in range(0, 10, 2):
    print(i)  # 0, 2, 4, 6, 8

# Iterar string
for letra in "Python":
    print(letra)  # P, y, t, h, o, n

# Enumerate
for i, valor in enumerate(["a", "b", "c"]):
    print(f"{i}: {valor}")
# 0: a, 1: b, 2: c
```

### while

```python
# Básico
contador = 0
while contador < 5:
    print(contador)
    contador += 1

# Con condición
opcion = ""
while opcion != "salir":
    opcion = input("Comando: ")
```

### Control de Bucles

```python
# break - Salir del bucle
for i in range(10):
    if i == 5:
        break
    print(i)  # 0, 1, 2, 3, 4

# continue - Saltar iteración
for i in range(5):
    if i == 2:
        continue
    print(i)  # 0, 1, 3, 4

# pass - Placeholder
if condicion:
    pass  # TODO: implementar
```

---

## ⚡ Funciones

```python
# Función simple
def saludar():
    print("¡Hola!")

saludar()  # Llamada

# Con parámetros
def saludar(nombre):
    print(f"¡Hola, {nombre}!")

saludar("Ana")  # ¡Hola, Ana!

# Con return
def sumar(a, b):
    return a + b

resultado = sumar(5, 3)  # 8

#Con valor por defecto
def saludar(nombre, saludo="Hola"):
    return f"{saludo}, {nombre}!"

saludar("Ana")            # "Hola, Ana!"
saludar("Carlos", "Hey")  # "Hey, Carlos!"

# Múltiples returns
def operaciones(a, b):
    return a + b, a - b, a * b

suma, resta, multi = operaciones(10, 5)
# suma=15, resta=5, multi=50

# Con docstring
def dividir(a, b):
    """
    Divide a entre b.
    
    Args:
        a (float): Dividendo
        b (float): Divisor
    
    Returns:
        float: Resultado de la división
    """
    if b == 0:
        return "Error: división por cero"
    return a / b
```

---

## 📥📤 Entrada/Salida

```python
# Salida
print("Hola mundo")
print("Valor:", 42)
print(f"x = {x}, y = {y}")

# Sin salto de línea
print("Cargando", end="...")
print("Listo")  # "Cargando...Listo"

# Entrada
nombre = input("¿Nombre? ")
edad = int(input("¿Edad? "))
altura = float(input("¿Altura? "))
```

---

## 🔄 Conversión de Tipos

```python
# A entero
int("42")        # 42
int(3.9)         # 3 (trunca)
int(True)        # 1

# A flotante
float("3.14")    # 3.14
float(42)        # 42.0
float(True)      # 1.0

# A string
str(42)          # "42"
str(3.14)        # "3.14"
str(True)        # "True"

# A booleano
bool(1)          # True
bool(0)          # False
bool("")         # False
bool("Hola")     # True
```

---

## 🐛 Debugging

```python
# Imprimir para debug
print(f"DEBUG: x = {x}")
print(f"DEBUG: type(x) = {type(x)}")

# Ver valor y tipo
x = 42
print(f"{x} es {type(x)}")

# Ayuda
help(print)
help(list)
```

---

## ⚠️ Errores Comunes

### Error 1: = vs ==

```python
# ❌ Incorrecto
if x = 5:  # SyntaxError

# ✅ Correcto
if x == 5:
    pass
```

### Error 2: Indentación

```python
# ❌ Incorrecto
if True:
print("Hola")  # IndentationError

# ✅ Correcto
if True:
    print("Hola")
```

### Error 3: Concatenar String con Número

```python
# ❌ Incorrecto
edad = 25
mensaje = "Tengo " + edad + " años"  # TypeError

# ✅ Correcto
mensaje = "Tengo " + str(edad) + " años"
mensaje = f"Tengo {edad} años"  # Mejor
```

### Error 4: División por Cero

```python
# ❌ Sin validación
resultado = 10 / 0  # ZeroDivisionError

# ✅ Con validación
if b != 0:
    resultado = a / b
else:
    print("Error: división por cero")
```

---

## 💡 Patterns Comunes

### Validar Input

```python
while True:
    try:
        edad = int(input("Edad: "))
        if edad > 0 and edad < 120:
            break
        print("Edad inválida")
    except ValueError:
        print("Ingresa un número")
```

### Menú de Opciones

```python
while True:
    print("\n1. Opción 1")
    print("2. Opción 2")
    print("3. Salir")
    
    opcion = input("Elige: ")
    
    if opcion == '1':
        # Acción 1
        pass
    elif opcion == '2':
        # Acción 2
        pass
    elif opcion == '3':
        print("Adiós")
        break
    else:
        print("Opción inválida")
```

### Par o Impar

```python
numero = 17
if numero % 2 == 0:
    print("Par")
else:
    print("Impar")
```

### FizzBuzz

```python
for i in range(1, 101):
    if i % 15 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```

---

## 🔗 Quick Links

- [Python Docs](https://docs.python.org/3/)
- [PEP 8 Style Guide](https://pep8.org/)
- [Glosario Completo](README.md)
- [Teoría Week 01](../1-teoria/)

---

_Cheat Sheet Week 01 | Bootcamp PyTorch Zero to Hero_
