# CONTEXTO DEL PROYECTO: EL DILEMA DEL PRISIONERO (APRENDIZAJE EN 1 MINUTO & SIMULADOR ESPACIAL 2D)

## 1. Visión General
Este proyecto es una aplicación web interactiva en un solo archivo plano (`index.html`) construida con tecnologías web estándar (HTML5, CSS3, ES6 nativo, Web Audio API y Canvas 2D) estructurada en dos experiencias complementarias.

> **Versión del Proyecto:** `1.0.0` (Primera Versión Estable)

1. **Juego de Aprendizaje en 1 Minuto (Modo Principal por Defecto):**
   * **Estética Nintendo Moderna:** Fondo negro puro (`#07080c`) con iluminaciones circulares difusas, tipografías redondeadas ('Fredoka' y 'Outfit'), botones 3D ultra-táctiles y jugosos.
   * **Gráficos Circulares:** Avatares circulares SVG expresivos con gestos animados, anillo circular SVG para progreso de ronda y tiempo, matriz de pagos en flor circular de 4 cuadrantes, y donut charts de porcentaje y podio.
   * **Ritmo Ágil de 1 Minuto:** Partidas rápidas de 5 rondas (~10-12s por ronda, ~60s totales) contra 5 arquetipos clásicos de IA (Kopy, Sneaky, Buddy, Grumpy y Detective) con decisiones sencillas (🤝 COOPERAR vs 🗡️ ENGAÑAR), efectos de monedas flotantes, sonido de sintetizador retro sintetizado con Web Audio API y lecciones didácticas personalizadas al finalizar.
   * **Simulador de Torneo Evolutivo:** Módulo que ejecuta una liga redonda de 100 rondas entre todos los personajes y demuestra gráficamente por qué la cooperación recíproca triunfa sobre la traición en la evolución.

2. **Apartado Dedicado: Simulador Espacial 2D Toroidal (Minecraft & Dwarf Fortress):**
   * Preservado íntegramente y accesible mediante el botón superior **`[ 🔬 SIMULADOR 2D (MINECRAFT/ASCII) ]`**.
   * Autómata celular toroidal $60 \times 30$ con vecindad de Moore (8 vecinos) y reglas de Nowak & May (1992).
   * Skins intercambiables: Pixel Art Minecraft en Canvas 2D y Terminal CRT ASCII retro Dwarf Fortress en bloque `<pre>` (atajo `[M]`).
   * Tres modalidades: Tutorial guiado en 4 lecciones, Laboratorio Sandbox con sliders en tiempo real y Modo Duelo Multijugador por turnos (2-4 jugadores).

---

## 2. Pila Tecnológica & Arquitectura
* **HTML5 Estándar:** Arquitectura de archivo plano sin dependencias externas obligatorias ni bundlers.
* **CSS3 Embebido Multi-Tema:**
  * Tema Nintendo Dark: `#07080c`, componentes con bordes circulares (`border-radius: 50%` y `999px`), elevaciones 3D (`box-shadow`), gradientes de alto contraste y animaciones de rebote elásticas.
  * Tema Terminal ASCII: Verde fósforo `#33ff33`, scanlines CRT y caja monoespaciada.
  * Tema Minecraft: Piedra labrada, biseles pixelados y renderizado pixelado `image-rendering: pixelated`.
* **Audio Nativo Web Audio API:** Generación procedural de tonos sinusoidales, triangulares y diente de sierra para monedas, clics y fanfarrias sin archivos externos.
* **JavaScript ES6 Modular:**
  * Motor Nintendo de 1 minuto: ciclo de turnos, máquinas de estado de los oponentes, cálculo de recompensas, renderizado de gráficos circulares SVG y lecciones reflexivas.
  * Motor Espacial 2D: matrices `Uint8Array` y `Float32Array` con *double buffering* para 60 FPS estables.

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
