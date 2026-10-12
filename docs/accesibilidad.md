# Accesibilidad – Rikimaka

Objetivo de conformidad: **WCAG 2.2 nivel AAA**.

## 1. Contraste de colores

Relación mínima exigida por WCAG 1.4.6 (AAA): **7:1** para texto normal y **4.5:1** para texto grande.

| Texto / elemento | Fondo | Relación | Resultado |
|---|---|---|---|
| `#1A1A1A` texto | `#FFFFFF` | 17.4:1 | ✔ AAA |
| `#1A1A1A` texto | `#F5F3F1` | 15.7:1 | ✔ AAA |
| `#FFFFFF` texto | `#9E0033` botón primario | 8.4:1 | ✔ AAA |
| `#9E0033` texto | `#FFFFFF` | 8.4:1 | ✔ AAA |
| `#3A3A3A` texto secundario | `#FFFFFF` | 11.4:1 | ✔ AAA |
| `#595959` bordes e íconos | `#FFFFFF` | 7.0:1 | ✔ (no textual ≥ 3:1) |
| `#FFFFFF` texto | Video con capa `rgba(10,10,10,.55)` | ≥ 7:1 | ✔ AAA (verificar con el video final) |

Nota: el carmesí de referencia `#B5003B` da 6.9:1 sobre blanco y **no** llega a AAA; por eso se usa `#9E0033`.

## 2. Criterios AAA aplicados en el diseño

| Criterio | Cómo se cumple | Pantallas |
|---|---|---|
| 1.4.6 Contraste mejorado | Paleta de la tabla anterior | Todas |
| 1.4.8 Presentación visual | Texto de 18 px, interlineado 1.5, líneas de 80 caracteres como máximo, sin justificar | Todas |
| 1.4.9 Imágenes de texto | Solo el logotipo; el resto es texto real | Todas |
| 2.1.3 Teclado sin excepciones | Calendario con flechas, modales con foco atrapado y Esc | W03, W03b, W07b, W08b |
| 2.2.3 Sin límites de tiempo | Sin cierre de sesión por inactividad | W01 |
| 2.2.4 Interrupciones | Notificaciones consultables, sin ventanas emergentes automáticas | W02 |
| 2.3.3 Animaciones | Video pausable y desactivado con `prefers-reduced-motion` | W00 |
| 2.4.8 Ubicación | Migas de pan y `aria-current="page"` en el menú | W02–W09 |
| 2.4.9 Propósito de los enlaces | Textos de enlace autoexplicativos («Ver reporte del 9 de octubre») | W05, W07 |
| 2.4.10 Encabezados de sección | Cada bloque tiene título | Todas |
| 2.5.5 Tamaño del objetivo | Botones de 48 px de alto (mínimo 44 px) | Todas |
| 3.1.4 Abreviaturas | `<abbr>` y glosario (KPI, TI, RR. HH.) | W09 |
| 3.1.5 Nivel de lectura | Resumen en lenguaje sencillo | W09 |
| 3.2.5 Cambios a petición | Filtros con botón «Aplicar filtros» | W05, W09 |
| 3.3.5 Ayuda | Texto de ayuda en campos y enlace de ayuda | W01, W03, W04 |
| 3.3.6 Prevención de errores | Confirmación y «Deshacer» en todas las acciones | W03b, W07b, W08 |

## 3. Plan de pruebas (Avance II en adelante)

| Herramienta | Meta |
|---|---|
| validator.w3.org / jigsaw.w3.org | 0 errores de HTML y CSS |
| Lighthouse | 100 en Accesibilidad |
| WAVE | 0 errores, 0 errores de contraste |
| NVDA (Windows) o VoiceOver (macOS) | Recorrer W01 → W02 → W03 → W03b solo con teclado y lector |
| Zoom del navegador al 200 % y ancho de 320 px | Sin pérdida de contenido ni desplazamiento horizontal |
