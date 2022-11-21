# Examen parcial 

## Instrucciones
* El presente examen debe desarrollarse con los [conceptos de programación vistos en clase hasta la sesión anterior a este examen](https://github.com/mmasias/prg1-22-23/tree/main/temario).
* Se deben además respetar los conceptos de código limpio: indentación, nombrado adecuado de constantes, clase y variables.
* Para la entrega:
    1. Haga un fork de éste repositorio. 
    1. En su repositorio, dentro de la carpeta **entregas** cree una carpeta con su nombre y apellido en formato **apellidoNombre** (*ejemplo: masiasManuel*). 
    1. Publique allí su [código fuente](https://es.wikipedia.org/wiki/C%C3%B3digo_fuente) en formato compilable. 
    1. Al terminar, realice un pull request a este repositorio.

> **Muy importante:** no se corregirán entregas que obvien las reglas anteriormente indicadas o que se envíen fuera del plazo de entrega del examen.

# Carrera de camellos

En las ferias, se desarrollan entre otros divertimentos, un juego de carrera de camellos, que básicamente consiste en un camello "controlado" por el jugador, el cual va avanzando según se acierte a embocar una pelota en un agujero.

<div align="center">

|Carrera
|-
|![](./images/ShimmeringTinyArrowana-size_restricted.gif)

</div>

## Reto base

Desarrolle un programa que simule esta carrera, atendiendo las siguientes reglas:

1. En cada turno, el jugador elige un agujero al cual lanzar la pelota.
1. En función a tabla indicaba debajo, se calcula la probabilidad de acierto. Si el jugador acierta, avanza el número de casillas indicado. 
1. El jugador inicia en la casilla 0
1. El juego termina cuando el jugador llega a la casilla 60
1. El juego lleva un conteo del número de turnos empleado

<div align="center">

|Agujero|Probabilidad de acierto|Avance del Caballo
|-|-|-
|1|60%|1
|2|40%|2
|3|30%|4
|4|10%|6

</div>

### Jugador al inicio
```
---+-----------+---------+---------+---------+---------+-----------+
---| 0.........1.........2.........3.........4.........5.........6 |
---| 0123456789012345678901234567890123456789012345678901234567890 |
---+-----------+---------+---------+---------+---------+-----------+
[J] ;--;'
---+-----------+---------+---------+---------+---------+-----------+
Turno 0
Elija un agujero: 
```
### Jugador en la posición 27
```
---+-----------+---------+---------+---------+---------+-----------+
---| 0.........1.........2.........3.........4.........5.........6 |
---| 0123456789012345678901234567890123456789012345678901234567890 |
---+-----------+---------+---------+---------+---------+-----------+
[J]                             ;--;'
---+-----------+---------+---------+---------+---------+-----------+
Turno 12 - Avanza 3 casillas - Esta en la casilla 27
Elija un agujero: 
```

### Jugador al final
```
---+-----------+---------+---------+---------+---------+-----------+
---| 0.........1.........2.........3.........4.........5.........6 |
---| 0123456789012345678901234567890123456789012345678901234567890 |
---+-----------+---------+---------+---------+---------+-----------+
[J]                                                              ;--;'
---+-----------+---------+---------+---------+---------+-----------+
Turno 12 - Avanza 2 casillas - Esta en la casilla 60
El juego ha terminado
```

## Reto extendido

- Extienda el juego para que controle los aciertos del jugador: si el jugador no acierta tres veces seguidas, vuelve a la posición cero. 

## Reto ampliado

Amplíe el juego para que intervenga otro caballo gobernado por el ordenador. El caballo del ordenador puede moverse aleatoriamente 1, 2 o 3 casillas por turno.

### Jugador en la posición 27, ordenador en la posición 25
```
---+-----------+---------+---------+---------+---------+-----------+
---| 0.........1.........2.........3.........4.........5.........6 |
---| 0123456789012345678901234567890123456789012345678901234567890 |
---+-----------+---------+---------+---------+---------+-----------+
[J]                             ;--;'
---+-----------+---------+---------+---------+---------+-----------+
[O]                           ;--;'
---+-----------+---------+---------+---------+---------+-----------+
Turno 12 - Avanza 2 casillas - Esta en la casilla 27
El ordenador avanza 3 casillas - Esta en la casilla 25
Elija un agujero:
```
