# Práctica 2: Guardar los números pares
## 1. Descripción del problema (Fase 1)
<!-- Explica con tus palabras qué hace tu programa y para qué serviría en la vida real. Máximo 4 líneas. --> El programa solicita cinco números enteros al usuario y guarda solo los que sean pares. Al final muestra cuántos números pares encontró y cuáles son. Puede servir para separar números pares de una lista de datos.

## 2. Entradas y salidas (Fase 1)
<!-- Define cada entrada y cada salida, con su tipo de dato y su objetivo. -->

**Entradas:**
1. 5 Números proporcionados por el usuario

**Salidas:**
1. Cantidad de números pares encontrados
2. Los números pares encontrados 

## 3. Restricciones e invariante (Fase 1 y 2)

**Restricciones** (¿qué debe cumplirse?):
- Que los números proporcionados sean exactamente 5
- Que sean números enteros  

**Tamaño del arreglo y por qué** (piensa en el peor caso):
Porque en el peor caso los cinco son pares

**¿El 0 y los negativos son pares? ¿Por qué?**
Porque su residuo al dividirlos entre dos es cero

**Invariante** (¿qué es verdad después de cada vuelta del ciclo?):
Después de cada vuelta del ciclo, el arreglo contiene los números pares encontrados hasta ese momento y el contador de pares indica cuántos se han guardado.

## 4. Casos resueltos a mano (Fase 1)

| Caso | Números | Pares guardados | Posición de cada par |
|---|---|---|---|
| 1 | 3, 8, 5, 2, 7 | 8, 2 | 0, 1 |
| 2 | 1, 3, 5, 7, 9 | 0 | Ninguna |
| 3 | 0, -3, -4, 7, 1 | 0, -4 | 0, 1 |

## 5. Receta en pseudocódigo (Fase 2)
<!-- Tu receta va en el archivo RECETA.md. Aquí solo responde las dos preguntas. -->

**¿Probé mi receta a mano con un caso?** Sí / No
**¿Tuve que corregirla?** _____

## 6. Cómo compilar y ejecutar (Fase 3)

```bash
g++ -Wall -Wextra -std=c++17 main.cpp -o numeros_pares
./numeros_pares
```

## 7. Ejemplo de ejecución (Fase 3)
<!-- Pega aquí lo que muestra tu programa en pantalla con un caso normal. -->

```
Guardar los números pares
Numero 1 de 5: 3
Numero 2 de 5: 8
Numero 3 de 5: 5
Numero 4 de 5: 2
Numero 5 de 5: 7
Cantidad de pares: 2
Numeros pares: 8 2
```

## 8. Experimentos (Fase 3)

**Experimento A: ¿qué apareció al imprimir las 5 posiciones del arreglo? ¿Por qué?**
Si se imprimen las cinco posiciones aunque se hayan encontrado menos de cinco pares, pueden aparecer valores que no son de los pares. Hay que mostrar solamente las posiciones que contienen pares, usando el contador
**Experimento B: ¿qué pasó al usar la variable del ciclo como posición del arreglo? ¿Por qué?**
El índice del arreglo debe avanzar solamente cuando se guarda un número par; por eso se necesita un contador independiente para los pares.

## 9. Tabla de pruebas (Fase 4)

| Caso | Números | Esperado | Obtenido | ¿Pasó? |
|---|---|---|---|---|
| Mezcla | 1, 2, 3, 4, 5 | 2 pares: 2, 4 | 2 pares: 2, 4 | Si |
| Posiciones distintas | 3, 8, 5, 2, 7 | 2 pares: 8, 2 | 2 pares: 8, 2 | si |
| Todos pares | 2, 4, 6, 8, 10 | 5  pares| 5  pares | si |
| Todos impares | 1, 3, 5, 7, 9 | 0 pares | 0 pares | si |
| Con cero y negativos | 0, -3, -4, 7, 1 | 2 pares: 0, -4 | 2 pares: 0, -4 | si |
| Entrada inválida | `hola` o `3.5` | vuelve a pedir | error | si |
| Caso propio 1 | 6, 1, 10, 3, 12 | 3 pares: 6, 10, 12 | 3 pares: 6, 10, 12 | si |
| Caso propio 2 | -2, -5, 0, 9, 11 | 2 pares: -2, 0 | 2 pares: -2, 0 | si |

## 10. Bitácora de mejoras (Fase 4)

| # | ¿Qué falló o qué quise mejorar? | ¿Qué cambié? | ¿Funcionó? |
|---|---|---|---|
| 1 | Mostrar posiciones vacias | usar el contador | si |
| 2 | No guardar impares | Comprobar que sea par | si |

**Reto elegido (opcional):** _____

## 11. Dudas para el profesor (Fase 3)

| Duda | Lo que ya intenté |
|---|---|
| _____ | _____ |

## 12. Reflexión final

**¿Qué aprendí con esta práctica?**
Arreglos que condicionan a los numeros

**Ahora que terminé, ¿qué cambiaría de mi proceso?**
Los errores que me marcaba

**¿Qué fue lo más difícil y cómo lo resolví?**
Usar el contador

**¿Qué pregunta me quedó sin responder?**
_____

**¿Por qué no puedo usar la variable del ciclo para guardar en el arreglo?**
Porque esa debe guardar los 5, no solo los pares

## 13. Lista de verificación antes de entregar (Fase 5)

- [ si] Llené todas las secciones (no quedan `_____`)
- [si] Mi programa compila sin advertencias
- [si] Probé todos los casos de la tabla
- [si] Hice los Experimentos A y B y dejé el código correcto al terminar
- [si] No modifiqué `utilerias.h`
- [si] Hice al menos 3 commits con mensajes claros
- [si] Hice `git push` y verifiqué mi fork en GitHub
- [si] Entregué el enlace de mi fork en Classroom