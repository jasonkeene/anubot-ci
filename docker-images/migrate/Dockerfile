FROM golang:latest

RUN mkdir /migrations
WORKDIR /migrations
COPY migrations/*.sql /migrations/

# install migrate tool
RUN mkdir /tmpworkspace && \
    GOPATH=/tmpworkspace go get github.com/mattes/migrate && \
    mv /tmpworkspace/bin/migrate /usr/bin/ && \
    rm -r /tmpworkspace

CMD ["migrate", "up"]
