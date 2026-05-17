# TP05 — Docker: primera app en contenedor
 
## Qué contiene
 
API Python con framework Flask corriendo en Docker, con buenas prácticas de producción.
 
## Endpoints
 
| Ruta | Descripción |
|---|---|
| `GET /` | Status de la app |
| `GET /health` | Uptime, hostname, entorno |
| `GET /info` | Versión y metadata |

## Correr localmente
Ejecutar en bash
docker run -d -p 8080:5000 TU_USUARIO/devops-portfolio:latest
curl http://localhost:8080/health

## Buenas prácticas aplicadas

- Uso de `python:3.12-slim` en lugar de `python:3.12`
  - Imagen aproximadamente 6 veces más liviana.

- `COPY requirements.txt` antes del código fuente
  - Optimización de caché de capas en Docker.

- Uso de `pip install --no-cache-dir`
  - Reduce el tamaño final de la imagen.

- Implementación de usuario no-root (`appuser`)
  - Mejora la seguridad del contenedor.

- Uso de `gunicorn` en lugar de `flask run`
  - Servidor preparado para producción.

- Variables de entorno para configuración dinámica
  - Facilita despliegues en distintos entornos.
## Imagen en Docker Hub
docker pull TU_USUARIO/devops-portfolio:latest
