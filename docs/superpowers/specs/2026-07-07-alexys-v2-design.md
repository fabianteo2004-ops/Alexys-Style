# Alexys Style v2 — Diseño Visual Premium

**Fecha:** 2026-07-07  
**Proyecto:** Alexys Style Luxury Hair Salon  
**Stack:** HTML / CSS / JS puro + GSAP + Canvas API + Lenis

---

## Objetivo

Elevar la web de Alexys Style a nivel spa de 5 estrellas con: fondo animado orgánico, typewriter effect en scroll, micro-interacciones en tarjetas, galería con lightbox y cursor personalizado dorado.

---

## 1. Fondo animado — Canvas Blobs

- Canvas fijo (`position: fixed`) detrás de toda la página (`z-index: -1`)
- 5 esferas de color: dorado cálido `#c9a96e`, púrpura oscuro `#3d1f5e`, negro `#080609`, rosa viejo `#8b4a5a`, ámbar `#a0622a`
- Movimiento: cada blob se mueve en trayectoria suave (sin rebote), ciclo ~40s
- Tamaño: 400–700px de diámetro, bordes completamente difuminados (filter: blur 80–120px)
- Opacidad en hero: 35% | En resto de secciones: 15%

## 2. Hero v2

- Título "Alexys Style" a `clamp(5rem, 12vw, 10rem)` — ocupa casi todo el ancho
- Shimmer dorado en las letras del título: brillo que barre de izquierda a derecha cada 4s
- Typewriter en subtítulo al cargar: GSAP TextPlugin escribe "Donde cada cabello cuenta su historia"
- Botón CTA: efecto ripple dorado al hover (pseudo-elemento que se expande desde el centro)

## 3. Tarjetas (servicios + reseñas)

- Hover → borde animado: línea dorada recorre el perímetro con `stroke-dashoffset` o pseudo-elemento
- Hover → glow dorado: `box-shadow` de 0 a `0 0 30px rgba(201,169,110,0.25)` suavemente
- Precios: al entrar en viewport, cuentan de 0 al valor real (animación 1s, easing out)

## 4. Galería con lightbox

- Click en imagen → lightbox a pantalla completa con fondo oscuro `rgba(0,0,0,0.95)`
- Flechas izquierda/derecha para navegar entre fotos
- Cerrar con click fuera o tecla Escape
- Hover en imagen: overlay dorado semitransparente + icono de lupa
- Transición: fade + scale de 0.95 a 1

## 5. Typewriter en etiquetas de sección

- Cada `.tag` (ej. "SOBRE NOSOTRAS") se borra y re-escribe cuando el scroll llega a esa sección
- GSAP TextPlugin, velocidad: ~0.05s por carácter
- Se ejecuta una sola vez por sección

## 6. Extras premium

- **Cursor personalizado**: círculo dorado 20px que sigue al ratón con leve lag (lerp). Se agranda al hover sobre links/botones
- **Scroll suavizado**: Lenis CDN (~4kb) para scroll sedoso
- **Separadores SVG**: ondas doradas entre secciones en lugar de cortes rectos

---

## Archivos a modificar

- `index.html` — único archivo, todos los cambios van aquí

## Dependencias nuevas

- GSAP TextPlugin (ya se carga GSAP, solo añadir el plugin)
- Lenis (CDN, ~4kb minificado)

## Restricciones

- Sin frameworks — HTML/CSS/JS puro
- Sin imágenes nuevas — las de Unsplash ya están
- Compatible con Firefox y Chrome
