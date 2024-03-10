# Buscaminas por Terminal

Este proyecto implementa el juego de Buscaminas en Java para ser ejecutado por la terminal.

## Introducción

El juego de Buscaminas es un clásico juego de mesa en el que el jugador debe descubrir todas las casillas que no contienen minas en un tablero. El objetivo es evitar las casillas con minas y marcarlas con banderas para evitar explotarlas.

## Funcionalidades

El juego de Buscaminas por terminal incluye las siguientes funcionalidades:

- Selección de diferentes opciones de dificultad al iniciar el juego.
- Posibilidad de descubrir una casilla.
- Colocación de banderas en las casillas sospechosas de contener minas.
- Salida del juego en cualquier momento.

## Ejemplos de Uso

### Seleccionar Dificultad
Al iniciar el juego, se presentará un menú para seleccionar la dificultad del juego: fácil, medio o difícil.

### Descubrir una Casilla
Para descubrir una casilla, se introduce la coordenada correspondiente y se presiona Enter. Si la casilla no contiene una mina, se mostrará el número de minas adyacentes. Si contiene una mina, el juego termina.

### Colocar una Bandera
Si se sospecha que una casilla contiene una mina, se puede colocar una bandera en ella. Para ello, se introduce la coordenada de la casilla y se coloca la bandera.

### Salir del Juego
En cualquier momento durante el juego, se puede salir del juego presionando la opción correspondiente en el menú.

## Ejemplo de Código

A continuación se muestra un ejemplo de cómo se podría implementar la funcionalidad para descubrir una casilla en Java:

```java
public void descubrirCasilla(int x, int y) {
    if (tablero[x][y].esMina()) {
        terminarJuego();
    } else {
        tablero[x][y].descubrir();
        // Lógica para mostrar número de minas adyacentes o expandir casillas vacías
    }
}
