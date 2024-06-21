FROM postgres:15.1-alpine


RUN apk add --no-cache icu-libs musl-locales


ENV POSTGRES_DB=my_client_docker
ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=superuser

# Создаем настройки локали en_US.UTF-8
RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    mkdir -p /usr/share/i18n/locales && \
    echo -e "LC_MESSAGES\nLC_IDENTIFICATION\nLC_COLLATE\nLC_CTYPE" > /usr/share/i18n/locales/en_US.UTF-8 && \
    echo -e "lang_name \"C.UTF-8\"\ncharmap \"UTF-8\"" >> /usr/share/i18n/locales/en_US.UTF-8


ENV LANG=en_US.UTF-8


RUN touch /docker-entrypoint-initdb.d/init.sql

# Даем все привилегии для базы данных
RUN echo "GRANT ALL PRIVILEGES ON DATABASE ${POSTGRES_DB} TO ${POSTGRES_USER};" > /docker-entrypoint-initdb.d/init.sql

VOLUME /var/lib/postgresql/data

EXPOSE 5432


CMD ["postgres"]
