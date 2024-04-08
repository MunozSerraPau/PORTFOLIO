# Buscaminas por Terminal

Este proyecto implementa el classico juego de Buscaminas en Java para ser ejecutado por la terminal con diferentes opciones de juego.

## Introducción

El juego de Busca Minas es un clásico juego de mesa en el que el jugador debe descubrir todas las casillas que no contienen minas en un tablero. El objetivo es evitar las casillas con minas y marcarlas con banderas para evitar explotarlas. Con la finalidad de marcar con banderas todas y cada una de las casillas que creas que contiene una bomba, a demás de destapar todas las casillas buenas.

## Funcionalidades

El juego de Buscaminas por terminal incluye las siguientes funcionalidades:
- Selección de diferentes opciones de dificultad al iniciar el juego.
- Posibilidad de descubrir una casilla.
- Colocación de banderas en las casillas sospechosas de contener minas.
- Salida del juego en cualquier momento.

## Ejemplos de Uso

### Seleccionar Dificultad
Al iniciar el juego, se presentará un menú para seleccionar la dificultad del juego: muy fácil, fácil, medio y difícil.

<img src="https://github.com/MunozSerraPau/PORTFOLIO/blob/main/Proyectos/JAVA/Proyecto1/menuDificutad.png?raw=true" alt="Menú de dificultat para el Busca Minas" width="500" />

### Descubrir una Casilla
Para descubrir una casilla, se introduce la coordenada correspondiente y se presiona Enter. Si la casilla no contiene una mina, se mostrará el número de minas adyacentes. Si contiene una mina, el juego termina. Como ultima opción, si es un espacio vacío de forma recursiva se mostrará todas las casillas del alrededor.

<img src="https://github.com/MunozSerraPau/PORTFOLIO/blob/main/Proyectos/JAVA/Proyecto1/trepitjarRecursividad.png?raw=true" alt="Ejemplo de descubrir una casilla" width="750" />

### Colocar una Bandera
Si se sospecha que una casilla contiene una mina, se puede colocar una bandera en ella. Para ello, se introduce la coordenada de la casilla y se coloca la bandera, si anteriormente ya está descubierta no podrás poner una bandera, pero, por el contrario, sí que puedes quitar una bandera poniendo de nuevo las coordenadas.

<img src="https://github.com/MunozSerraPau/PORTFOLIO/blob/main/Proyectos/JAVA/Proyecto1/AssiganrBandera.png?raw=true" alt="Ejemplo de colocar uan bandera" width="750" />

### Salir del Juego
En cualquier momento durante el juego, se puede salir del juego presionando la opción correspondiente en el menú.

<img src="https://github.com/MunozSerraPau/PORTFOLIO/blob/main/Proyectos/JAVA/Proyecto1/Exit.png?raw=true" alt="Como salir del juego" width="500" />

## Ejemplo de Código i estructura
La estructura que hemos seguido para poder crear el Busca minas a sigo la siguiente teniendo un total de 4 clases:

<img src="https://github.com/MunozSerraPau/PORTFOLIO/blob/main/Proyectos/JAVA/Proyecto1/EstructuraPrograma.png?raw=true" alt="Estructura del codigo" width="250" />

A continuación se muestra un ejemplo del código que tiene la funcionalidad para descubrir una casilla en Java:
```java
     /**
     Trepitgem la casella seleccionada, depèn d'on caiguis s'acaba el joc, es mostra una sola casella o es
     * mostra una part de caselles al voltant.
     * @param fil El número de fila que hem seleccionat
     * @param colum El número de columna que hem seleccionat
     * @return El camp visible del jugador amb l'array actualitzada segons el que has trepitjat
     */
    public static char[][] trepitjar (int fil, int colum) {
        // Comprovem si NO esta destapada, si ho esta saltem i no passa res
        if (campJugador[fil][colum] == '·') {
            // Ara comprovem si has trepitjat una bomba
            if (campSolucio[fil][colum] == 'B') {
                // Enviem un missatge conforme has perdut
                System.out.println("Has trepitjat una bomba!");
                // Un altre missatge per mostrar-li la solució
                System.out.println("AQUI LA SOLUCIÓ:");
                // Ensenyem l'array solució amb aquesta funció
                Vista.mostrar_camp_mines(campSolucio, files, columnes);
                // Sortim del programa
                System.exit(1);
            } else if (campSolucio[fil][colum] == ' ') {    // Ara comprovem si has trepitjat un espai
                // Primer de tot copiem l'espai al campJugador que és elq ue veu el jugador.
                campJugador[fil][colum] = campSolucio[fil][colum];
                // Ara com ha detectat un espai iniciem la funció per veure que té al voltant
                comprobarEspais(fil, colum);
            }else {     // Ara copiem le contingut del camp solució al de Jugadors
                campJugador[fil][colum] = campSolucio[fil][colum];
            }
        }
        // Retornem el camp Jugador
        return campJugador;

    }
```

Y su forma recursiva para comprobar los espacios alrededor:
```java
    /**
     * Fem la comprovació de tot el voltant de la casella que havíem seleccionat
     * @param fila És la fila que volem fer la comprovació perquè té un espai
     * @param columna És la columna que volem fer la comprovació perquè té un espai
     */
    private static void comprobarEspais (int fila, int columna) {
        // Fem la comprovació de tot el voltant de la casella
        trepitjar(fila-1,columna-1);
        trepitjar(fila-1,columna);
        trepitjar(fila-1,columna+1);

        trepitjar(fila,columna-1);
        trepitjar(fila,columna+1);

        trepitjar(fila+1,columna-1);
        trepitjar(fila+1,columna);
        trepitjar(fila+1,columna+1);
    }
```
