# Cotizador MARCHOS

Aplicación web interactiva (cotizador inteligente) para la agencia Marchos.
Un solo archivo: `index.html`. No necesita instalación ni servidor.

## Cómo probarlo en tu compu

1. Abrí `index.html` con doble clic (se abre en el navegador).
2. Completá el diagnóstico de 5 pasos y revisá la propuesta generada.
3. Probá el panel interno: abrí la misma página agregando `?admin` al final
   de la dirección (ej: `index.html?admin`). Clave inicial: `McH-7v3!2026`.

## Cómo publicarlo (GitHub Pages, gratis)

1. Creá un repo público en GitHub (ej: `marchos-cotizador`).
2. Subí el archivo `index.html` a la raíz del repo.
3. En el repo: Settings → Pages → Source: branch `main`, carpeta `/root` → Save.
4. En unos minutos tenés el enlace: `https://TU-USUARIO.github.io/marchos-cotizador/`
   Ese es el enlace para compartir con tus clientes.
5. El panel interno queda en `.../index.html?admin` (no lo compartas).

## Cómo funciona el captación de leads

- Cada cliente que genera su propuesta puede enviarla completa a Marchos por
  WhatsApp con el botón "Solicitar reunión por WhatsApp" (ese es el canal
  real de llegada de los datos).
- Como respaldo, cada propuesta queda guardada en el navegador donde se
  complete. Desde el panel admin (`?admin`) podés ver los prospectos con su
  puntaje (0-100) y prioridad, cambiar el estado comercial y exportar todo a CSV.

## Precios y paquetes

- Los precios salen del catálogo oficial (Start Bs 1.800, Crecimiento Bs 2.800,
  Dominio Bs 3.800 + 8 servicios adicionales). Verificado contra
  `Marchos_Catalogo_Actualizado.pdf`.
- Para cambiar precios sin tocar código: panel admin → pestaña
  "Precios y configuración" (se guarda en ese dispositivo).
- Para cambiar entregables o textos de planes: editá la sección `CONFIG`
  al inicio del `<script>` de `index.html`.

## Notas técnicas

- Motor de recomendación y scoring aislados entre `//ENGINE-START` y
  `//ENGINE-END`: son funciones puras, fáciles de testear.
- Las pruebas automáticas están en `../tests/escenarios.js`
  (se corren con Node: `node tests/escenarios.js`).
- Si en el futuro querés una base central de prospectos, no hay que rehacer
  nada: el motor ya genera el payload listo y solo se conecta un endpoint.
