# Datos de las partidas

Archivo: `Algo1_TPI_1942/data/data.csv`.

**Unidad de registro:** una partida finalizada. El archivo recibido incluye 14 registros; su origen como partidas reales o datos de demostración no está documentado.

| Columna | Contenido |
|---|---|
| `id` | Identificador calculado a partir de la cantidad de filas al iniciar la partida. |
| `puntaje` | Puntaje acumulado. |
| `tiempo` | Duración en milisegundos. |
| `enemigos derrotados` | Total de enemigos derrotados. |
| `enemigos rojos derrotados` | Cantidad de enemigos rojos derrotados. |
| `enemigos verdes derrotados` | Cantidad de enemigos verdes derrotados. |
| `precision disparo` | Impactos registrados / proyectiles disparados × 100; cero si no se disparó. |
| `player_id` | Identificador de tres letras ingresado en el menú. |
| `win` | `1` para victoria; `0` para derrota. |

El CSV original tiene una columna final sin nombre, producto de una coma al final de cada fila. Se conservó para no alterar los datos de la entrega; puede normalizarse en una mejora posterior.

## Cálculos

- El filtro `ALL` toma todas las partidas; cualquier otro ID selecciona las de ese jugador.
- Media: suma de valores dividida por la cantidad de partidas seleccionadas.
- Desvío estándar muestral: raíz de la suma de desviaciones cuadráticas dividida por `n − 1`; el código devuelve cero cuando hay menos de dos partidas.
- Porcentaje de victorias: cantidad de victorias / cantidad de partidas × 100.
- Ranking: primeras diez partidas al ordenar por puntaje descendente.

`ALL` también puede escribirse como ID de jugador en el menú actual. Conviene reservarlo exclusivamente para el filtro global en una mejora posterior.

## Persistencia

El juego modifica este CSV al terminar las partidas. Antes de publicar nuevos cambios, revisá si querés conservar los resultados de tus pruebas. Mantené el archivo y sus encabezados: la inicialización de `Partida` espera encontrar una tabla válida.
