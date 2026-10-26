Tabla de controles:
    IMC_Default - 
        Salto -  barra espaciadora y "boton frontal inferior del mando"
        Movimiento - WASD, flechas direccionales del teclado (arriba, abajo, izquierda, derecha) y joystick izquierdo
        Movimiento de la cámara (IA_Look) - Joystick derecho
        Interactuar - E

    IMC_MouseLook
        Movimiento de la cámara (IA_MouseLook) - Eje 2D XY del ratón

    IMC_Pinball
        Activar palanca izquierda (IA_Plipper_L) - flecha direccional izquierda
        Activar palanca derecha (IA_Plipper_R) - flecha direccional derecha
        Lanzar bola (IA_Launch) - flecha direccional arriba, barra espaciadora
        Salir - ESC


Valores físicos de la bola y material físico:

    - Bola (`BP Ball`, componente `SphereCollision`)
        - Radio de colisión | 0,5 cm (1 cm de diámetro)
        - Simulate Physics: true 
        - Enable Gravity: true
        - Masa (override): 0,1 kg
        - Linear Damping: 0,01
        - Angular Damping: 0
        - CCD: true
        - Perfil de colisión: PhysicsActor
        - Simulation Generates Hit Events: true

    - Material
        - Friction: 0,05
        - Static Friction: 0
        - Restitution 0,75
        - Density: 1 g/cm³
        - Friction Combine Mode: Average
        - Restitution Combine Mode: Average

Mejoras implementadas:
- Uso de interfaces para añadir elementos interactuables. Cuando el jugador se acerca a un elemento interactuable, aparecerá un mensaje en pantalla que indica que puede interactuar con él.
- Se puede interactuar con el pinball para controlarlo. Mientras el jugador controla el pinball, puede dejar de controlarlo pulsando ESC.
- Se han añadido SFX para cuando la bola rebota y cuando ésta cae.
- Se ha añadido un contador de vidas. El jugador tiene 3 vidas, cada una de las cuales le permite lanzar una bola. Si se acaban todas las vidas, se reinicia la puntuación y vuelve a tener 3 vidas.

IMPORTANTE: Para usar ESC, es necesario modificar los atajos de teclado, ya que normalmente ESC está asignado por defecto a detener la simulación del proyecto en Unreal Engine. Para ello, hay que ir a "Editar>Atajos de teclado" o pulsar Ctrl+Alt+K y modificar "Mundo de juego (PIE/SIE) > Detener"