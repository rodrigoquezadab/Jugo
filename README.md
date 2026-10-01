# Dilema del Prisionero Iterado Evolutivo 2D (ASCII & Minecraft)

Simulador interactivo espacial de Teoría de Juegos y Autómatas Celulares en un espacio toroidal de $60 \times 30$ celdas con soporte dual de Skins visuales y modo multijugador por turnos.

## Skins Visuales
* **📜 Dwarf Fortress (ASCII Retro):** Terminal CRT con fuente monoespaciada, texto verde fósforo, scanlines y renderizado en texto preformateado `<pre>`.
* **⛏️ Minecraft (Voxel / Pixel Art):** Texturas procedurales de 16x16 píxeles (Bloques de Césped, Esmeralda, TNT y Diamante) en `<canvas>` 2D acelerado, con interfaz de piedra labrada y botones biselados clásicos de Minecraft.
* *Atajo rápido:* Presiona `[M]` en cualquier momento para alternar de skin al instante sin reiniciar la simulación.

## Modos de Juego
1. **🧪 Modo Laboratorio / Sandbox:** Simulación continua, control de parámetros en tiempo real, presets históricos y edición libre de la cuadrícula.
2. **⚔️ Modo Duelo Multijugador por Turnos:** Juego táctico local (2 a 4 jugadores) con Puntos de Acción (PA), facciones, pulsos de caos y batalla evolutiva.

## Cómo Ejecutar
Abre `index.html` en cualquier navegador web moderno. No requiere librerías externas ni servidores locales.

## Control de Versiones con Tig y Git
El proyecto está versionado con Git y configurado para usarse con `tig`:

```bash
tig
```
Para ver los fundamentos matemáticos y la arquitectura completa, consulta [`CONTEXT.md`](./CONTEXT.md).
