FROM kong:3.6

# Configuración de Postgres en Render
ENV KONG_DATABASE=postgres
ENV KONG_PG_HOST=${KONG_PG_HOST}
ENV KONG_PG_PORT=${KONG_PG_PORT}
ENV KONG_PG_USER=${KONG_PG_USER}
ENV KONG_PG_PASSWORD=${KONG_PG_PASSWORD}
ENV KONG_PG_DATABASE=${KONG_PG_DATABASE}

# Logs a stdout/stderr
ENV KONG_PROXY_ACCESS_LOG=/dev/stdout
ENV KONG_ADMIN_ACCESS_LOG=/dev/stdout
ENV KONG_PROXY_ERROR_LOG=/dev/stderr
ENV KONG_ADMIN_ERROR_LOG=/dev/stderr

# Exponer puertos
EXPOSE 8000 8443 8001 8444




# Opción B: sin entrypoint oficial, usando `kong start`
ENTRYPOINT ["sh","-c","kong migrations bootstrap && kong start"]
