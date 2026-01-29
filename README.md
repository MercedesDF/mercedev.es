# mercedev.es

Biblioteca profesional viva: código + documentación del proceso.
La web publicada es el resultado; este repositorio es la fuente de verdad.

## 📂 Estructura
- `/src`: Código fuente.
- `/public`: Salida lista para publicar.
- `/docs`: Decisiones, mapa web, backlog y errores resueltos.
- `/scripts`: Automatizaciones (zsh).
- `/assets/originals`: Originales sin optimizar (ignorado por git).

## 🛠️ Principios
- **Mobile first + Responsive.**
- **Accesibilidad:** (Lighthouse / axe-core).
- **JS mínimo:** Enfocado en la funcionalidad.
- **Seguridad:** Secretos en `.env` y fuera del repo.

## 📐 Arquitectura y decisiones
Este repositorio es la **fuente de verdad** del proyecto.

Decisiones clave documentadas:
1. [Documento de Intención](./docs/00-0-intencion.md)
2. [Backlog Operativo](./docs/00-1-backlog.md)
3. [Mapa Web](./docs/01-mapa-web.md) — Scope y secciones.
4. [Biblioteca y Semántica](./docs/02-biblioteca.md) — Colores, índice y glosario.
5. [Operaciones IT](./docs/07-operaciones-it.md) — Infraestructura, Droplet y Pipeline de despliegue.

## 🚀 Estado del Despliegue
- [ ] **Producción (DigitalOcean):** 🏗️ Configurando Pipeline de despliegue.
- [ ] **Mirror Técnico (GitHub Pages):** 🏗️ Pendiente de Action inicial.

## ⚙️ CI/CD y Calidad (Pipeline de Prevención)
Cada push a `main` disparará este flujo obligatorio:
1. **Linting:** Validación de sintaxis (HTML/CSS/Markdown).
2. **Security Scan:** Verificación de secretos expuestos y dependencias.
3. **Automated Tests:** - ✅ Accesibilidad (Axe Core / Lighthouse CI).
   - ✅ Link Checker (verificación de enlaces rotos).
   - ✅ Smoke Tests (validación de carga de páginas críticas).
4. **Deploy:** Vía SSH + rsync solo si los 3 pasos anteriores devuelven "PASS".
