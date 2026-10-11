# Revisión técnica y preparación del repositorio

Revisión realizada sobre la entrega recibida el 11 de octubre de 2026.

## Alcance

Se seleccionó `sketch_tpi/Algo1_TPI_1942`, la versión más completa incluida en el ZIP. El nivel superior `sketch_tpi` contiene una implementación más pequeña con archivos incompletos; no se mezclaron ambas versiones.

Se conservaron sin cambios los 29 archivos `.pde`, `sketch.properties`, los recursos utilizados y el CSV recibido. La preparación agrega documentación y reglas para ignorar archivos temporales.

Del paquete de publicación se omitieron las carpetas de historial Git y dos recursos sin referencias en los `.pde`: `data/agua.gif` y `data/fonts/Press_Start_2P.zip`. La fuente descomprimida y su licencia permanecen incluidas.

## Verificación realizada

- Comparación de los archivos incluidos contra la versión recibida.
- Comprobación de la coincidencia entre el nombre de la carpeta y el sketch principal.
- Revisión de las rutas de imágenes, animaciones, fuente y CSV utilizadas por el código.
- Comprobación de encabezados y filas del CSV.
- Comprobación de enlaces locales de la documentación y de la integridad del ZIP final.

**No se compiló ni se ejecutó el juego en Processing.** La revisión de código y recursos no sustituye una prueba de funcionamiento. Tampoco se verificó el balance o el comportamiento de una partida completa.

## Mejoras priorizadas

| Prioridad | Hallazgo | Próximo cambio sugerido |
|---|---|---|
| Alta | La versión del entorno y de las bibliotecas no está registrada. | Anotar las versiones de una instalación que ejecute el proyecto y probarla desde una descarga nueva. |
| Alta | `Partida` usa `table.getRowCount()` inmediatamente después de cargar el CSV. | Manejar archivo ausente o inválido e inicializar una tabla con todos sus encabezados. |
| Media | El menú muestra «2 jugadores», pero su opción no tiene implementación. | Ocultarla, marcarla como pendiente o desarrollar el modo. |
| Media | `K` permite avanzar y ganar; esos resultados se guardan normalmente. | Habilitar el atajo solo en modo de desarrollo y excluir esas partidas del ranking. |
| Media | La pantalla de estadísticas vuelve a cargar el CSV para cada métrica durante el dibujo. | Calcular al entrar o cambiar de filtro y reutilizar los resultados. |
| Media | `ALL` se admite como ID de jugador y como filtro global. | Reservar esa palabra para el filtro. |
| Baja | Se conserva `processing.video` aunque el fondo activo es una imagen. | Retirar el import y `movieEvent` juntos, y comprobar que el juego compila sin Video. |

## Prueba manual pendiente

1. Abrir el sketch con sus dos bibliotecas instaladas y comprobar que aparece el menú.
2. Elegir un jugador, ingresar tres letras, mover el avión y disparar.
3. Completar una derrota y revisar que se agregó exactamente una fila al CSV.
4. Revisar ranking, estadísticas globales y un filtro por jugador; volver al menú con `R`.
5. Recorrer los tres niveles y una victoria. El atajo `K` sirve para inspeccionar pantallas, pero no verifica el combate ni la progresión normal.
6. Probar una instalación nueva para confirmar que las instrucciones del README son suficientes.

## Presentación para un portfolio

El proyecto permite explicar programación orientada a objetos, interacción por eventos y persistencia de datos. Para describir el trabajo individual, completar qué clases o funcionalidades desarrolló cada integrante, qué problema resolvió y cómo comprobó su solución.

Una extensión posible orientada a Ciencia de Datos es un análisis separado del CSV en Python. Esa extensión todavía no forma parte de este proyecto.
