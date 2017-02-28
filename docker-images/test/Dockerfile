FROM anubot/build:latest

# install postgres
RUN apt-get install --yes postgresql postgresql-contrib && \
    /etc/init.d/postgresql start && \
    su -c 'echo ALTER USER "postgres" WITH PASSWORD '"\'pass\' | psql" postgres

ENV ANUBOT_TEST_POSTGRES="postgres://postgres:pass@localhost:5432/postgres?sslmode=disable"
