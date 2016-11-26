FROM buildpack-deps:jessie-scm

# updates sources
RUN apt-get --quiet=2 --download-only update

# install libzmq
RUN apt-get install --yes libzmq3-dev pkg-config
ENV PKG_CONFIG_PATH /usr/lib/x86_64-linux-gnu/pkgconfig

# copy over api binary
COPY ./api /usr/local/bin/api

ENTRYPOINT ["api"]
