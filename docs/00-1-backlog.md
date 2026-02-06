# 00-1-backlog.md · mercedev.es (Sincronizado)

## 0) Marco Scrum Operativo
**Roles:** PO (Prioridades), SM (Foco/WIP), Dev (Implementación).
**Cadencia:** Sprints de 1 semana.
**DoD Global:** Mobile-first, accesible (Lighthouse), sin secretos, errores manejados, docs en `/docs`.

---

## 1) Epic: Repo como “fuente de verdad” (Base)
- [ ] **1.1 Repo inicial:** `/src`, `/public`, `/docs`, `/scripts`, `/.github/workflows`.
- [ ] **1.2 Seguridad:** `.gitignore` robusto.
- [ ] **1.3 Docs base:** README.md, `docs/00-0-intencion.md` y `docs/00-03-paradigmas.md`.

## 2) Epic: Documentación Desbloqueadora (Pre-Código)
- [ ] **2.1 Mapa Web:** `docs/01-mapa-web.md`.
- [ ] **2.2 Biblioteca Conceptual:** `docs/02-biblioteca.md` (Categorías/Colores + Carpeta).
- [ ] **2.3 Mercí v0:** `docs/03-merci-v0.md` (Contrato de comportamiento).
- [ ] **2.4 Datos Glosario:** Crear `src/data/glosario.json` con los primeros 10 términos.

## 3) Epic: Web v1 “Funcional”
- [ ] **3.1 Arquitectura:** `docs/04-home-estructura.md`.
- [ ] **3.2 Implementación:** Home + 5 páginas base (HTML/CSS).
- [ ] **3.3 Componente Biblioteca:** Visual v1 (Semántica alineada).
- [ ] **3.4 Componente Carpeta:** Vista alternativa "Índice con pestañas" (5 Tabs CSS: Ocre, Azul, Verde, Naranja, Negro).

## 4) Epic: Calidad Automática (QA) - *EL PORTERO*
*Sin esto, no hay deploy seguro.*
- [ ] **4.1 Linter:** Configurar `markdownlint` y `htmlhint`.
- [ ] **4.2 Accessibility Test:** Integrar `axe-core`.
- [ ] **4.3 Link Checker:** Script anti-404.
- [ ] **4.4 Smoke Test:** Verificación de status 200.

## 5) Epic: Publicación y CI/CD
- [ ] **5.1 Mirror:** Deploy a GitHub Pages.
- [ ] **5.2 GH Secrets:** Configurar `DEPLOY_HOST`, `DEPLOY_USER`, `DEPLOY_KEY`.
- [ ] **5.3 Pipeline Producción:** GitHub Action + `rsync` hacia Droplet (178.128.47.178).

## 6) Epic: Cuaderno de Bitácora
- [ ] **6.1 Plantilla:** `docs/05-Cuaderno-de-Bitacora-template.md`.
- [ ] **6.2 Semilla:** 5 posts iniciales.
- [ ] **6.3 LinkedIn:** Automatización RSS/Webhook.

## 7) Epic: Mercí (Identidad)
- [ ] **7.1 SVG:** `assets/merci/merci.svg` canónico.
- [ ] **7.2 UX:** Tooltips contextuales.
- [ ] **7.3 Docs:** Página "Proyecto Mercí".
- [ ] **7.4 Mercí Diccionario:** Tooltip interactivo para términos del Glosario.

## 8) Epic: No-tienda
- [ ] **8.1 Catálogo:** 6-12 ítems del "archivo curioso".
- [ ] **8.2 Narrativa:** Microhistorias.

## 9) Epic: Laboratorio
- [ ] **9.1 Plantilla Proyecto:** `docs/06-proyecto-template.md`.
- [ ] **9.2 Mercí Focus:** Experimento v1.

---
*Checkpoints:* ¿Está documentado? ¿Es accesible? ¿He reducido el WIP?
