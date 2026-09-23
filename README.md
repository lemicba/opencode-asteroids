# Asteroids

Clon del clásico arcade **Asteroids** implementado en canvas HTML5 puro, sin dependencias ni bundler.

## Descripción

Nave espacial en un campo de asteroides con envolvimiento de bordes (el espacio es toroidal). Destruye asteroides para sumar puntos: los grandes se parten en medianos, los medianos en pequeños. Incluye power-ups de velocidad, de disparo triple y de escudo, y la estrella fugaz, un cometa que cruza la pantalla en línea recta a alta velocidad.

## Tecnologías

- **HTML5 Canvas** — renderizado 2D
- **JavaScript (ES6+)** — lógica del juego en un solo archivo `game.js`
- Sin frameworks, sin bundler, sin dependencias

## Cómo correr

Abre `index.html` directamente en el navegador (doble clic), o usa un servidor local:

```bash
npx serve .
```

Luego visita `http://localhost:3000`.

## Controles

| Tecla     | Acción                     |
| --------- | -------------------------- |
| `←` `→`   | Rotar nave                 |
| `↑`       | Propulsar                  |
| `Espacio` | Disparar                   |
| `S`       | Cambiar skin de la nave    |

## Puntuación

| Objeto         | Puntos |
| -------------- | ------ |
| Grande         | 20     |
| Mediano        | 50     |
| Pequeño        | 100    |
| Estrella fugaz | 500    |

## Características

- 3 vidas con invencibilidad temporal al reaparecer (parpadeo)
- Asteroides se parten en fragmentos más pequeños al ser destruidos
- Partículas de explosión al destruir asteroides
- Power-ups: los asteroides destruidos pueden soltar cápsulas de **velocidad** (empuje duplicado durante 5 s, en cian), de **disparo triple** (3 balas en abanico durante 5 s, en amarillo) o de **escudo** (anillo verde durante 6 s que destruye asteroides y estrellas fugaces que chocan contra la nave, sin perder vida)
- Estrella fugaz: cruza la pantalla periódicamente, suma 500 puntos al dispararle, no se parte en fragmentos y destruye la nave al chocar
- Skins de la nave: pulsá `S` para ciclar entre 4 diseños con silueta y color propios (Clásica, Cazador, Coloso y Espectro); la elección se guarda en el navegador y se recuerda entre sesiones
