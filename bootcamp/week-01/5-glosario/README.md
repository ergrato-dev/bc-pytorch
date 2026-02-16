# 📖 Glosario - Semana 01: Fundamentos de Python

> Definiciones de términos clave de la semana para referencia rápida.

---

## Índice Alfabético

[A](#a) | [B](#b) | [C](#c) | [D](#d) | [E](#e) | [F](#f) | [G](#g) | [H](#h) | [I](#i) | [L](#l) | [M](#m) | [Ó](#ó) | [P](#p) | [R](#r) | [S](#s) | [T](#t) | [V](#v)

---

## A

### Asignación
Operación de asignar un valor a una variable usando el operador `=`.

```python
nombre = "Ana"  # Asignación simple
x = y = 10      # Asignación múltiple
```

### Argumento
Valor pasado a una función al llamarla.

```python
def saludar(nombre):  # nombre es parámetro
    print(f"Hola, {nombre}")

saludar("Carlos")  # "Carlos" es argumento
```

---

## B

### Booleano (bool)
Tipo de dato que solo puede ser `True` o `False`.

```python
es_mayor = True
esta_activo = False
resultado = 5 > 3  # True
```

### break
Palabra clave que termina un bucle inmediatamente.

```python
for i in range(10):
    if i == 5:
        break  # Sale del bucle
    print(i)  # Imprime 0, 1, 2, 3, 4
```

### Bucle
Estructura que repite código mientras se cumpla una condición.

```python
# Bucle for
for i in range(3):
    print(i)

# Bucle while
x = 0
while x < 3:
    print(x)
    x += 1
```

---

## C

### Cadena (string/str)
Tipo de dato que representa texto.

```python
nombre = "Python"
mensaje = 'Hola mundo'
multilinea = """
    Varias
    líneas
"""
```

### Casting
Conversión explícita de un tipo de dato a otro.

```python
numero = int("42")      # str → int
texto = str(100)        # int → str
decimal = float("3.14") # str → float
```

### Comentario
Texto ignorado por Python, usado para documentar código.

```python
# Comentario de una línea

"""
Comentario de
múltiples líneas
(docstring)
"""
```

### continue
Palabra clave que salta a la siguiente iteración del bucle.

```python
for i in range(5):
    if i == 2:
        continue  # Salta el 2
    print(i)  # 0, 1, 3, 4
```

---

## D

### def
Palabra clave para definir una función.

```python
def mi_funcion():
    print("Hola")

def otra(parametro):
    return parametro * 2
```

### División Entera (//)
Operador que divide y retorna solo la parte entera.

```python
print(7 / 2)   # 3.5 (división normal)
print(7 // 2)  # 3 (división entera)
```

### Docstring
Cadena de documentación al inicio de función/clase.

```python
def funcion():
    """
    Este es un docstring.
    Explica qué hace la función.
    """
    pass
```

---

## E

### elif
Abreviatura de "else if", para múltiples condiciones.

```python
if edad < 13:
    print("Niño")
elif edad < 18:
    print("Adolescente")
else:
    print("Adulto")
```

### else
Bloque que se ejecuta si la condición if no se cumple.

```python
if condicion:
    # Si es True
else:
    # Si es False
```

### Entero (int)
Tipo de dato para números sin decimales.

```python
edad = 25
cantidad = -10
grande = 999_999_999
```

---

## F

### Flotante (float)
Tipo de dato para números con decimales.

```python
altura = 1.75
precio = 99.99
pi = 3.14159
```

### for
Bucle que itera sobre una secuencia.

```python
for i in range(5):
    print(i)

for letra in "Python":
    print(letra)
```

### f-string
Cadena formateada con expresiones interpoladas (Python 3.6+).

```python
nombre = "Ana"
edad = 25
mensaje = f"{nombre} tiene {edad} años"
```

### Función
Bloque de código reutilizable que realiza una tarea.

```python
def saludar(nombre):
    """Saluda a una persona"""
    return f"Hola, {nombre}!"
```

---

## G

### Global
Variable definida fuera de funciones, accesible en todo el programa.

```python
x = 100  # Variable global

def funcion():
    global x  # Modificar global
    x = 200
```

---

## H

### Herencia
*(Concepto de POO, no cubierto en Week-01)*

---

## I

### if
Estructura condicional que ejecuta código si se cumple una condición.

```python
if edad >= 18:
    print("Mayor de edad")
```

### Indentación
Espacios al inicio de línea que definen bloques de código en Python.

```python
# ✅ Correcto: 4 espacios
if True:
    print("Indentado")
    print("También indentado")

# ❌ Error: Indentación inconsistente
if True:
  print("2 espacios")
    print("4 espacios")  # Error!
```

### input()
Función para capturar entrada del usuario.

```python
nombre = input("¿Cómo te llamas? ")
edad = int(input("¿Edad? "))
```

### Intérprete
Programa que ejecuta código Python línea por línea.

---

## L

### Local
Variable definida dentro de una función, solo existe en esa función.

```python
def funcion():
    x = 10  # Variable local
    print(x)

# print(x)  # Error: x no existe aquí
```

---

## M

### Método
Función asociada a un objeto.

```python
texto = "Python"
print(texto.upper())  # upper() es un método
print(texto.lower())  # lower() es un método
```

### Módulo
Operador `%` que retorna el residuo de una división.

```python
print(10 % 3)   # 1 (residuo)
print(7 % 2)    # 1
print(8 % 2)    # 0 (sin residuo, es par)
```

---

## N

### None
Valor especial que representa ausencia de valor.

```python
resultado = None
if resultado is None:
    print("No hay resultado")
```

---

## Ó

### Ópera dor
Símbolo que realiza una operación.

```python
# Aritméticos: +, -, *, /, //, %, **
# Comparación: ==, !=, >, <, >=, <=
# Lógicos: and, or, not
# Asignación: =, +=, -=, *=, /=
```

---

## P

### Parámetro
Variable que recibe una función en su definición.

```python
def sumar(a, b):  # a y b son parámetros
    return a + b
```

### pass
Palabra clave que no hace nada, placeholder.

```python
def funcion_vacia():
    pass  # TODO: implementar después

if condicion:
    pass  # Aún no sé qué poner aquí
```

### PEP 8
Guía de estilo oficial de Python.

**Reglas clave**:
- 4 espacios para indentación
- Líneas máximo 79 caracteres
- snake_case para variables y funciones
- PascalCase para clases

### Potencia (**)
Operador de exponenciación.

```python
print(2 ** 3)   # 8 (2 al cubo)
print(10 ** 2)  # 100 (10 al cuadrado)
print(5 ** 0)   # 1 (cualquier número elevado a 0)
```

### print()
Función para mostrar salida en pantalla.

```python
print("Hola")
print("Nombre:", nombre)
print(f"Valor: {x}")
```

---

## R

### range()
Función que genera una secuencia de números.

```python
range(5)        # 0, 1, 2, 3, 4
range(2, 6)     # 2, 3, 4, 5
range(0, 10, 2) # 0, 2, 4, 6, 8
```

### return
Palabra clave que retorna un valor de una función.

```python
def suma(a, b):
    return a + b

resultado = suma(3, 5)  # resultado = 8
```

---

## S

### Scope
Ámbito donde una variable es accesible.

```python
x = "global"  # Scope global

def funcion():
    y = "local"  # Scope local
    print(x)     # Puede leer global
    print(y)     # Puede leer local

funcion()
# print(y)  # Error: y no existe aquí
```

### Sintaxis
Reglas que definen cómo escribir código Python válido.

```python
# ✅ Sintaxis correcta
nombre = "Ana"
if edad >= 18:
    print("Mayor")

# ❌ Sintaxis incorrecta
nombre = Ana  # Falta comillas
if edad >= 18  # Faltan dos puntos
print("Mayor")  # Falta indentación
```

---

## T

### Type hints
Anotaciones opcionales de tipos (Python 3.5+).

```python
def saludar(nombre: str) -> str:
    return f"Hola, {nombre}"

edad: int = 25
altura: float = 1.75
```

### type()
Función que retorna el tipo de un dato.

```python
print(type(42))      # <class 'int'>
print(type(3.14))    # <class 'float'>
print(type("Hola"))  # <class 'str'>
print(type(True))    # <class 'bool'>
```

---

## V

### Variable
Nombre que apunta a un valor en memoria.

```python
edad = 25         # Variable de tipo int
nombre = "Ana"    # Variable de tipo str
es_mayor = True   # Variable de tipo bool
```

---

## W

### while
Bucle que ejecuta mientras una condición sea verdadera.

```python
contador = 0
while contador < 5:
    print(contador)
    contador += 1
```

---

## Referencias Cruzadas

- **Operadores** → Ver [03-operadores.md](../1-teoria/03-operadores.md)
- **Estructuras** → Ver [04-estructuras-control.md](../1-teoria/04-estructuras-control.md)
- **Funciones** → Ver [05-funciones-basicas.md](../1-teoria/05-funciones-basicas.md)
- **Cheat Sheet** → Ver [cheat-sheet.md](cheat-sheet.md)

---

<p align="center">
  <strong>📖 Glosario Week 01</strong><br>
  <em>"El conocimiento de las palabras conduce al conocimiento de las cosas." - Platón</em>
</p>

---

[⬅️ Volver a Week-01](../README.md) | [📋 Cheat Sheet](cheat-sheet.md)
