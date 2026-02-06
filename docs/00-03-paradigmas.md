---
title: 00-03 · Ruta Unificada (provisional)
date: 2026-02-06
scope: Preparación lógica/estructura
estado: En curso
referencias:
  - README.md
  - docs/00-0-intencion.md
  - docs/00-1-backlog.md
  - docs/01-mapa-web.md
  - docs/02-Biblioteca.md
  - docs/07-operaciones-it.md
---

## Propósito
- Consolidar intención, mapa, backlog y paradigmas en una sola hoja de ruta para la fase de preparación. La estética y el código quedan en segundo plano; mandan la estructura, la lógica y los checkpoints de calidad.
- Este documento actúa como “fuente de verdad” táctica hasta que se publique la versión estable en `docs/`.

## Norte y ámbito
- Web estática + WordPress (tienda/merch) bajo la filosofía motherfuckingwebsite.com: mínimo peso, funciona sin JS, accesible WCAG AA.
- Arquitectura: ES Modules, BEM, SASS 7-1 con `_index.scss` por carpeta y `_index` raíz; coherencia entre parte estática y WP.
- Categorías y narrativa siguen el Mapa Web (8 secciones) y la metáfora de Biblioteca/Carpeta de `docs/01-mapa-web.md` y `docs/02-Biblioteca.md`.

## Estructura esperada (resumen)
- Código: `/src` (fuente), `/public` (build), `/scripts`, `/assets/originals` (ignorado), `/components`, `/js/modules`, `/sass`.
- Documentación: `/docs` (decisiones públicas); este archivo vive aquí como versión pública mínima. La versión extendida interna queda en `/.docs` hasta consolidar.
- Infra: ver `docs/07-operaciones-it.md` para DO droplet, claves y flujo de despliegue.

## Paradigmas aplicados
- Principios: Clean Architecture + SOLID, modularidad estricta, lazy load cuando no rompa a11y, comentarios breves en castellano.
- Paleta y legibilidad (de `.docs/paradigmas-mercedev.md`): negro 60% / naranja 30% / blanco 10%; h1/h2 `#F97316`, h3/h4 `#EA580C`, texto `#4B5563`; AA obligatorio.
- Performance: CSS ≈15KB, JS ≈8KB, imágenes optimizadas (script), sin bundlers pesados.
- Accesibilidad y SEO: WCAG AA, navegación por teclado, alt/aria completos, meta obligatorias + pending meta description y Open Graph por página.
- Seguridad: secretos en `.env`, `.gitignore` robusto, SSH seguro.

## Checkpoints de fase (Go/No-Go)
- Documentación: actualización en README y `/docs` + nota de cambio en `/.docs` para cada entrega.
- A11y: foco visible, Tab/Enter/Escape en interacciones, pruebas sin ratón; pasa checklist WCAG AA.
- SEO: `title`, `charset`, `viewport` siempre; antes de cerrar sprint añadir `meta description` + OG por página; sitemap enlazado en footer.
- Rendimiento: pesos objetivo (CSS/JS), ejecutar `scripts/optimize-images.sh` al añadir assets; evitar JS bloqueante; comprobar TTI/CLS si se toca layout.
- Sin-JS: contenido y navegación básica funcionan sin JavaScript; fallbacks para localStorage/componentes cargados dinámicamente.
- QA automatizado: suites Jest vigentes; Lighthouse pendiente con umbrales >90/95/90/90; preparar plan E2E mínimo.
- Infra: no se despliega a main si falla lint/security/test en pipeline descrito en README.

## Roadmap inmediato (pre-código)
1. Completar metadatos SEO (description + OG) en todas las páginas definidas en `docs/01-mapa-web.md`.
2. Definir guía de build ligero y caché (sin bundler) + uso opcional de prompt caching para MerciAssistant (si aplica).
3. Ejecutar y registrar auditoría Lighthouse; generar backlog de mejoras con responsables y fecha.
4. Cerrar diseño funcional del Laboratorio/carrusel con criterios de a11y y fallback sin JS; documentar en `/docs`.
5. Plan E2E: seleccionar herramienta (Cypress/Playwright), flujos mínimos (nav, CV, laboratorio, checkout simulado) y dataset de pruebas.

## Integración WordPress (tienda/merch)
- Mantener paleta/tipografía y tono; respetar BEM en plantillas o bloques personalizados.
- Checkout simulado y catálogos deben seguir la narrativa de la No-tienda; sin romper peso ni accesibilidad.
- Registrar decisiones WP en `/.docs` y enlazar en `docs/07-operaciones-it.md` cuando se consoliden.

## Cómo usar este documento
- Punto de partida en la rama `paradigmas` hasta consolidar; al converger, mover versión estable a `docs/` y enlazar desde README y backlog.
- Cada tarea del backlog debe referenciar el checkpoint correspondiente de este archivo y del paradigma asociado.
