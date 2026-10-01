# El Dilema del Prisionero | Crónicas de la Confianza (Modo Historia 1P & Simulador 2D)

Aplicación web interactiva que enseña los principios de la **Teoría de Juegos** a través de una **campaña narrativa para un jugador ("Crónicas de la Confianza")** ambientada en una **videoconsola portátil tipo Nintendo Switch**, con Joy-Cons interactivos, fondo negro, diálogos RPG, lecciones pedagógicas en pantalla y ajuste 100% a 720p y 1080p sin scroll, conservando además el **simulador espacial 2D toroidal** (con skins Minecraft y Dwarf Fortress) en su propio apartado dedicado.

> **Versión 1.4.0**: Iconos y avatares de personajes más grandes (110px) y Gráficos de Radar de ADN Estratégico SVG para cada contrincante (Bondad, Firmeza, Perdón, Provocación) tanto en Modo Historia como en la Galería de Rivales.

---

## 🧭 1. Gráficos de Radar de ADN Estratégico & Avatares Gigantes
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
