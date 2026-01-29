# 07-operaciones-it.md · Infraestructura

## 🌐 Servidor Producción
- **IP:** 178.128.47.178 (DigitalOcean Droplet)
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