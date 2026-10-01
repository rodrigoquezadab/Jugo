# El Dilema del Prisionero | Crónicas de la Confianza (Modo Historia 1P & Simulador 2D)

Aplicación web interactiva que enseña los principios de la **Teoría de Juegos** a través de una **campaña narrativa para un jugador ("Crónicas de la Confianza")** ambientada en una **videoconsola portátil tipo Nintendo Switch**, con Joy-Cons interactivos, fondo negro, diálogos RPG, lecciones pedagógicas en pantalla y ajuste 100% a 720p y 1080p sin scroll, conservando además el **simulador espacial 2D toroidal** (con skins Minecraft y Dwarf Fortress) en su propio apartado dedicado.

> **Versión 1.8.2**: Reubicación de la caja narrativa de diálogo y comentarios en la parte superior del escenario (arriba de los personajes y de la barra de acciones central) para una lectura natural y óptima en la consola Nintendo Switch, junto con las placas de identidad de los 6 personajes y el soporte multijugador idéntico a 1P.

---

## 📜 1. Texto de la Historia Arriba de los Personajes y Botones
* **Lectura Natural Tipo RPG / Novela Visual:** La caja de diálogo y narrativa (`.story-rpg-dialogue-box`) en el **Modo Historia (1P)** y la caja de comentarios del árbitro (`.mp-dialogue-box`) en el **Modo Multijugador (2P)** ahora se posicionan en la **zona superior del escenario**, inmediatamente encima de los personajes y de la barra de acciones central.
* **Jerarquía Visual Clara:**
  1. **Arriba:** Caja de diálogo con insignia de interlocutor (`.story-speaker-tag`), texto narrativo del capítulo y consejos estratégicos.
  2. **Abajo:** Fila escénica con el Jugador a la izquierda, la barra de acciones y radar estratégico en medio, y el rival a la derecha.
* **Espacio y Proporciones Preservadas:** Se mantiene la altura de 140px de los avatares gigantes y la escala completa sin scroll vertical en resoluciones 720p y 1080p.

---

## 🏷️ 2. Placas de Identidad & Nombres de Personajes con sus Imágenes
Cada luchador cuenta con una **Placa de Identidad Nintendo (`.actor-nameplate`)** situada bajo su avatar gigante de 140px:
* **Nombre Oficial e Icono del Personaje:** Muestra con claridad el nombre del arquetipo activo (`🤠 El Viajero`, `🐱 Kopy el Guardián`, `🦊 Sneaky el Bribón`, `🐶 Buddy el Granjero`, `🐻 Grumpy el Herrero`, `🦉 Detective Búho`).
* **Insignia Temática de Arquetipo:** Detalla la filosofía de juego y controles asociados (`Estratega Noble`, `El Imitador (Tit for Tat)`, `Joy-Con Azul [W / S]`, `Joy-Con Rojo [I / K]`, etc.).
* **Etiqueta Editable para Usuarios Reales (`✎ Renombrar`):** Al hacer clic en la etiqueta superior del jugador (`[ 🎮 JUGADOR (TÚ) ]`, `[ 🟦 JUGADOR 1 ]`, `[ 🟥 JUGADOR 2 ]`), puedes ingresar tu nombre real (ej. *Rodrigo*, *Lucas*, *Camila*) y se sincronizará automáticamente en la pantalla de batalla, en la barra superior de la consola y en los marcadores.
* **Sincronización Total con el Roster:** Al cambiar de personaje en el selector, la placa de nombre, el icono, la paleta cromática y la ilustración se actualizan simultáneamente.

---

## 👥 2. Roster Oficial de 6 Personajes & Selector Visual (1P vs CPU & 2P vs Usuario Real)
Cualquier jugador puede elegir entre los **6 arquetipos de Teoría de Juegos por defecto**:
1. **🤠 El Viajero (Gamer Azul):** Estratega noble y curioso. Inicia cooperando y busca la reciprocidad mutua.
2. **🐱 Kopy el Guardián (Tit for Tat):** La regla del espejo. Noble al inicio, castiga las agresiones y perdona de inmediato si vuelves a cooperar.
3. **🦊 Sneaky el Bribón (Traidor Permanente):** Depredador y estafador. Nunca coopera y busca robar los 5 puntos explotando a los inocentes.
4. **🐶 Buddy el Granjero (Cooperador Incondicional):** Amigo pacífico. Coopera siempre sin importar lo que haga el rival.
5. **🐻 Grumpy el Herrero (Grim Trigger):** El rencoroso implacable. Justo de entrada, pero si lo traicionas una sola vez, nunca jamás te perdonará.
6. **🦉 Detective Búho (Analista Táctico):** Sonda tus intenciones al inicio; si te dejas abusar te explota, pero si te defiendes con firmeza, coopera.

* **¿Cómo se seleccionan?**
  * **En Modo 1P (vs Computadora):**
    * Puedes cambiar a tu personaje con `[ 👤 Cambiar Personaje ]`.
    * Puedes cambiar al rival de la computadora con `[ 🤖 Cambiar Rival CPU ]`, adoptando de inmediato su avatar, radar estratégico e inteligencia artificial.
  * **En Modo Multijugador (vs Usuario Real 1v1):**
    * El Jugador 1 (Azul) elige su personaje con `[ 👤 Elegir Personaje P1 ]`.
    * El Jugador 2 (Rojo) elige su personaje con `[ 👤 Elegir Personaje P2 ]`.
  * **Modal Roster:** Despliega una cuadrícula interactiva con las 6 fichas completas, retratos vectoriales iluminados y asignación inmediata en 1 clic.

---

## ⚔️ 2. Modo Multijugador (1 vs 1) Idéntico al Modo 1 Player
Accesible desde la pestaña principal `[ ⚔️ MULTIJUGADOR (2-4P) ]` del Switch OS:
* **Misma Estructura Escénica:**
  * **Jugador 1 (Azul - Joy-Con L):** Avatar gigante (140px), respiración permanente *idle*, burbuja emocional flotante (`#mp-p1-emotion`), marcador en vivo y controles `[ W ] 🤝 COOP` / `[ S ] 🗡️ ATACAR`.
  * **Jugador 2 (Rojo - Joy-Con R):** Avatar gigante (140px), respiración permanente *idle*, burbuja emocional flotante (`#mp-p2-emotion`), marcador en vivo y controles `[ I ] 🤝 COOP` / `[ K ] 🗡️ ATACAR`.
* **Barra de Acciones en Medio de la Pantalla:** Controles táctiles y teclado colocados en el centro neurálgico entre ambos jugadores, con confirmación de jugada lista y resolución simultánea del choque.
* **Animaciones Reactivas Diferenciadas (Felicidad 😄 y Tristeza 😢):** Ambos jugadores celebran o sufren el desenlace de la ronda de forma simultánea e independiente según la matriz de Teoría de Juegos.
* **Reporte Final Multijugador:** Al completar las rondas, se abre el modal analítico con balance global de cooperaciones vs ataques, perfiles psicológicos (*El Pacifista Constructor*, *El Conquistador Traidor*, *El Guardián Ojo por Ojo*, etc.) y botón de revancha instantánea.

---

## 🔬 2. Simulador Espacial 2D (Minecraft / Dwarf Fortress): Modo Independiente y Alternativo
* Ubicado en su pestaña dedicada **`[ 🔬 SIMULADOR 2D ]`**, totalmente separado del duelo por turnos de la consola.
* Autómata celular toroidal $60 \times 30$ con vecindad de Moore de 8 vecinos bajo las reglas de Nowak & May (1992).
* Skins alternativas conmutables: Canvas Voxel 2D (Minecraft) o Terminal CRT en fósforo verde (Dwarf Fortress) con tecla `[M]`.

---

## ♿ 3. Cobertura Total de Atributos `alt` y Accesibilidad
* Toda barra de progreso (Barra de balance en vivo, barra de balance final multijugador, indicador de batería), avatar, gráfico SVG de radar, botón de acción Joy-Con y caja narrativa cuenta con su atributo `alt="..."` descriptivo y etiquetas `aria-label`/`title`.

---

## 🎮 4. Escenario Óptimo: Barra de Acciones Central, Actores Gigantes & Animaciones (Modo 1P)
* **Barra de Acciones en Medio de la Pantalla:** Los comandos de combate (`[🤝 CUMPLIR PACTO]` y `[🗡️ ATACAR / TRAICIONAR]`, junto con `[📜 ABRIR DIARIO]`) ahora se sitúan directamente en el centro neurálgico entre ambos contrincantes, ofreciendo una ergonomía arcade directa sin tener que mirar al pie de página.
* **Actores Gigantes (140px) & Distribución Escénica:** Los personajes (El Viajero y los 5 arquetipos rivales) crecen hasta **140px** con ilustraciones vectoriales de **118px**, pedestales de batalla y ajuste perfecto sin scroll a 720p/1080p.
* **Animación Permanente (Idle Breathing):** Ambos combatientes respiran y levitan suavemente de forma continua e independiente en su posición de guardia.
* **Animaciones Reactivas: Felicidad 😄 vs Tristeza 😢:**
  * **Felicidad (Cooperación o Ganancia Exitosa):** El personaje ejecuta un salto elástico triunfal (`actor-jump-happy`), destellos y un estallido de aura esmeralda/dorada, coronado por su burbuja flotante de satisfacción (`😄 ¡Cooperamos! +3` o `😎 ¡Botín! +5`).
  * **Tristeza / Daño (Traicionado o Ataque Mutuo):** El personaje sufre un estremecimiento violento con distorsión de color, destello rojo de daño y decaimiento cabizbajo (`actor-shudder-sad`), acompañado de su burbuja de lamento (`😢 ¡Atacado! 0` o `💢 ¡Ataque mutuo! +1`).

---

## 🧭 2. Gráficos de Radar de ADN Estratégico para Cada Contrincante
* **Avatares Ampliados (110px):** Los iconos de personajes y contrincantes cuentan con mayor escala visual, marcos de neón temáticos y animación de pulso interactivo para una lectura visual clara estilo Nintendo.
* **Gráficos de Radar SVG Cuadridimensionales (ADN de Teoría de Juegos):**
  Cada contrincante posee su propia huella estratégica calculada y representada vectorialmente en 4 ejes:
  * **🤝 Bondad (Niceness):** Disposición a cooperar en la primera jugada y no iniciar hostilidades.
  * **⚡ Firmeza (Retaliation):** Capacidad de castigar inmediatamente una traición o agresión.
  * **🕊️ Perdón (Forgiveness):** Rapidez para restaurar la cooperación si el rival vuelve a cooperar.
  * **😈 Provocación (Provocation):** Tendencia a tentar la suerte traicionando de improviso.
* **Visualización en Vivo & Galería:**
  * **En el Duelo de Historia:** Una tarjeta holográfica central muestra el radar táctico activo y la debilidad del contrincante.
  * **En la Galería de Rivales:** Fichas técnicas completas con gráficos de radar de cada arquetipo (Kopy, Sneaky, Buddy, Grumpy y Detective).

---

## 📊 2. Barra de Balance en Vivo (Cooperaciones vs Ataques)
Ubicada en la barra de la consola Switch:
* **Visualización Dinámica:** Muestra en tiempo real la proporción entre **🤝 Cooperaciones (Verde)** y **🗡️ Ataques/Traición (Rojo)**.
* **Jugar con Barra o a Ciegas (1 Clic):** Puedes alternar la barra entre visible y oculta con el botón `[ 👁️ Ocultar / Ver Barra ]`, haciendo clic directamente en la barra o pulsando la tecla `[H]`. Esto permite jugar en modo inmersivo sin conocer el recuento hasta el final.

---

## ⚔️ 2. Modo Multijugador (2 a 4P) & Estadísticas Finales
Accesible directamente desde la pestaña `[ ⚔️ MULTIJUGADOR (2-4P) ]` del Switch OS:
* **Duelo Táctico Hot-Seat:** Los jugadores compiten por turnos distribuyendo Puntos de Acción (PA) para desplegar Cooperadores (Esmeralda), Traidores (TNT), Imitadores (Diamante) o Pulsos de Caos (Bomba).
* **Pantalla de Estadísticas Finales:** Al concluir el duelo, se despliega un reporte analítico exhaustivo:
  * **Balance Global:** Proporción total de cooperaciones vs agresiones en toda la partida.
  * **Tarjetas de Jugadores (P1 a P4):** Conteo exacto de cooperaciones, infiltraciones TNT, centinelas TFT, bombas y celdas conquistadas.
  * **Perfil Psicológico & Título Honorífico:** Clasifica a cada jugador automáticamente según su comportamiento (*El Pacifista Constructor*, *El Conquistador Traidor*, *El Guardián Ojo por Ojo*, *El Pirómano del Caos* o *El Estratega Equilibrado*).
  * Botón de revancha inmediata.

---

## 📖 3. Modo Historia para 1 Jugador: "Crónicas de la Confianza" (Por Defecto)
El jugador asume el papel de **El Viajero**, recorriendo el Valle de la Confianza a través de 5 capítulos con dilemas morales y económicos explicados con narrativa visual tipo RPG de Nintendo:
* **Capítulo 1: El Mercado de la Buena Fe (con Buddy el Granjero):**
  * *Trama:* Aprende el valor del intercambio honesto de cosechas.
  * *Lección:* La cooperación mutua genera riqueza compartida de la nada ($R > P$).
* **Capítulo 2: El Forastero de las Sombras (con Sneaky el Bribón):**
  * *Trama:* Un estafador en la taberna te promete multiplicar tus monedas.
  * *Lección:* La ingenuidad ciega ante depredadores no es sostenible. Protegerse es necesario.
* **Capítulo 3: El Centinela del Espejo (con Kopy el Guardián):**
  * *Trama:* El guardián de la frontera aplica la ley del espejo (Tit for Tat).
  * *Lección:* La regla de oro de Axelrod: ser noble al inicio, no tolerar abusos y saber perdonar.
* **Capítulo 4: El Fuego del Rencor (con Grumpy el Herrero):**
  * *Trama:* Un herrero legendario que nunca perdona si rompes tu palabra una sola vez.
  * *Lección:* La fragilidad de la reputación. La traición destruye alianzas duraderas.
* **Capítulo 5 (Clímax): El Gran Juicio del Sabio (con el Detective):**
  * *Trama:* El examen supremo del Consejo para consagrarte como Maestro de la Confianza.
  * *Lección:* Poner límites firmes obliga a los rivales a respetarte y cooperar.
* **Caja de Diálogo RPG & Diario del Sabio:** En cada encuentro, los personajes reaccionan con diálogos expresivos. Al completar cada capítulo se desbloquea una página del diario con la lección filosófica y matemática explicada con claridad.

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
