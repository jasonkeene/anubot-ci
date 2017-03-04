FROM anubot/build:latest

# install postgres
RUN apt-get install --yes postgresql postgresql-contrib && \
    /etc/init.d/postgresql start && \
    su -c 'echo ALTER USER "postgres" WITH PASSWORD '"\'pass\' | psql" postgres && \
    mkdir /tmpworkspace && \
    GOPATH=/tmpworkspace go get github.com/mattes/migrate && \
    mv /tmpworkspace/bin/migrate /usr/bin/ && \
    rm -r /tmpworkspace

ENV ANUBOT_TEST_POSTGRES="postgres://postgres:pass@localhost:5432/postgres?sslmode=disable"
