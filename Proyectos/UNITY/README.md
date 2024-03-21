# El Camino del Monje - Juego en Unity 2D

Este proyecto presenta "El Camino del Monje", mi primer juego en Unity en 2D inspirado en el famoso juego de Mario Bros. Desarrollado como proyecto final durante mi segundo año de SMX en el instituto Sa Palomera, este juego ofrece una experiencia emocionante llena de acción y desafíos, con el objetivo de derrotar al jefe final o llegar al check point para salvarte.

## Introducción

"El Camino del Monje" es una aventura de plataformas en la que asumes el papel de un valiente monje en busca de la paz interior. Tu misión es recorrer un mundo lleno de peligros, enfrentarte a enemigos desafiantes, recolectar gemas y derrotar al poderoso jefe final. No obstante, su camino para llegar al jefe final tendrás que ir derrotando a sus fieles secuaces, los cuales intentaran que no puedas llegar a la sala final. ¿¡Podrás llegar!?

## Funcionalidades

- **Animaciones de personaje:** Disfruta de animaciones de ataque, salto y carrera, todas ellas diseñadas para brindar una experiencia visualmente atractiva.
- **Variedad de Enemigos:** Enfréntate a tres tipos diferentes de enemigos, cada uno con sus propias animaciones y patrones de ataque únicos.
- **Recolección de Gemas:** Explora el mapa y recolecta gemas dispersas por todo el mapa.
- **Contador de Tiempo:** Supera el desafío del tiempo y completa el juego lo más rápido posible.
- **Boss Final:** Enfréntate a un jefe final, al final del mapa y demuestra tu valía como monje.
- **Checkpoint:** Encuentra el checkpoint en el centro del mapa para avanzar rápidamente y completar el juego de manera eficiente y rápida.

## Ejemplos de Juego

### Personaje principal
Utiliza tus habilidades de ataque para derrotar a los enemigos y defiéndete de sus ataques.


### Recolección de Gemas
Explora el mapa y recolecta gemas para desbloquear contenido adicional y mejorar tus habilidades.

### Variedad de Enemigos
Prepárate para el enfrentamiento final contra el jefe más poderoso del juego y demuestra tu valentía y destreza.

## Ejemplo de Código y Estructura

La estructura del proyecto sigue un diseño claro y organizado, con diferentes scripts para manejar las animaciones, la lógica del juego y la interacción del jugador. A continuación se muestra un ejemplo de código que maneja la animación de salto en C#:

```csharp
// Script para la animación de salto
public class JumpAnimation : MonoBehaviour
{
    private Animator animator;

    private void Start()
    {
        animator = GetComponent<Animator>();
    }

    public void Jump()
    {
        // Iniciar la animación de salto
        animator.SetTrigger("Jump");
    }
}
```
