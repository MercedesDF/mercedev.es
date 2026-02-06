# 07-operaciones-it.md · Infraestructura

## 🌐 Servidor Producción
- **IP:**  DEPLOY_HOST(DigitalOcean Droplet)
- **OS:** Ubuntu (WordPress Marketplace)
- **Path Destino:** `/var/www/html`

## 🔐 Seguridad de Acceso
- Acceso vía llave SSH `ed25519` dedicada (`id_rsa_github_mercedev`).
- Secretos en GitHub: `DEPLOY_HOST`, `DEPLOY_USER`, `DEPLOY_KEY`.

## 🛡️ Protocolo de Calidad (QA)
El flujo de GitHub Actions es:
1. **Linting** -> 2. **Security Check** -> 3. **Tests (Acc/Links)** -> 4. **Deploy**.
*Si falla cualquier paso previo, el rsync no se ejecuta.*

## 🔄 Estrategia de Despliegue
- **Herramienta:** `rsync` sobre SSH.
- **Frecuencia:** Automática al hacer push a `main`.

## 🧩 Integración WordPress / Tienda
- Lineamientos mínimos: ver `docs/08-wordpress-integracion.md`.
- Registrar en este archivo los cambios de tema/plantillas y resultados Lighthouse relacionados con WP.

## 🧪 CI/CD pendiente
- Workflow en `.github/workflows` por crear. Debe incluir:
  1) Linting (HTML/CSS/Markdown)
  2) Security scan (secretos y dependencias)
  3) Tests automatizados: accesibilidad (Axe/Lighthouse CI), link checker, smoke de páginas críticas
  4) Deploy por `rsync` solo si todo lo anterior pasa
