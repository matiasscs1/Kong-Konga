# Usa la imagen oficial de Konga
FROM pantsel/konga:latest

# Modo producción y Postgres externo
ENV NODE_ENV=production
ENV DB_ADAPTER=postgres
ENV DB_URI=${DB_URI}

# Expone el puerto de la UI
EXPOSE 1337

# Prepara esquema y arranca la app
ENTRYPOINT ["sh","-c","node ./bin/konga.js prepare --adapter $DB_ADAPTER --uri \"$DB_URI\" && npm run production"]
