# 07-operaciones-it.md · Infraestructura y Operaciones

Este documento describe la infraestructura, el acceso seguro, la estrategia de despliegue y el registro operativo de cambios (especialmente WordPress), para que el proyecto sea **audit-able** y **repetible**.

---

## 1) 🌐 Entornos y servidor

### Producción (PROD)
- **Proveedor:** DigitalOcean (Droplet + cloudPanel / WordPress Marketplace)
- **OS:** Ubuntu
- **Host PROD:** gestionado por secreto `DEPLOY_HOST` (no se publica en docs)
- **Usuario deploy:** gestionado por secreto `DEPLOY_USER`
- **Destino web:** `/var/www/html`

> Nota: Evitar publicar IP/host en repos públicos. Se gestiona por secretos y panel del proveedor.

### Staging (opcional, recomendado)
- Si se habilita un staging, se documenta aquí:
  - **Host STG:** `STAGING_HOST` (secreto)
  - **Destino STG:** `/var/www/staging` (ejemplo)
  - Regla: cambios de tema/plantillas WP pasan por STG antes de PROD.

---

## 2) 🔐 Acceso y autenticación

### SSH
- **Tipo de clave:** `ed25519`
- **Nombre recomendado:** `id_ed25519_mercedev` y `id_ed25519_mercedev.pub`
- **Uso:** acceso por SSH al servidor y despliegue automatizado por CI.

### Secretos (GitHub)
- `DEPLOY_HOST` → host producción (o IP, si aplica)
- `DEPLOY_USER` → usuario del servidor para despliegue
- `DEPLOY_KEY` → clave privada SSH (ed25519) en formato texto
- (Opcional) `DEPLOY_PORT` → puerto SSH si no es 22

### Reglas mínimas
- Prohibido commitear `.env`, claves, tokens o credenciales.
- Acceso por contraseña deshabilitado si es posible (solo llave).
- Usuarios WP: mínimos necesarios, roles revisados.

---

## 3) 🧩 WordPress / “No-tienda” (integración)

- **Lineamientos mínimos:** ver `docs/08-wordpress-integracion.md`.
- **Enfoque “No-tienda”:** catálogo + microhistorias + checkout simulado claro (sin compra real salvo decisión explícita).
- **Regla de oro:** cualquier cambio que afecte a tema/plantillas/bloques/plugins o rendimiento/accesibilidad **se registra** en este documento (sección 7).

---

## 4) 🛡️ Protocolo de calidad (QA) y release

### Objetivo del pipeline
Evitar despliegues rotos: **si falla cualquier paso, NO se despliega**.

### Orden de fases (CI)
1. **Linting**
2. **Security check**
3. **Tests automatizados (Acc/Links/Smoke)**
4. **Deploy**

### Qué valida cada fase (mínimo)
- **Linting**
  - HTML: validación/estilo (si aplica)
  - CSS/SCSS: lint básico
  - Markdown: enlaces rotos / formato
- **Security check**
  - Escaneo de secretos (gitleaks o similar)
  - Dependencias (npm audit / osv / similar, según stack)
- **Tests**
  - Accesibilidad: axe / lighthouse-ci (mínimo en páginas críticas)
  - Link checker (internos y externos clave)
  - Smoke: carga de home + 2-3 rutas críticas

---

## 5) 🔄 Estrategia de despliegue (CI/CD)

### Método
- **Herramienta:** `rsync` sobre SSH
- **Trigger:** push a `main`
- **Condición:** solo si pasan lint + security + tests

### Destino
- **Ruta destino:** `/var/www/html`
- **Formato destino:** `DEPLOY_USER@DEPLOY_HOST:/var/www/html`

### Reglas de despliegue
- No subir archivos sensibles (`.env`, claves, etc.).
- No subir carpetas pesadas innecesarias (ej: `node_modules/`, `dist/` si no aplica).
- El deploy debe ser **idempotente** (repetible sin romper).

---

## 6) 🧪 CI/CD pendiente (estado y requisitos)

### Ubicación
- `.github/workflows/` (por crear)

### Requisitos del workflow (mínimo viable)
1) Linting (HTML/CSS/Markdown)  
2) Security scan (secretos + dependencias)  
3) Tests: accesibilidad (axe/lighthouse-ci), link checker, smoke de páginas críticas  
4) Deploy por `rsync` **solo** si todo lo anterior pasa

> Cuando el workflow exista, se añade aquí el nombre del archivo y un resumen de variables/artefactos.

---

## 7) 🧾 Registro de cambios WordPress (tema/plantillas/ajustes)

**Regla:** todo cambio que afecte a UX, rendimiento, accesibilidad o plantilla WP se registra aquí.

### Plantilla de entrada (copiar/pegar)
- **Fecha (ISO):** YYYY-MM-DD
- **Entorno:** Producción / Staging
- **Cambio:** (qué se hizo, 1–2 líneas)
- **Motivo:** (por qué)
- **Alcance:**
  - tema / child-theme / plantilla (`front-page`, `single`, `page`, `archive`, `404`, `search`)
  - bloque / plugin / settings
- **Riesgo:** bajo / medio / alto
- **Rollback:** (cómo deshacerlo)
- **Lighthouse (móvil):**
  - Antes: Perf __ / Acc __ / BP __ / SEO __
  - Después: Perf __ / Acc __ / BP __ / SEO __
- **Notas:** incidencias, dependencias, follow-ups

### Entradas
- _(aún sin entradas)_

---

## 8) 🧯 Incidencias y recuperación (mínimo)

### Si el deploy rompe algo
1. **Parar cambios:** no volver a hacer push a `main` hasta entender el fallo.
2. **Identificar commit:** `git log --oneline -5`
3. **Rollback de contenido (si procede):**
   - Revertir commit: `git revert <hash>`
   - Push y redeploy (solo si el pipeline pasa)
4. **Registrar incidencia:** en esta sección o en `docs/XX-incidencias.md` si crece.

### Política de rollback WP
- Si el cambio fue en WP (panel/tema/plugin), registrar:
  - qué se tocó
  - cómo se revierte
  - impacto Lighthouse antes/después

---

## 9) ✅ Checklist operacional (antes de un cambio relevante)

- [ ] `git status` limpio antes de push final
- [ ] No hay secretos en el diff
- [ ] Accesibilidad: foco visible, teclado OK
- [ ] Imágenes optimizadas (peso razonable)
- [ ] Lighthouse móvil registrado si toca tema/plantillas
- [ ] Registro WP actualizado (si aplica)

---

## 10) Referencias internas
- `docs/08-wordpress-integracion.md` — lineamientos mínimos de WP
- `docs/00-03-paradigmas.md` — anotar cambios que afecten a filosofía/paradigmas
- `README.md` — visión general, estructura y principios
