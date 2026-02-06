# 08-wordpress-integracion.md · Lineamientos mínimos

## Objetivo
Mantener coherencia de marca, rendimiento y accesibilidad al integrar la tienda/merch en WordPress (DO cloudPanel).

## Paleta y tipografía (alineado con 02-biblioteca)
- Estantes: Ocre (Obra civil), Azul ingeniero (Seguridad), Verde terminal (Laboratorio), Naranja acento (Art de Coté), Negro (Mercí/Glosario).
- Neutros: Gris hormigón para fondos, blanco de alto contraste para áreas de lectura.
- Botones: usar el color del estante que represente el contenido; texto siempre con contraste AA.
- Titulación: sans técnica/rotunda (p.ej. Inter/Roboto Mono); cuerpo: serif legible (p.ej. Merriweather/Lora). Evitar fuentes pesadas.

## CSS y semántica
- Respetar nomenclatura BEM en plantillas/bloques personalizados.
- Limitar CSS adicional; sin frameworks pesados; mantener CSS total <15KB donde sea posible.
- Asegurar HTML5 semántico en plantillas (main, nav, header, footer, section).

## Accesibilidad
- WCAG AA: foco visible, navegación con teclado (Tab/Enter/Escape), `aria-label/role/aria-pressed` en controles.
- Alt descriptivos; decorativas con `alt=""`.
- Comprobar contraste antes de publicar.

## Rendimiento
- Imágenes: subir webp + fallback; comprimir antes de subir.
- Evitar JS bloqueante; cargar scripts de tienda en defer.
- Registrar Lighthouse al publicar cambios de tema/plantillas.

## Contenido y UX
- Narrativa “No-tienda”: microhistorias, catálogo coherente, checkout simulado claro.
- Mantener enlaces de footer (GitHub, LinkedIn, email, mapa del sitio, año dinámico, contacto/formulario).

## Seguridad
- Secretos fuera del repositorio; usar `.env` o credenciales del panel.
- Revisar roles/usuarios WP y desactivar plugins innecesarios.

## Registro de decisiones
- Documentar cambios de tema/plantillas y resultados de Lighthouse en `docs/07-operaciones-it.md` y añadir nota corta en `docs/00-03-paradigmas.md` cuando afecten a paradigmas.
