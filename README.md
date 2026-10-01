# El Dilema del Prisionero | Juego de Aprendizaje en 1 Minuto & Simulador 2D

Aplicación web interactiva que enseña los principios de la **Teoría de Juegos** y la evolución de la cooperación a través de un **juego rápido de aproximadamente 1 minuto** ambientado en una **videoconsola portátil tipo Nintendo Switch**, con Joy-Cons interactivos (Neon Blue y Neon Red), fondo negro, gráficos circulares y adaptación precisa a pantallas 720p y 1080p (sin scroll vertical con la barra de Windows visible), conservando además el **simulador espacial 2D toroidal** (con skins Minecraft y Dwarf Fortress) en su propio apartado dedicado.

> **Versión 1.1.0**: Renovación completa de la interfaz en formato videoconsola portátil Nintendo Switch con Joy-Cons interactivos, ajuste a 720p/1080p sin scroll y Switch OS.

---

## 🎮 1. Interfaz de Videoconsola Portátil Nintendo Switch (Por Defecto · ~1 Minuto)
Diseñada para que el jugador vea **todos los datos simultáneamente en pantalla sin hacer scroll**, replicando una consola portátil de Nintendo:
* **Chasis de Consola Portátil:**
  * **Joy-Con Izquierdo (Neon Blue):** Stick analógico con relieve, botón `[-]`, D-Pad direccional (▲/▼/◀/▶) para ciclar entre rivales y botón de captura.
  * **Pantalla Central LCD (16:9 Bezel):** Marco negro brillante con Switch OS (reloj en tiempo real, batería 100%, volumen y selector de modo pantalla completa `[ 🖥️ / 🎮 ]`).
  * **Joy-Con Derecho (Neon Red):** Clúster diamante interactivo con botones ABXY:
    * **[ Y ]**: 🤝 **COOPERAR** (Neon green)
    * **[ X ]**: 🗡️ **ENGAÑAR** (Neon red)
    * **[ A ]**: 🚀 **SIGUIENTE OPONENTE**
    * **[ B ]**: ↺ **REVANCHA**
    * Stick analógico, botón `[+]` y botón Home metálico.
* **Control Flexible:** Puedes jugar pulsando los botones táctiles gigantes en pantalla, usando los botones físicos de los Joy-Cons o con el teclado (`Y`/`C` para cooperar, `X`/`T` para engañar, flechas de dirección para rivales).
* **5 Arquetipos de IA Clásicos:**
  1. 🐱 **KOPY (Ojo por Ojo / Tit for Tat):** Amable y recíproco. Empieza cooperando y luego copia tu última jugada.
  2. 🦊 **SNEAKY (El Tramposo):** Siempre traiciona para intentar robarte todo.
  3. 🐶 **BUDDY (El Bondadoso):** Coopera incondicionalmente sin importar lo que hagas.
  4. 🐻 **GRUMPY (El Rencoroso):** Coopera hasta que le fallas una sola vez; luego nunca perdona.
  5. 🦉 **DETECTIVE (El Analista):** Te pone a prueba en las rondas iniciales para ver si te dejas explotar o si te defiendes.
* **Resultados & Conclusiones:** Al finalizar la ronda 5, presenta un gráfico donut circular comparativo, trofeo y una conclusión didáctica sobre qué estrategia funcionó y por qué.
* **Simulador de Torneo Evolutivo:** En la pestaña `[ 👥 TORNEO ]`, simula una liga de 100 rondas entre todas las estrategias con un gráfico de podio circular.

---

## 🔬 2. Simulador Espacial 2D (Minecraft & Dwarf Fortress)
Accesible en cualquier momento desde el botón superior **`[ 🔬 SIMULADOR 2D (MINECRAFT/ASCII) ]`**:
* **Espacio Toroidal 2D:** Cuadrícula de $60 \times 30$ celdas con vecindad de Moore de 8 vecinos bajo las reglas de Nowak & May (1992).
* **Skins Visuales Intercambiables:**
  * **⛏️ Minecraft (Voxel Pixel Art):** Texturas de Bloques de Césped, Esmeralda, TNT y Diamante en Canvas 2D acelerado.
  * **📜 Dwarf Fortress (ASCII Retro):** Terminal CRT con fuente monoespaciada, texto verde fósforo y scanlines.
  * *Atajo:* Presiona `[M]` para alternar de skin al instante.
* **Modos de Simulación Espacial:**
  * **Modo Tutorial:** 4 lecciones guiadas paso a paso con bitácora de análisis en vivo.
  * **Modo Laboratorio / Sandbox:** Simulación continua, sliders de la matriz de pagos en tiempo real, presets históricos y mutación genética.
  * **Modo Duelo Multijugador por Turnos:** Juego táctico local (2 a 4 jugadores) con Puntos de Acción (PA) y pulsos de caos.

---

## 🚀 Cómo Ejecutar
Abre `index.html` en cualquier navegador web moderno (Edge, Chrome, Firefox, Safari). No requiere instalación, librerías externas ni servidores locales.

---

## 📦 Control de Versiones con Git y Tig
El proyecto está versionado con Git y optimizado para explorarse mediante `tig`:
```bash
tig
```
Para más detalles sobre la arquitectura y formulación matemática, consulta [`CONTEXT.md`](./CONTEXT.md).
