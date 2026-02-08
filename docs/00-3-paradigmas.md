---
title: 00-3 · Ruta Unificada (provisional)
date: 2026-02-06
scope: Preparación lógica/estructura
estado: En curso
referencias:
  - README.md
  - docs/00-0-intencion.md
  - docs/00-1-backlog.md
  - docs/01-mapa-web.md
  - docs/02-biblioteca.md
  - docs/07-operaciones-it.md
---

## Propósito
- Consolidar intención, mapa, backlog y paradigmas en una sola hoja de ruta para la fase de preparación. La estética y el código quedan en segundo plano; mandan la estructura, la lógica y los checkpoints de calidad.
- Este documento actúa como “fuente de verdad” táctica hasta que se publique la versión estable en `docs/`.

## Norte y ámbito
- Fase documental y de preparación: aún sin despliegue ni UI nueva; la web visible sigue la estructura de la rama `main`.
- Filosofía motherfuckingwebsite.com: mínimo peso, accesible WCAG AA, usable sin JS.
- Arquitectura objetivo: ES Modules, BEM y SASS 7-1 cuando se aborde la capa visual/código, manteniendo coherencia con WordPress.

## Estructura esperada (resumen)
- Código (cuando se incorpore): `/src`, `/public`, `/scripts`, `/assets/originals` (ignorado), `/sass`, `/js/modules`, `/components`.
- Documentación: `/docs` (decisiones públicas); este archivo vive aquí como versión pública mínima. La versión extendida interna queda en `/.docs` hasta consolidar.
- Infra: ver `docs/07-operaciones-it.md` para DO droplet, claves y flujo de despliegue.

## Paradigmas aplicados
- Principios: Clean Architecture + SOLID, modularidad estricta, lazy load cuando no rompa a11y, comentarios breves en castellano.
- Paleta y legibilidad (alineada con `docs/02-biblioteca.md`): Ocre/Tierra (Obra Civil), Azul Ingeniero/Acero (Seguridad), Verde Terminal/Lima (Lab/Web), Naranja Acento (Art de Coté), Negro (Mercí/Glosario). Neutros: Gris Hormigón + Blanco de lectura. Contraste AA obligatorio.
- Performance: CSS ≈15KB, JS ≈8KB, imágenes optimizadas (script), sin bundlers pesados.
- Accesibilidad y SEO: WCAG AA, navegación por teclado, alt/aria completos, meta obligatorias + pending meta description y Open Graph por página.
- Seguridad: secretos en `.env`, `.gitignore` robusto, SSH seguro.

## Checkpoints de fase (Go/No-Go)
- Documentación: actualización en README y `/docs` + nota de cambio en `/.docs` para cada entrega.
- A11y: foco visible, Tab/Enter/Escape en interacciones, pruebas sin ratón; pasa checklist WCAG AA.
- SEO: `title`, `charset`, `viewport` siempre; antes de cerrar sprint añadir `meta description` + OG por página; sitemap enlazado en footer.
- Rendimiento: pesos objetivo (CSS/JS), ejecutar `scripts/optimize-images.sh` al añadir assets; evitar JS bloqueante; comprobar TTI/CLS si se toca layout.
- Sin-JS: contenido y navegación básica funcionan sin JavaScript; fallbacks para localStorage/componentes cargados dinámicamente.
- QA automatizado: **stack por definir** (sin código aún); Lighthouse pendiente con umbrales >90/95/90/90; preparar plan E2E mínimo.
- Infra: no se despliega a main si falla lint/security/test en pipeline descrito en README.

## Roadmap inmediato (pre-código)
1. Completar metadatos SEO (description + OG) para las páginas existentes en la rama `main`.
2. Definir guía de build ligero y caché (sin bundler) + uso opcional de prompt caching para MerciAssistant (si aplica).
3. Ejecutar y registrar auditoría Lighthouse; generar backlog de mejoras con responsables y fecha.
4. Plan E2E: seleccionar herramienta (Cypress/Playwright), flujos mínimos acordes a la estructura actual y dataset de pruebas.
5. Preparar checklist de “sin-JS usable” aplicable a la navegación y contenidos actuales.

## Integración WordPress (tienda/merch)
- Mantener paleta/tipografía y tono; respetar BEM en plantillas o bloques personalizados.
- Evitar dependencias pesadas; priorizar rendimiento y a11y sobre la estética.
- Registrar decisiones WP en `/.docs` y enlazar en `docs/07-operaciones-it.md` cuando se consoliden.

## Cómo usar este documento
- Punto de partida en la rama `paradigmas` hasta consolidar; al converger, mover versión estable a `docs/` y enlazar desde README y backlog.
- Cada tarea del backlog debe referenciar el checkpoint correspondiente de este archivo y del paradigma asociado.

---
## Notas de cambio
- 2026-02-07: Normalización de referencias al archivo `docs/00-3-paradigmas.md` en README y docs; ajuste del título interno.
- 2026-02-07: Alineado el estado del pipeline y workflows con el estado real del repo (planificado, pendiente de creación).
- 2026-02-07: Ajuste del apartado de QA automatizado para reflejar que el stack aún no está definido.
- 2026-02-07: Backlog actualizado para marcar documentos pendientes de crear y evitar dependencias fantasma.
- 2026-02-07: Creadas plantillas mínimas de documentación (Mercí, Home, Bitácora, Proyecto).
- 2026-02-07: Backlog corregido para reflejar que las plantillas v0 ya existen.
- 2026-02-07: Paleta en paradigmas alineada con `docs/02-biblioteca.md`.
