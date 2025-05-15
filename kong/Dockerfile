# ─────────────────────────────────────────────────
# Dockerfile para desplegar KONG en producción
# ─────────────────────────────────────────────────
FROM kong:3.6

# Conecta Kong con tu Postgres de Render:
ENV KONG_DATABASE=postgres
ENV KONG_PG_HOST=${KONG_PG_HOST}
ENV KONG_PG_PORT=${KONG_PG_PORT}
ENV KONG_PG_USER=${KONG_PG_USER}
ENV KONG_PG_PASSWORD=${KONG_PG_PASSWORD}
ENV KONG_PG_DATABASE=${KONG_PG_DATABASE}

# Logs a stdout/stderr para que Render los capture:
ENV KONG_PROXY_ACCESS_LOG=/dev/stdout
ENV KONG_ADMIN_ACCESS_LOG=/dev/stdout
ENV KONG_PROXY_ERROR_LOG=/dev/stderr
ENV KONG_ADMIN_ERROR_LOG=/dev/stderr

# Exponer los puertos de proxy y Admin API:
EXPOSE 8000 8443 8001 8444

# Al arrancar: aplica migraciones y luego inicia Kong en modo Docker
ENTRYPOINT ["sh","-c","kong migrations bootstrap && kong docker-start"]
