FROM golang:latest

# install migrate tool
RUN mkdir /tmpworkspace && \
    GOPATH=/tmpworkspace go get github.com/mattes/migrate && \
    mv /tmpworkspace/bin/migrate /usr/bin/ && \
    rm -r /tmpworkspace

CMD ["migrate", "up"]

RUN mkdir /migrations
WORKDIR /migrations

COPY migrations/*.sql /migrations/
