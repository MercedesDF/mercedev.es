# 00-1-backlog.md · mercedev.es

## 0) Marco Scrum Operativo
**Roles:** PO (Prioridades), SM (Foco/WIP), Dev (Implementación).
**Cadencia:** Sprints de 1 semana.
**DoD Global:** Mobile-first, accesible, sin secretos, errores manejados, documentado en `/docs`, README actualizado.

---

## 1) Epic: Repo como “fuente de verdad” (Base)
- [ ] **1.1 Repo inicial:** Estructura `/src`, `/public`, `/docs`, `/scripts`, `/.github/workflows`.
- [ ] **1.2 Seguridad:** `.gitignore` configurado.
- [ ] **1.3 Documentos base:** README.md y `docs/00-0-intencion.md`.

## 2) Epic: Documentación Desbloqueadora (Pre-Código)
- [ ] **2.1 Mapa Web:** `docs/01-mapa-web.md` (secciones cerradas).
- [ ] **2.2 Biblioteca Conceptual:** `docs/02-biblioteca.md` (semántica y categorías).
- [ ] **2.3 Mercí v0:** `docs/03-merci-v0.md` (contrato de comportamiento y tono).

## 3) Epic: Web v1 “Funcional”
- [ ] **3.1 Arquitectura:** `docs/04-home-estructura.md` (recorrido de navegación).
- [ ] **3.2 Implementación Estática:** Estructura HTML/CSS para las 6 páginas principales.
- [ ] **3.3 Componente Biblioteca:** Implementación visual v1.

## 4) Epic: Publicación y CI/CD (DigitalOcean + Pages)
- [ ] **4.1 Pipeline Mirror:** Deploy automático a GitHub Pages.
- [ ] **4.2 Secretos de Despliegue:** Configurar `DEPLOY_HOST`, `DEPLOY_USER` y `DEPLOY_KEY` en GH Secrets.
- [ ] **4.3 Pipeline Producción:** GitHub Action con `rsync` hacia el Droplet (178.128.47.178).
- [ ] **4.4 Registro IT:** Finalizar `docs/07-operaciones-it.md`.

## 5) Epic: Calidad Automática (QA/Tests)
*Esta Epic bloquea el paso 4.3.*
- [ ] **5.1 Linters:** Configurar `markdownlint` y `htmlhint` en el workflow.
- [ ] **5.2 Accessibility Test:** Integrar `axe-core` en el pipeline.
- [ ] **5.3 Integrity:** Link Checker + Smoke Test (status 200).

## 6) Epic: Cuaderno de Bitácora
- [ ] **6.1 Plantilla:** `docs/05-Cuaderno-de-Bitacora-template.md`.
- [ ] **6.2 Semilla:** 5 posts iniciales (Art de Coté, Iteración, Prevención...).
- [ ] **6.3 LinkedIn:** Automatización de publicación vía RSS/Webhook.

## 7) Epic: Mercí (Presencia)
- [ ] **7.1 Identidad:** `assets/merci/merci.svg` canónico.
- [ ] **7.2 Interacciones:** Tooltips contextuales (sin IA).
- [ ] **7.3 Roadmap:** Página "Proyecto Mercí".

## 8) Epic: No-tienda
- [ ] **8.1 Catálogo:** Selección de 6-12 ítems conceptuales.
- [ ] **8.2 Narrativa:** Microhistorias técnicas por ítem.

## 9) Epic: Laboratorio
- [ ] **9.1 Plantilla Proyecto:** `docs/06-proyecto-template.md`.
- [ ] **9.2 Mercí Focus:** Inicio del primer experimento.

---
*Checkpoints de control:* ¿Es publicable? ¿Hay decisión nueva en /docs? ¿WIP limitado?