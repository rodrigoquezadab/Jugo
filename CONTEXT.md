# CONTEXTO DEL PROYECTO: DILEMA DEL PRISIONERO EVOLUTIVO 2D (TOROIDAL)

## 1. Visión General
Este proyecto es una aplicación web interactiva en un solo archivo plano (`index.html`) que implementa una simulación de **Teoría de Juegos Evolutiva Espacial** y **Autómatas Celulares**: el **Dilema del Prisionero Iterado en un Espacio Bidimensional Toroidal**.

Presenta una arquitectura híbrida con soporte completo para:
1. **Skins Visuales Intercambiables:**
   * **Skin Dwarf Fortress / ASCII Retro:** Terminal CRT con fuente monoespaciada, texto verde fósforo (`#33ff33`), líneas de escaneo y renderizado en bloque `<pre>`.
   * **Skin Minecraft / Voxel Pixel Art:** Texturas procedurales de 16x16 píxeles (Césped, Bloque de Esmeralda, Bloque de TNT, Bloque de Diamante) renderizadas en un `<canvas>` 2D acelerado, con interfaz de piedra labrada y botones biselados de Minecraft.
2. **Modo Laboratorio / Sandbox:** Simulación continua, ejecución paso a paso, presets históricos y modificación interactiva de la matriz de pagos y parámetros biológicos.
3. **Modo Duelo Multijugador por Turnos:** Competencia táctica local (*Hot-seat*) para 2 a 4 jugadores por turnos, con sistema de Puntos de Acción (PA), facciones, combate evolutivo y registro de combate en tiempo real.

---

## 2. Pila Tecnológica & Arquitectura
* **HTML5 Estándar:** Estructura semántica sin dependencias externas ni frameworks pesados.
* **CSS3 Embebido Dual:**
  * Modo Terminal: Fondo `#050805`, verde fósforo `#33ff33`, scanlines CRT y bordes discontinuos tipo caja ASCII.
  * Modo Minecraft: Fondo texturizado bedrock/piedra, botones con bisel 3D pixelado (`#4a423a`), sombras duras y renderizado de píxeles nítidos (`image-rendering: pixelated`).
* **JavaScript ES6 Modular & Motor Gráfico Dual:**
  * **Optimización de Rendimiento:** Uso de `Uint8Array` y `Float32Array` para almacenar estrategias, facciones y fitness.
  * **Double Buffering:** Matrices dobles (`currentGrid`, `nextGrid`, `ownerGrid`, `nextOwnerGrid`) para transiciones libres de efectos de borde y sin recolección de basura (*GC thrashing*), garantizando 60 FPS estables.
  * **Renderizador Dual:** Alternancia instantánea y reactiva entre un viewport `<pre>` (Dwarf Fortress) y un `<canvas>` de $960 \times 480$ px (Minecraft) manteniendo el estado exacto de la simulación.

---

## 3. Fundamento Matemático y Reglas de Teoría de Juegos

### A. Matriz de Pagos Canónica ($2 \times 2$)
Cumple estrictamente con la desigualdad canónica del Dilema del Prisionero:
$$T > R > P > S \quad \text{y} \quad 2R > T + S$$
* **$T$ (Temptation / Éxito del Traidor):** 5.0 pts (Traidor vs Cooperador)
* **$R$ (Reward / Cooperación Mutua):** 3.0 pts (Cooperador vs Cooperador)
* **$P$ (Punishment / Traición Mutua):** 1.0 pt (Traidor vs Traidor)
* **$S$ (Sucker's Payoff / Pérdida del Estafado):** 0.0 pts (Cooperador vs Traidor)

Todos los valores son ajustables dinámicamente en tiempo real mediante sliders.

### B. Geometría Toroidal & Vecindad de Moore
* La cuadrícula tiene dimensiones $W = 60$, $H = 30$ ($1800$ celdas interactivas).
* Condiciones periódicas de frontera (*Efecto Pac-Man*):
  $$x' = (x + dx + W) \pmod W$$
  $$y' = (y + dy + H) \pmod H$$
  donde $dx, dy \in \{-1, 0, 1\} \setminus \{(0,0)\}$ (8 vecinos adyacentes de Moore).

### C. Estrategias Modeladas y Equivalencias en Skins
| Estrategia | Token DF (ASCII) | Bloque Minecraft | Comportamiento en el Dilema |
| :--- | :--- | :--- | :--- |
| **Cooperador Puro** | `'C'` (Verde Fósforo) | **Bloque de Esmeralda** | Coopera incondicionalmente; genera alta sinergia en grupos cerrados. |
| **Traidor Puro** | `'T'` (Rojo Carmesí) | **Bloque de TNT** | Explota cooperadores ajenos; destructivo frente a otros traidores ($P = 1.0$). |
| **Imitador (TFT)** | `'I'` (Cian Eléctrico) | **Bloque de Diamante** | Coopera inicialmente; replica de inmediato la traición si el rival traicionó. |
| **Terreno Vacío** | `'.'` (Verde Atenuado) | **Bloque de Césped / Tierra** | Espacio no reclamado; colonizable por vecinos de alto fitness. |

### D. Algoritmo de Dos Fases por Generación
1. **Fase de Juego:** Cada agente activo disputa 8 partidas simultáneas contra sus vecinos reales de Moore. Su puntuación acumulada se almacena en `fitnessGrid`.
2. **Fase Evolutiva (*Spatial Best-Takes-All* Nowak & May 1992):**
   * **Celdas Ocupadas:** Evalúan su puntuación propia y la de sus 8 vecinos. La celda adopta la estrategia del agente con mayor fitness. Si hay empate, se resuelve estocásticamente.
   * **Celdas Vacías:** Tienen una probabilidad $\kappa$ (colonización) de ser colonizadas por la estrategia vecina más exitosa.
   * **Mutación Genética:** Con probabilidad $\mu$ ($0\% - 10\%$), cualquier celda muta aleatoriamente en $C, T$ o $I$.

---

## 4. Modo Duelo Multijugador por Turnos (*Hot-Seat*)

### A. Facciones Disponibles (Mínimo 2, hasta 4 Jugadores)
* **Jugador 1 [ALPHA]:** Token / Borde Cian Neón (`#00ffff`).
* **Jugador 2 [OMEGA]:** Token / Borde Ámbar Dorado (`#ffaa00`).
* **Jugador 3 [GAMMA]:** Token / Borde Amatista (`#d946ef`).
* **Jugador 4 [DELTA]:** Token / Borde Cuarzo / Blanco (`#f1f5f9`).

### B. Sistema de Puntos de Acción (PA)
Cada jugador dispone de una reserva fija de PA por turno (ajustable de 3 a 10 PA, por defecto 5 PA):
* **Desplegar Cooperador (`C` / Esmeralda) [1 PA]:** Construcción de economías cooperativas densas.
* **Desplegar Traidor (`T` / TNT) [1 PA]:** Misil táctico de infiltración en territorio enemigo.
* **Desplegar Imitador (`I` / Diamante) [1 PA]:** Centinela fronterizo *Tit for Tat*.
* **Pulso de Caos (`💥`) [2 PA]:** Bomba táctica que limpia un área de $3 \times 3$ neutralizando células enemigas.

### C. Ciclo del Turno y Resolución
1. **Turno de P1:** Distribuye sus PA y presiona `[ FINALIZAR TURNO P1 ]` (o tecla `Espacio`).
2. **Turno de P2 (y P3/P4):** El banner táctico y los controles se actualizan para el siguiente jugador.
3. **Resolución de Batalla Evolutiva:** Una vez que todos completan su turno, el motor ejecuta $N$ épocas evolutivas del Dilema del Prisionero. Las células rivales combaten y el mayor fitness transfiere la **lealtad territorial** a la facción vencedora.
4. **Registro de Combate (Log ASCII):** Reporta en vivo celdas conquistadas, puntos obtenidos y eventos de sabotaje.
5. **Victoria:** Al alcanzar el límite de rondas (ej. 15) o por aniquilación del adversario, se corona al ganador con un trofeo en arte ASCII.

---

## 5. Control de Versiones con Git y Tig

El proyecto cuenta con un repositorio Git local configurado y compatibilidad directa con **`tig`** (la interfaz de modo texto basada en ncurses para Git):

### Comandos de Utilidad:
* **Explorar el historial visualmente con Tig:**
  ```bash
  tig
  ```
* **Ver el estado del repositorio:**
  ```bash
  tig status
  ```
* **Comandos estándar de Git:**
  ```bash
  git status
  git log --oneline --graph --decorate
  git diff
  ```

---

## 6. Atajos de Teclado
* `[Espacio]`: Play / Pausar en Sandbox, o Finalizar Turno en Multijugador.
* `[M]`: Alternar instantáneamente entre Skin **Dwarf Fortress** y Skin **Minecraft**.
* `[N]`: Avanzar un solo paso / generación evolutiva.
* `[R]`: Reiniciar con mapa aleatorio o nueva partida.
* `[C]`: Limpiar cuadrícula a terreno vacío.
