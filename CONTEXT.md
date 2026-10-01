# CONTEXTO DEL PROYECTO: EL DILEMA DEL PRISIONERO (CRÓNICAS DE LA CONFIANZA 1P & SIMULADOR ESPACIAL 2D)

## 1. Visión General
Este proyecto es una aplicación web interactiva en un solo archivo plano (`index.html`) construida con tecnologías web estándar (HTML5, CSS3, ES6 nativo, Web Audio API y Canvas 2D) estructurada en dos experiencias complementarias.

> **Versión del Proyecto:** `1.8.0` (Placas de Identidad & Nombres de Personajes Junto a sus Imágenes · Personalización de Nombres de Usuarios Reales · Roster Oficial de 6 Personajes · Multijugador Idéntico a 1P)

1. **Placas de Identidad & Nombres de Personajes Junto a sus Imágenes de Jugadores:**
   * Módulo visual `.actor-nameplate` acoplado al pie de cada pedestal de 140px.
   * **Nombre e Icono del Personaje:** Tipografía Fredoka de alto contraste, icono temático (`🤠`, `🐱`, `🦊`, `🐶`, `🐻`, `🦉`) y sombras 3D.
   * **Insignia de Rol / Arquetipo:** Filosofía de Teoría de Juegos y controles en colores HSL reactivos.
   * **Etiqueta Personalizable de Usuario (`✎ Renombrar`):** Permite a los usuarios reales hacer clic y escribir su nombre (ej. "Rodrigo", "Camila"), actualizándose en el Switch OS y marcadores en vivo.
   * Actualización instantánea en cascada al utilizar el selector de personajes Roster.

2. **Roster Oficial de 6 Personajes por Defecto & Selector Visual:**
   * Elenco canónico de 6 arquetipos:
     1. `traveler` (El Viajero): Reciprocidad noble y constructiva.
     2. `kopy` (Kopy el Guardián): Tit for Tat (amable, justiciero y compasivo).
     3. `sneaky` (Sneaky el Bribón): Traidor egoísta permanente (+5 ptos).
     4. `buddy` (Buddy el Granjero): Cooperador incondicional.
     5. `grumpy` (Grumpy el Herrero): Grim Trigger (rencor absoluto tras 1 fallo).
     6. `detective` (Detective Búho): Sondeador táctico y analista de límites.
   * **Selector Visual Dinámico en Pantalla (`[ 👤 Cambiar Personaje ]`):**
     * En 1P vs Computadora: Permite elegir tanto al protagonista como al rival CPU (adaptando la IA en vivo).
     * En Multijugador vs Usuario Real: Permite que el Jugador 1 y el Jugador 2 elijan sus personajes respectivos independientemente.
     * Modal Roster con vista previa de avatares gigantes, paletas de color y filosofías.

2. **Modo Multijugador (1 vs 1) Idéntico al Modo 1 Player:**
   * Misma interfaz de videoconsola con dos combatientes cara a cara: Jugador 1 (Azul) y Jugador 2 (Rojo).
   * Avatares gigantes (140px) con animación permanente *idle* de respiración y pulsación de neón desincronizada.
   * Barra de acciones en medio de la pantalla con botones dedicados para P1 (`[W] COOP` / `[S] ATACAR`) y P2 (`[I] COOP` / `[K] ATACAR`).
   * Animaciones reactivas diferenciadas de Felicidad 😄 y Tristeza 😢 en ambos jugadores según la resolución del dilema.
   * Despliegue automático de la Pantalla de Estadísticas Finales con perfiles psicológicos honoríficos y revancha.

2. **Simulador Espacial 2D (Minecraft & Dwarf Fortress) Independiente y Alternativo:**
   * Módulo independiente ubicado en la pestaña `[ 🔬 SIMULADOR 2D ]`.
   * Espacio toroidal $60 \times 30$, vecindad de Moore (8 vecinos) y reglas de Nowak & May (1992).
   * Skins conmutables: Voxel Pixel Art en Canvas 2D (Minecraft) o Terminal CRT ASCII retro verde fósforo (Dwarf Fortress).

3. **Accesibilidad Integral con Atributos `alt`:**
   * Todas las barras de progreso, marcadores, avatares, gráficos SVG, botones Joy-Con y cajas de texto poseen sus correspondientes atributos `alt` y `aria-label` descriptivos.

4. **Aprovechamiento Integral del Escenario, Barra de Acciones Central & Animaciones (Modo 1P):**
   * **Barra de Acciones en Medio:** Reubicada en el choque central (`.story-center-clash`), flanqueada por ambos contrincantes, eliminando saltos visuales hacia el borde inferior.
   * **Actores Gigantes (140px):** Mayor escala escénica con bordes luminosos y sombras dinámicas calculadas.
   * **Animación Permanente (Idle):** Ciclo continuo de oscilación vertical y pulso de brillo para dotar de vida a la escena.
   * **Máquina de Estados de Expresión Emocional:**
     * **Felicidad:** Salto elástico con rotación dinámica, estallido lumínico esmeralda y burbuja de éxito (`😄 ¡Cooperamos! +3` / `😎 ¡Botín! +5`).
     * **Tristeza:** Estremecimiento sísmico, viraje de saturación, destello escarlata y burbuja de dolor (`😢 ¡Atacado! 0` / `💢 ¡Conflicto! +1`).
     * Transición y retorno automático a guardia pasiva a los 2.2 segundos.

2. **Gráficos de Radar Estratégico SVG (ADN Estratégico):**
   * Diámetro de avatares aumentado de 78px a 110px tanto en Modo Historia como en la Galería de Contrincantes, con anillas de neón pulsantes.
   * **Gráfico de Radar Cuadridimensional (ADN Estratégico):**
     * Visualización matemática poligonal de los 4 pilares de Robert Axelrod:
       1. **Bondad (Niceness):** Inicia cooperando y no traiciona primero.
       2. **Firmeza / Represalia (Retaliation):** Rapidez y severidad de respuesta tras ser traicionado.
       3. **Perdón (Forgiveness):** Facilidad con la que restaura la cooperación si el rival se enmienda.
       4. **Provocación (Provocation):** Tasa de agresiones unilaterales espontáneas.
     * Tarjeta holográfica en tiempo real en el centro de la escena del duelo del Modo Historia.
     * Fichas de inspección visual en la Galería de Rivales / Modo Libre.

2. **Barra de Progreso / Balance en Vivo (Cooperaciones vs Ataques):**
   * Indicador visual dinámico segmentado en verde (Cooperaciones 🤝) y rojo (Ataques/Traiciones 🗡️).
   * **Conmutabilidad con 1 Clic (`[H]` / Botón):** Permite al jugador alternar instantáneamente entre jugar viendo la telemetría en vivo o jugar a ciegas sin verla para no condicionar sus decisiones, revelando el resultado al final.
   * Funcional en Modo Historia, Duelo Arcade y Modo Multijugador.

2. **Modo Multijugador Táctico (2 a 4P) & Reporte Analítico Final:**
   * Duelo local por turnos (Hot-seat) accesible desde la pestaña `[ ⚔️ MULTIJUGADOR (2-4P) ]`.
   * Puntos de Acción (PA) para desplegar Cooperadores (Esmeralda), Traidores (TNT), Imitadores (Diamante) o Pulsos de Caos (Bomba).
   * **Gran Pantalla de Estadísticas Finales Multijugador:**
     * Balance global de agresividad vs cooperación.
     * Tarjeta individual de cada jugador con conteo de jugadas, territorio conquistado y fitness acumulado.
     * **Perfil Psicológico y Título Honorífico Automatizado:** Clasificación según conducta de juego (*El Pacifista Constructor*, *El Conquistador Traidor*, *El Guardián Ojo por Ojo*, *El Pirómano del Caos* o *El Estratega Equilibrado*).

3. **Modo Historia para 1 Jugador: "Crónicas de la Confianza" (Por Defecto):**
   * Campaña de 5 capítulos con narrativa visual RPG en pantalla (Buddy, Sneaky, Kopy, Grumpy y Detective).
   * Diálogos en tiempo real y Diario del Sabio explicativo al superar cada lección.
   * Chasis Nintendo Switch con Joy-Cons interactivos y ajuste 100% a 720p/1080p sin scroll vertical.

4. **Apartado Dedicado: Simulador Espacial 2D Toroidal (Minecraft & Dwarf Fortress):**
   * Preservado íntegramente y accesible mediante el botón superior **`[ 🔬 SIMULADOR 2D ]`** dentro del Switch OS.
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
