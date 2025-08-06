#actividades 

ACT01-GRUPO2..pdf
# Contenido
```table-of-contents
```
# Enunciado
![[IPC_01_03_ACTIVIDAD-01.pdf]]

---
# Pseudo código

## Ejercicio 4: *Adivinar un Número*

Este es el algoritmo para el juego en el que una persona debe adivinar un número pensado por otra, recibiendo pistas de "mayor", "menor" o "igual".

**Solución en Pseudocódigo:**
1. **Inicio del Algoritmo**
2. Definir `numero_secreto` con un valor (ej: 58).
3. Definir `intento_usuario` con un valor inicial nulo o 0.
4. **Mientras** `intento_usuario` sea diferente de `numero_secreto`, **hacer**:
    1. Mostrar "Introduce un número para adivinar".
    2. Leer `intento_usuario`.
    3. **Si** `intento_usuario` es menor que `numero_secreto`, **entonces**:
        1. Mostrar "El número a adivinar es **mayor**".
    4. **Si no, si** `intento_usuario` es mayor que `numero_secreto`, **entonces**:
        1. Mostrar "El número a adivinar es **menor**".
    5. **Si no**, **entonces**:
        1. Mostrar "¡Correcto! Has adivinado el número."
5. **Fin del Algoritmo**
## Ejercicio 5: *Pintando la Palabra "Python"*
Este algoritmo describe los pasos para pintar la palabra "Python" usando solo movimientos básicos del pincel, como se pide en el ejercicio.

**Solución en Pseudocódigo:**
1. **Inicio del Algoritmo**
2. // Iniciar con la letra **P**
3. Bajar pincel.
4. Mover pincel hacia abajo (4 veces).
5. Mover pincel hacia arriba (2 veces).
6. Mover pincel a la derecha (2 veces).
7. Mover pincel hacia abajo (1 vez).
8. Mover pincel a la izquierda (2 veces).
9. Levantar pincel.
10. Mover pincel a la derecha (4 veces para dejar espacio).
11. // Continuar con la letra **Y**
12. Bajar pincel.
13. Mover pincel a la derecha (2 veces).
14. Mover pincel a la izquierda (1 vez).
15. Mover pincel hacia abajo (2 veces).
16. Levantar pincel.
17. Mover pincel a la izquierda (1 vez).
18. Mover pincel hacia arriba (2 veces).
19. Bajar pincel.
20. Mover pincel a la derecha (2 veces).
21. Levantar pincel.
22. Mover pincel a la derecha (2 veces para dejar espacio).
23. // Continuar con la letra **T**
24. Bajar pincel.
25. Mover pincel a la derecha (2 veces).
26. Mover pincel a la izquierda (1 vez).
27. Mover pincel hacia abajo (4 veces).
28. Levantar pincel.
29. Mover pincel a la derecha (2 veces para dejar espacio).
30. // Continuar con la letra **H**
31. Bajar pincel.
32. Mover pincel hacia abajo (4 veces).
33. Mover pincel hacia arriba (2 veces).
34. Mover pincel a la derecha (2 veces).
35. Mover pincel hacia abajo (2 veces).
36. Mover pincel hacia arriba (4 veces).
37. Levantar pincel.
38. Mover pincel a la derecha (3 veces para dejar espacio).
39. // Continuar con la letra **O**
40. Bajar pincel.
41. Mover pincel a la derecha (2 veces).
42. Mover pincel hacia abajo (4 veces).
43. Mover pincel a la izquierda (2 veces).
44. Mover pincel hacia arriba (4 veces).
45. Levantar pincel.
46. Mover pincel a la derecha (3 veces para dejar espacio).
47. // Continuar con la letra **N**
48. Bajar pincel.
49. Mover pincel hacia abajo (4 veces).
50. Mover pincel hacia arriba (4 veces).
51. Mover pincel en diagonal hacia abajo y a la derecha (2 veces).
52. Mover pincel hacia arriba (4 veces).
53. Levantar pincel.
54. **Fin del Algoritmo**

## Ejercicio 6: Algoritmo para pintar al pato
Este algoritmo describe el proceso de dibujar el pato en términos de sus formas y colores, utilizando los índices de la cuadrícula como referencia.

**Solución en Pseudocódigo:**
1. **Inicio del Algoritmo**
2. Definir los colores a utilizar: `AMARILLO`, `NARANJA`, `ROJO`, `NEGRO`.
3. // **Cabeza y Pico**
4. Seleccionar color `AMARILLO`.
5. Dibujar la forma principal de la cabeza, ocupando el área aproximada de las filas 1-3 y columnas 3-5.
6. Seleccionar color `NEGRO`.
7. Dibujar el ojo en la coordenada de la matriz: `fila 3, columna 3`.
8. Seleccionar color `NARANJA`.
9. Dibujar el pico a la izquierda de la cabeza, en la `fila 4`, columnas `1` y `2`.
10. // **Cuerpo y Cola**
11. Seleccionar color `AMARILLO`.
12. Trazar el cuello hacia abajo desde la cabeza.
13. Dibujar el cuerpo principal, extendiéndose desde el cuello hacia la derecha.
14. Formar la cola al final del cuerpo, llegando hasta la `columna 10` en la `fila 5`.
15. // **Corazón**
16. Seleccionar color `ROJO`.
17. Dibujar la forma del corazón en el centro del cuerpo. Usar la `fila 6` (columnas `5` y `8`) y la `fila 7` (columnas `6` y `7`) como guías.
18. // **Patas**
19. Seleccionar color `AMARILLO`.
20. Dibujar la parte superior de las patas por debajo del cuerpo, en la `fila 10`.
21. Seleccionar color `NARANJA`.
22. Dibujar los pies al final de las patas, principalmente en la `fila 11`.
23. **Fin del Algoritmo**

# Código en Python

## Ejercicio 4: *Juego de Adivinar el Número*
```python
# Importamos la librería 'random' para poder generar un número aleatorio.
import random

def juego_adivinar_numero():
    """
    Función principal del juego para adivinar un número.
    La computadora elige un número al azar y el usuario intenta adivinarlo.
    """
    # La computadora elige un número entero al azar entre 1 y 100.
    numero_secreto = random.randint(1, 100)
    
    # Variable para guardar el número que introduce el usuario. La inicializamos en 0.
    numero_del_usuario = 0
    
    print("¡Hola! He pensado en un número entre 1 y 100. ¿Puedes adivinarlo?")

    # Creamos un bucle que se repetirá hasta que el usuario adivine el número.
    while numero_del_usuario != numero_secreto:
        try:
            # Pedimos al usuario que introduzca un número.
            numero_del_usuario = int(input("Introduce tu número: "))

            # Comparamos el número del usuario con el número secreto.
            if numero_del_usuario < numero_secreto:
                # Si el número del usuario es menor, se lo decimos.
                print("El número que he pensado es mayor.")
            elif numero_del_usuario > numero_secreto:
                # Si el número del usuario es mayor, se lo decimos.
                print("El número que he pensado es menor.")
            else:
                # Si los números son iguales, el usuario ha ganado.
                print(f"¡Felicidades! ¡Adivinaste! El número era {numero_secreto}.")
        except ValueError:
            # Si el usuario no introduce un número válido, mostramos un error.
            print("Error: Debes introducir un número entero.")

# Llamamos a la función para iniciar el juego.
juego_adivinar_numero()
```
## Ejercicio 5: *Instrucciones para Pintar "Python"*
```python
def dibujar_python_en_ascii():
    """
    Dibuja la palabra 'Python' en la consola usando arte ASCII.
    """

    # Se define cada letra como una lista de cadenas (filas).
    # Todas las letras tienen la misma altura (7 filas) para poder alinearlas.
    letra_P = [
        "######  ",
        "#    ## ",
        "#    ## ",
        "######  ",
        "#       ",
        "#       ",
        "#       "
    ]

    letra_Y = [
        "#    #  ",
        " #  #   ",
        "  ##    ",
        "  ##    ",
        "  ##    ",
        "  ##    ",
        "  ##    "
    ]

    letra_T = [
        "####### ",
        "   #    ",
        "   #    ",
        "   #    ",
        "   #    ",
        "   #    ",
        "   #    "
    ]

    letra_H = [
        "#    #  ",
        "#    #  ",
        "#    #  ",
        "######  ",
        "#    #  ",
        "#    #  ",
        "#    #  "
    ]

    letra_O = [
        " #####  ",
        "#     # ",
        "#     # ",
        "#     # ",
        "#     # ",
        "#     # ",
        " #####  "
    ]

    letra_N = [
        "#    #  ",
        "##   #  ",
        "# #  #  ",
        "#  # #  ",
        "#   ##  ",
        "#    #  ",
        "#    #  "
    ]

    # Juntamos todas las listas de letras en una sola lista para procesarlas.
    palabra_completa = [letra_P, letra_Y, letra_T, letra_H, letra_O, letra_N]
    
    print("Dibujando la palabra 'Python' en formato ASCII:\n")

    # El bucle recorre cada fila, desde la 0 hasta la 6.
    for i in range(7):
        linea_para_imprimir = ""
        # En cada fila, concatenamos la parte correspondiente de cada letra.
        for letra in palabra_completa:
            linea_para_imprimir += letra[i] + "  "  # Añade la fila de la letra y un espacio.
        
        # Imprime la línea completa de la palabra.
        print(linea_para_imprimir)

# Llamamos a la función para ejecutar el dibujo.
dibujar_python_en_ascii()
```
## Ejercicio 6: Algoritmo para pintar al pato
```python
import tkinter as tk
from tkinter import Canvas


def dibujar_pixel_art(canvas, matriz, tamaño_celda=30):
    """
    Dibuja pixel art basado en una matriz de colores

    Args:
        canvas: Canvas de Tkinter donde dibujar
        matriz: Lista de listas con colores o None para espacios vacíos
        tamaño_celda: Tamaño en píxeles de cada celda
    """
    # Diccionario de colores
    colores = {
        "Amarillo": "#FAF600",
        "Rojo": "#FF0000",
        "Negro": "#3F403B",
        "Naranja": "#FCAB04",
        None: "#FFFFFF"  # Blanco para espacios vacíos
    }

    # Limpiar canvas
    canvas.delete("all")

    # Dibujar grid y colores
    for fila in range(len(matriz)):
        for columna in range(len(matriz[fila])):
            x1 = columna * tamaño_celda
            y1 = fila * tamaño_celda
            x2 = x1 + tamaño_celda
            y2 = y1 + tamaño_celda
            
            # Obtener color de la celda
            color_celda = matriz[fila][columna]
            color_fill = colores.get(color_celda, "#FFFFFF")
            
            # Dibujar rectángulo con borde
            canvas.create_rectangle(x1, y1, x2, y2, 
                                  fill=color_fill, 
                                  outline="#000000",
                                  width=1)


def crear_matriz_imagen():
    """
    Crea la matriz que representa la imagen mostrada
    Basado en las coordenadas de la imagen adjunta
    """
    # Crear matriz 12x11 (filas x columnas) inicializada con None
    matriz = [[None for _ in range(11)] for _ in range(12)]

    # Definir los colores según la imagen
    # Fila 1: amarillo en columnas 3,4
    matriz[1][3] = "Amarillo"
    matriz[1][4] = "Amarillo"

    # Fila 2: amarillo en columnas 2,3,4,5
    matriz[2][2] = "Amarillo"
    matriz[2][3] = "Amarillo" 
    matriz[2][4] = "Amarillo"
    matriz[2][5] = "Amarillo"

    # Fila 3: amarillo y negro
    matriz[3][2] = "Amarillo"
    matriz[3][3] = "Negro"  # ojo izquierdo
    matriz[3][4] = "Amarillo"
    matriz[3][5] = "Amarillo"

    # Fila 4: naranja y amarillo
    matriz[4][1] = "Naranja"
    matriz[4][2] = "Naranja"
    matriz[4][3] = "Amarillo"
    matriz[4][4] = "Amarillo"
    matriz[4][5] = "Amarillo"

    # Fila 5: amarillo extendido
    # matriz[5][2] = "Amarillo"
    matriz[5][3] = "Amarillo"
    matriz[5][4] = "Amarillo"
    matriz[5][5] = "Amarillo"
    matriz[5][6] = "Amarillo"
    matriz[5][7] = "Amarillo"
    matriz[5][8] = "Amarillo"
    matriz[5][9] = "Amarillo"
    matriz[5][10] = "Amarillo"

    # Fila 6: amarillo con rojo
    matriz[6][2] = "Amarillo"
    matriz[6][3] = "Amarillo"
    matriz[6][4] = "Amarillo"
    matriz[6][5] = "Rojo"
    matriz[6][6] = "Amarillo"
    matriz[6][7] = "Amarillo"
    matriz[6][8] = "Rojo"
    matriz[6][9] = "Amarillo"
    # matriz[6][10] = "Amarillo"

    # Fila 7: amarillo con rojo
    matriz[7][2] = "Amarillo"
    matriz[7][3] = "Amarillo"
    matriz[7][4] = "Amarillo"
    matriz[7][5] = "Amarillo"
    matriz[7][6] = "Rojo"
    matriz[7][7] = "Rojo"
    matriz[7][8] = "Amarillo"
    matriz[7][9] = "Amarillo"

    # Fila 8: amarillo
    # matriz[8][2] = "Amarillo"
    matriz[8][3] = "Amarillo"
    matriz[8][4] = "Amarillo"
    matriz[8][5] = "Amarillo"
    matriz[8][6] = "Amarillo"
    matriz[8][7] = "Amarillo"
    matriz[8][8] = "Amarillo"

    # Fila 9: amarillo
    # matriz[9][3] = "Amarillo"
    matriz[9][4] = "Amarillo"
    matriz[9][5] = "Amarillo"
    matriz[9][6] = "Amarillo"
    matriz[9][7] = "Amarillo"

    # Fila 10: naranja
    matriz[10][5] = "Naranja"
    matriz[10][7] = "Naranja"

    # Fila 11: naranja
    matriz[11][4] = "Naranja"
    matriz[11][5] = "Naranja"
    matriz[11][6] = "Naranja"
    matriz[11][7] = "Naranja"

    return matriz


def crear_interfaz():
    """Crea la interfaz principal con Tkinter"""
    # Crear ventana principal
    root = tk.Tk()
    root.title("Pixel Art de pato - Actividad 6 clase 2")
    root.resizable(False, False)

    # Crear canvas
    canvas_width = 11 * 30  # 11 columnas * 30 píxeles
    canvas_height = 12 * 30  # 12 filas * 30 píxeles
    canvas = Canvas(root, width=canvas_width, height=canvas_height, bg="white")
    canvas.pack(padx=20, pady=20)

    # Crear matriz y dibujar
    matriz = crear_matriz_imagen()
    dibujar_pixel_art(canvas, matriz, 30)

    # Frame para botones
    frame_botones = tk.Frame(root)
    frame_botones.pack(pady=10)

    return root, canvas


def ejemplo_uso_personalizado():
    """
    Ejemplo de cómo usar la función con una matriz personalizada
    """
    # Matriz de ejemplo más simple (cara sonriente)
    matriz_simple = [
        [None, None, "Amarillo", "Amarillo", "Amarillo", None, None],
        [None, "Amarillo", "Amarillo", "Amarillo", "Amarillo", "Amarillo", None],
        ["Amarillo", "Negro", "Amarillo", "Amarillo", "Amarillo", "Negro", "Amarillo"],
        ["Amarillo", "Amarillo", "Amarillo", "Amarillo", "Amarillo", "Amarillo", "Amarillo"],
        ["Amarillo", "Rojo", "Rojo", "Rojo", "Rojo", "Rojo", "Amarillo"],
        [None, "Amarillo", "Amarillo", "Amarillo", "Amarillo", "Amarillo", None],
        [None, None, "Amarillo", "Amarillo", "Amarillo", None, None]
    ]

    # Crear ventana para ejemplo
    root_ejemplo = tk.Tk()
    root_ejemplo.title("Ejemplo - Cara Sonriente")
    canvas_ejemplo = Canvas(root_ejemplo, width=7*25, height=7*25, bg="white")
    canvas_ejemplo.pack(padx=10, pady=10)

    dibujar_pixel_art(canvas_ejemplo, matriz_simple, 25)

    return root_ejemplo


if __name__ == "__main__":
    # Ejecutar aplicación principal
    root, canvas = crear_interfaz()

    # Opcional: mostrar también el ejemplo
    # root_ejemplo = ejemplo_uso_personalizado()

    # Iniciar loop de eventos
    root.mainloop()
```