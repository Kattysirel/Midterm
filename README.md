# Midterm
Proyecto AES – Encriptado por Bloques
Descripción General

Este proyecto implementa una simulación del proceso de encriptado AES (Advanced Encryption Standard) por bloques de 4x4 bytes.
Cada integrante del grupo desarrolló una parte específica del proceso de cifrado, y todos los módulos se integraron en un solo programa.
El objetivo es comprender las transformaciones que sufre el estado en cada ronda del algoritmo.

Estructura del Encriptado AES
1. Primera Ronda

AddRoundKey
Se aplica la clave inicial al estado antes de cualquier otra transformación.
Se utiliza la operación XOR (⊕) entre la matriz del texto y la matriz de la clave.

2. Rondas Intermedias

SubBytes → ShiftRows → MixColumns → AddRoundKey

SubBytes: Sustituye cada byte por su valor correspondiente en la tabla S-box.

ShiftRows: Desplaza cada fila del estado hacia la izquierda según su índice.

MixColumns: Mezcla los valores de cada columna mediante multiplicaciones en el campo GF(2⁸).

AddRoundKey: Se aplica la subclave de la ronda al estado actual mediante XOR.

3. Última Ronda

SubBytes → ShiftRows → AddRoundKey

En esta ronda no se aplica MixColumns.

Estructura del Código

El código está compuesto por las siguientes partes:

SubBytes (Sustitución de bytes)

Usa una tabla S-box para reemplazar cada byte.

Convierte valores de hexadecimal a binario y luego aplica la sustitución.

ShiftRows (Desplazamiento de filas)

Desplaza cada fila i del estado i posiciones a la izquierda.

MixColumns (Mezcla de columnas)

Multiplica cada columna de la matriz por una matriz fija de coeficientes.

En este proyecto, las operaciones son multiplicaciones y sumas simples (sin módulo 256) para visualizar el proceso.

AddRoundKey (Adición de clave)

Aplica la clave mediante XOR entre la matriz del texto y la matriz de la clave.
