# 00-1-backlog.md · mercedev.es (Sincronizado)

## 0) Marco Scrum Operativo
**Roles:** PO (Prioridades), SM (Foco/WIP), Dev (Implementación).
**Cadencia:** Sprints de 1 semana.
**DoD Global:** Mobile-first, sin-JS usable, accesible (WCAG/Lighthouse registrado), sin secretos, errores manejados, docs en `/docs`.

---

## 1) Epic: Repo como “fuente de verdad” (Base)
- [X] **1.1 Repo inicial:** `/src`, `/public`, `/docs`, `/scripts`, `/.github/workflows`.
- [X] **1.2 Seguridad:** `.gitignore` robusto.
- [X] **1.3 Docs base:** README.md, `docs/00-0-intencion.md` y `docs/00-03-paradigmas.md`.
- [X] **1.4 Operaciones IT:** `docs/07-operaciones-it.md` (infra y despliegue DO; incluye guía WP `docs/08-wordpress-integracion.md`).

## 2) Epic: Documentación Desbloqueadora (Pre-Código)
- [X] **2.1 Mapa Web:** `docs/01-mapa-web.md`.
- [X] **2.2 Biblioteca Conceptual:** `docs/02-biblioteca.md` (Categorías/Colores + Carpeta).
- [2.1,2.2] **2.3 Mercí v0:** `docs/03-merci-v0.md` (Contrato de comportamiento).
- [2.1] **2.4 Datos Glosario:** Crear `src/data/glosario.json` con los primeros 10 términos.

## 3) Epic: Web v1 “Funcional”
- [2.x] **3.1 Arquitectura:** `docs/04-home-estructura.md`.
- [3.1] **3.2 Implementación:** Home + 5 páginas base (HTML/CSS).
- [2.2,3.1] **3.3 Componente Biblioteca:** Visual v1 (Semántica alineada).
- [2.2,3.1] **3.4 Componente Carpeta:** Vista alternativa "Índice con pestañas" (5 Tabs CSS: Ocre, Azul, Verde, Naranja, Negro).

## 4) Epic: Calidad Automática (QA) - *EL PORTERO*
*Sin esto, no hay deploy seguro.*
- [3.1] **4.1 Linter:** Configurar `markdownlint` y `htmlhint`.
- [3.x] **4.2 Accessibility Test:** Integrar `axe-core`.
- [3.x] **4.3 Link Checker:** Script anti-404.
- [3.x] **4.4 Smoke Test:** Verificación de status 200.
- [3.x] **4.5 Lighthouse:** Ejecutar y registrar baseline (>90/95/90/90) en cambios de layout/assets.
- [3.x] **4.6 E2E mínimo:** Elegir herramienta (Playwright/Cypress) y flujos base (nav, CV, laboratorio, checkout simulado).

## 5) Epic: Publicación y CI/CD
- [1.4,4.x] **5.1 Mirror:** Deploy a GitHub Pages.
- [1.4,5.1] **5.2 GH Secrets:** Configurar `DEPLOY_HOST`, `DEPLOY_USER`, `DEPLOY_KEY`.
- [1.4,4.x,5.2] **5.3 Pipeline Producción:** GitHub Action + `rsync` hacia Droplet (178.128.47.178) con etapas: lint, security scan, accesibilidad (Axe/Lighthouse CI), link checker, smoke tests, deploy si PASS.

## 6) Epic: Cuaderno de Bitácora
- [2.x] **6.1 Plantilla:** `docs/05-Cuaderno-de-Bitacora-template.md`.
- [6.1] **6.2 Semilla:** 5 posts iniciales.
- [6.1,6.2] **6.3 LinkedIn:** Automatización RSS/Webhook.

## 7) Epic: Mercí (Identidad)
- [2.3] **7.1 SVG:** `assets/merci/merci.svg` canónico.
- [7.1,2.4] **7.2 UX:** Tooltips contextuales.
- [7.1,2.3] **7.3 Docs:** Página "Proyecto Mercí".
- [2.4,7.1] **7.4 Mercí Diccionario:** Tooltip interactivo para términos del Glosario.

## 8) Epic: No-tienda
- [2.x,3.x] **8.1 Catálogo:** 6-12 ítems del "archivo curioso".
- [8.1] **8.2 Narrativa:** Microhistorias.
- [1.4] **8.3 Guía WP aplicada:** Ajustar plantillas WP a `docs/08-wordpress-integracion.md`.

## 9) Epic: Laboratorio
- [2.x] **9.1 Plantilla Proyecto:** `docs/06-proyecto-template.md`.
- [9.1,7.x] **9.2 Mercí Focus:** Experimento v1.

---
*Checkpoints:* ¿Está documentado? ¿Es accesible? ¿He reducido el WIP?
