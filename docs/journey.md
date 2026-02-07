**PokedIn** es un nombre genial. Es pegadizo, explica el concepto de inmediato y tiene ese toque *cheeky* que le encanta a la comunidad tech.

Hacer que los "stats" dependan directamente de **GitHub** no solo es más justo (evita que la gente mienta sobre su nivel), sino que convierte el perfil del programador en su "hoja de personaje" real.

Aquí tienes la expansión del plan funcional integrando la **PokedIn-dex** y la lógica de datos de GitHub.

---

## 📊 1. Integración de Stats (The GitHub Sync)

Para que el login transforme el perfil de GitHub en un personaje de PokedIn, necesitamos mapear la data de la API de GitHub a atributos de juego:

| Dato de GitHub | Atributo en PokedIn | Efecto en el Juego |
| --- | --- | --- |
| **Repositorios Públicos** | **Nivel de Entrenador** | A mayor cantidad de código, más "jerarquía" en el mapa. |
| **Lenguaje más usado** | **Tipo Primario** | Ej: JavaScript (Eléctrico), Python (Tierra), Rust (Acero). |
| **Stars en repos** | **Puntos de Ataque (AP)** | Representa tu influencia y calidad de código. |
| **Followers** | **Carisma / Aura** | Desbloquea misiones de "Líder de Gremio" (networking masivo). |
| **Contribuciones (Grafo)** | **Energía / Stamina** | Los "cuadritos verdes" determinan cuántas misiones puedes hacer al día. |

---

## 📕 2. La PokedIn-dex (Tu Registro de Carrera)

La PokedIn-dex no es solo una lista, es el registro de tu trayectoria y las conexiones que has hecho "en la vida real".

### Secciones de la PokedIn-dex:

* **Dev-Dex:** Un registro de cada desarrollador con el que has hecho un "Sync". Al abrir su ficha, puedes ver su stack, su GitHub y una nota privada de "dónde se conocieron".
* **Hub-Log:** Lista de los lugares aliados que has visitado (Cafeterías, Coworkings). Completar el set de una ciudad te da un badge de **"Local Legend"**.
* **Tech-Archive:** Cada vez que resuelves un reto técnico en un nodo, desbloqueas una entrada con "Lore" sobre esa tecnología (ej. "La historia oculta de C++").

---

## 🛠️ Plan de Requisitos Funcionales (Actualizado)

### RF1 - Sistema de Stats Dinámico

* **RF1.1:** El sistema debe realizar una llamada a la API de GitHub (`/users/{username}/repos`) durante el primer login y cada 24 horas para actualizar el nivel del usuario.
* **RF1.2:** Cálculo automático del "Tipo" dominante basado en los bytes de lenguaje devueltos por GitHub.

### RF2 - La PokedIn-dex Web

* **RF2.1:** Interfaz tipo *grid* que muestre siluetas de los "tipos de devs" o "badges" no descubiertos para incentivar la exploración.
* **RF2.2:** Capacidad de exportar tu PokedIn-dex o un "Resumen de Entrenador" como una imagen para compartir en LinkedIn (marketing orgánico).

### RF3 - Mecánica de "Captura" (Sync)

* **RF3.1:** Para agregar a alguien a tu PokedIn-dex, ambos deben estar en el mismo **Nodo** y realizar un intercambio de códigos de 4 dígitos (generado dinámicamente) para validar el encuentro físico.

---

## 🎨 Estructura de Componentes en React (Sugerencia)

Para tu demo actual, podrías organizar los componentes así:

1. **`<ProfileCard />`**: Muestra tu avatar de GitHub, tu tipo (Elemento) y tus stats calculados.
2. **`<Scanner />`**: Botón que dispara la geolocalización manual y renderiza la lista de `Nodes` y `Devs` cercanos.
3. **`<PokedIndex />`**: Un modal o ruta separada que mapea los registros de tu base de datos (Supabase/Firebase) de conexiones previas.
4. **`<CheckInButton />`**: Valida tu posición con el nodo seleccionado.

---

> **Idea Pro:** Podrías añadir un "Daily Commit Streak Bonus". Si el usuario hizo un commit en GitHub en las últimas 24 horas, su rango de escaneo en PokedIn aumenta un 50%. ¡Gamificación pura para la productividad!

**¿Te gustaría que te ayude a redactar el pequeño algoritmo en JavaScript que clasifica al usuario en un "Tipo" (Elemento) según los lenguajes de su GitHub?**
