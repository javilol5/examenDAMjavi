# Examen de Programación: Sistema de Puntuación de Golf

## Descripción

Desarrolla una app en Java para calcular las puntuaciones de un partido de golf siguiendo las modalidades _Stroke Play_ y _Stableford_. El sistema debe procesar los golpes realizados por varios jugadores en un recorrido de 18 hoyos y calcular sus puntuaciones según ambas modalidades.

![Golf Score Card](../../examen_java/doc/golf-scorecard-ringway.png)

## Clases proporcionadas

Se proporcionan dos clases base para el desarrollo:

### `App.java`
Contiene el programa principal con ejemplos de uso del sistema, incluyendo:
- Creación de jugadores y sus recorridos
- Ejemplos de puntuaciones en ambas modalidades
- Salida esperada del programa

### `Course.java`
Clase que gestiona el campo de golf y los recorridos de los jugadores, proporcionando:
- Almacenamiento de golpes por jugador y hoyo
- Métodos para añadir y recuperar recorridos de jugadores


## Dependencias

Has de incluir la dependancia a Google Guava en tu proyecto.

Consulta la referencia de la librería para saber cómo añadirla:

[https://github.com/google/guava](https://github.com/google/guava)


## Requisitos

1. **Gestión de Jugadores**
    - Implementa una clase `Player` que almacene:
        - Iniciales del jugador.
        - Hándicap.
        - Puntuación total.
        - Puntos Stableford.

2. **Tarjeta de Puntuación**
    - Implementa una clase `ScoreCard` que gestione:
        - Hasta 4 jugadores (A, B, C, D), **opcionales**.
        - Colección de hoyos con su par correspondiente.
        - Referencia al campo (de tipo `Course`)

3. **Modalidades de Juego**
    - Implementa el patrón _Strategy_ para las dos modalidades de puntuación:
        - **Stroke Play**: suma total de golpes del recorrido de un jugador/a.
        - **Stableford**: puntos según la diferencia con el par del hoyo. Compara el número de golpes del jugador/a en cada hoyo con el par del hoyo para averiguar la categoría obtenida en ese hoyo. La categoría indica los puntos a sumar o restar al total del jugador según esta equivalencia:
            * _Double Bogey_ (2 o más sobre par): -3 puntos
            * _Bogey_ (1 sobre par): -1 punto
            * _Par_: 0 puntos
            * _Birdie_ (1 bajo par): +2 puntos
            * _Eagle_ (2 bajo par): +5 puntos
            * _Albatross_ (3 bajo par): +8 puntos
    - Crea la interfaz `GolfPlay` para implementar la estrategia o modalidad de juego (_Stroke Play_ o _Stableford_).
    - La clase `ComputeCard` aplica la estrategia /modalidad de juego seleccionada.

4. **Hoyo**
    - Implementa una clase `Hole` que representa un hoyo con su número en el circuito y su par.

5. **Requisitos de Implementación**
    - Usa el patrón _Strategy_ para las modalidades de juego.
    - Implementa los principios Open/Closed y SRP.
    - Utiliza `Optional` para la gestión de jugadores en `ScoreCard`.
    - Puedes hacer uso de `Streams` para el procesamiento de datos.
    - Implementa un **tipo enumerado** para el sistema _Stableford_.

## Ejemplo de Uso

Salida por consola

![Salida CLI](../../examen_java/doc/CLI_01.png)
![Salida CLI](../../examen_java/doc/CLI_02.png)



## Diagrama de clases UML / Arquitectura de la app.

Utiliza el patrón _Strategy_ para estructurar la aplicación.

Consulta su diseño en el libro sobre patrones de software proporcionado en la bibliografía del curso.


## Evaluación

Se valorará:
1. Correcta implementación del patrón _Strategy_.
2. Uso adecuado de `Optional` y `Streams`.
3. Uso del tipo de colección Java adecuado.
3. Implementación de un tipo enumerado para el sistema _Stableford_.
4. Implementación de los principios Open/Closed y SRP.
5. Implementación de pruebas unitarias.


## Prepara el proyecto

1. Crea un nuevo repo PRIVADO en tu cuenta en **Github** y compártelo con el usuario dfleta.
2. Crea un nuevo directorio en tu equipo y **clona el repositorio** de Github.
3. Abre VSCode /Eclipse /Netbeans /IntelIJ y **establece como workspace** el directorio que has clonado.
4. Crea un proyecto **Gradle** o **Maven**.
5. Pon el proyecto en seguimiento en **Git** y configura `.gitignore`.
6. Copia y pega la función principal `App.java`. Utilízala como guía en el proceso TDD. Comenta aquellas partes que no hayas implementado.
7. Completa las clases que aquí se indican **implementando los casos test que necesites**. Practica **TDD**.
8. **Realiza `commits` como mínimo cada vez que termines una historia de usuario**. Sin commit periódicos, no corrijo el examen.


## Entrega

1. Crea un repo PRIVADO en tu GitHub y compártelo con el usuario dfleta.
2. **Realiza commits periódicamente** mientras avanzas en el desarrollo de la aplicación. Sin commit periódicos, no corrijo el examen.
3. Realiza un `push` al repo remoto en GitHub **SÓLO cuando hayas terminado el proyecto**.