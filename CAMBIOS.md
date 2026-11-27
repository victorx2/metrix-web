# Metrix Web — Registro de cambios y prompts

Archivo principal: `metrix_v1.html` (una sola página: HTML + Tailwind por CDN + JS en línea).
Carpeta de imágenes: `img/`.

---

## Sesión 27/11/2026 — Banner principal (hero)

### 1. Reducir altura del banner y carrusel automático

**Prompt (mensaje del cliente):**
> Está mejor. Ahora hay que reducir la altura de las imágenes del banner principal y quitarle esos botones de flechas y pausar y que automáticamente se pasen las imágenes

**Cambios:**
- Flechas y botón de pausa: en `metrix_v1.html` ya no existían. El carrusel ya avanzaba solo cada 3 s (función `startHeroAutoPlay`, `setInterval` de 3000 ms). Solo quedan los puntos indicadores.
- Sección `#inicio`: se quitó `min-h-screen` (antes ocupaba toda la pantalla) y se redujo el padding: `pt-24 pb-8 lg:pt-28 lg:pb-10`.
- Visuales de los 3 slides: de `max-w-sm sm:max-w-md lg:max-w-[440px]` a `max-w-[280px] sm:max-w-xs lg:max-w-[340px]`.
- Separación texto/visual: `gap-12` → `gap-8`. Puntos indicadores: `mt-8` → `mt-6`.
- Panel de métricas (slide 3): padding `p-6 sm:p-8` → `p-5`, `space-y-5` → `space-y-4`, tarjetas `p-4` → `p-3`, números `text-3xl` → `text-2xl`.

### 2. Reclamo: "las imágenes no se pasan automáticamente y se ven con mucho grosor"

**Prompt (conversación reenviada del cliente):**
> Las imágenes no se están pasando de forma automática y, de igual forma, las estoy viendo con mucho grosor. No sé si lo revisas antes de indicarlo.

**Verificación:** probado en Chrome headless con capturas a 1,5 s, 4,5 s y 7,5 s: el carrusel sí cambia de slide (1 → 2 → 3) y no hay errores de JavaScript.
**Conclusión:** como el cliente mencionó flechas y pausa que este archivo no tiene, lo más probable es que estuvieran viendo otra copia (hosting, archivo viejo o caché). Hay que asegurarse de que vean ESTA versión.

### 3. Título más delgado y con letras separadas

**Prompts:**
> haz el título más delgado y separa las letras
> hazlo todavía más delgado
> bájalo a 400
> deja transforma un poco más gruesa

**Cambios (títulos de los 3 slides, líneas ~308, ~486, ~563):**
- Grosor: `font-extrabold` (800) → `font-normal` (400). Pasó por 600 y 500 hasta quedar en 400.
- Espaciado: `tracking-tight` → `tracking-normal`.
- Fuente: se agregaron los pesos 400 y 500 de Plus Jakarta Sans en el `<link>` de Google Fonts:
  `Plus+Jakarta+Sans:wght@400;500;600;700;800`
- Palabras doradas ("transforma", "ejecuta", "impacto"): se agregó `font-semibold` (600) para que resalten sobre el resto del título.

---

## Pendiente / notas para continuar

- Confirmar con el cliente dónde ven la página (URL o archivo enviado) y subir esta versión ahí.
- Si quieren el banner aún más bajo, el siguiente paso es reducir el tamaño del título (`text-4xl sm:text-5xl lg:text-[3.1rem]`).
- Los prompts de sesiones anteriores a esta no quedaron registrados aquí.
