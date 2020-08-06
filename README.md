
# Godot

Este repositorio contiene pequeñas demos jugables diseñadas con la intención de ser fáciles de aprender y enseñar. Los proyectos has sido creadas con el motor **Godot Engine** (versión 3.2), y usando otros recursos libres.

1. [Arkanoid](#arkanoid)
1. [Command](demos/command) (En construccion!)
1. [Platform](#platform)
1. [Platform-Top-Down](#platform-top-down)
1. [Roguelike](#roguelike)
1. [SpaceShooter](#spaceshooter)
1. [Tower Defense](demos/tower-defense) (En construcción!)

## [Arkanoid](demos/arkanoid)

![](docs/images/arkanoid.png)

* demos/arkanoid: Inspirado en los ejemplos y vídeos de Rafanoid.
* Se usa el motor de física en el movimiento de la pelota, aprovechando que todos los elementos del juego son cuerpos físicos: RigidBody2D(pelota), StaticBody2D(los muros), KinematicBody2D(player).
* Hay una ventana de menú inicial, y una ventana de pausa creadas con los elementos de GUI(Container, Label y Button).
* Futuro: añadir efecto de Particle2D a la pelota, aumentar el número de niveles, diseñar varios muros con diferentes comportamientos (Por ejemplo diferente resistencia).

## [Platform](demos/platform)

![](docs/images/platform.png)

* demos/platform: Juego de plataformas con gráficos de 16x16 y 1bit color, descargados de la página web de Kenney.
* El player es un KinematicBody2D con colisiones con el entorno. Las plataformas móviles también son KinematicBody2D.
* Los enemigos son Area2D.
* Para diseñar el mundo se ha usado TileMap y TileSet para crear un conjunto de celdas (tiles).
* Los actores están animados usando AnimatedSprite.
* Futuro: De momento sólo tenemos un nivel, pero la idea es crear más pantallas formando un mapa más complejo.
Se pueden coger unos objetos brillantes, pero por ahora no sirven para nada.

## [Platform (Top-Down)](demos/platform-top-down)

![](docs/images/platform-top-down.png)

* demos/platform-top-down: Es una demo que implementa la forma de juego plataformas pero con una vista top-down.
* Esto es, hay distintas alturas en el mapa del juego. Para subir se usan las escaleras o el salto. Para bajar se usan las escaleras, el salto o dejarse caer por el borde de un nivel.
* El player es un KinematicBody2D que inicialmente está en la capa 1 (altura 1). A medida que se sube se modifica el valor de la capa.
* Se usan las teclas WASD para el desplazamiento.
* Tenemos un TileMap(`map`) sin colisiones para hacer visible el mapa del juego.
* Para representar cada altura del mapa se usan los nodos dentro del `heights`. Donde `h1` representa el mapa de colisiones de la altura 1, `h2` el mapa de colisiones de la altura 2, etc.
* La lógica de funcionamiento del `player` se ha creado usando máquinas de estados. Donde tenemos los siguientes estados: `state/move`, `states/die` y `states/fall`.
* Futuro: implementar la función de salto en el estado `states/jump`.

## [Roguelike](demos/roguelike)

![](docs/images/roguelike.png)

* demos/roguelike: Un juego 2D de vista top-down, donde el player debe coger todas las llaves que abren la puerta para escapar del laberinto mientras esquivamos a los enemigos. Esta demo jugable puede ser adecuada para empezar a aprender.
* Para diseñar el mundo se ha usado TileMap y TileSet para crear un conjunto de celdas (tiles).
* Se usa el motor de física para controlar la colisiones. El player es un KinematicBody2D y los muros del laberinto StaticBody2D.
* Los enemigos son Area2D para poder detectar las colisiones. Además cada enemigo tiene un comportamiento diferente que se puede configurar.
* Ir a [explicación](docs/roguelike/README.md) para ver un pequeño resumen.
* Futuro: Crear ventanas de inicio y pausa.

## [SpaceShooter](demos/spaceshooter)

![](docs/images/spaceshooter.png)

* demos/spaceshooter: Shooter de scroll vertical. Los assets son imágenes de 16x16, hechas con Gimp y luego escaladas a 48x48 para resaltar el efecto de pixelado. Los assets no son muy elaborados. Son de creación propia, usando Gimp para el pixel art.
* Todos los objetos del juego son del tipo Area2D. Actualmente están definidos los siguientes elementos: Rocas (pequeñas y grandes), Satélites, Tie-figther y el X-Wing(Player).
* Efectos: tenemos efectos de explosiones creados con Particle2D, además se usa Timer y SelfModulate para el efecto flash cuando se recibe un impacto no letal.
* Hay dos ficheros Singleton: Global y Loader. Global para las variables globales del juego. Loader para contener las funciones de construcción del nivel. El diseño del nivel se hace en un fichero de texto (level/level2.txt) que Loader lee y construye.

## [Tower Defense](demos/tower-defense)

![](docs/images/tower-defense.png)
* demos/tower-defense: EN CONSTRUCCION. Los assets son de Aarón VJ, creados con Gimp.
* De momento sólo permite escoger entre 2 tipos de cartas, y colocar las piezas en la primera columna del tablero.
* Futuro: En construcción!

# Información sobre videojuegos y Godot

[Enlaces de interés, consejos y artículos relacionados.](docs/README.md)
