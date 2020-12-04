FROM composer:2.0

ARG GID
ARG GROUP
ARG UID
ARG USER
ARG WORKDIR

RUN set -eux; \
    addgroup -g ${GID} ${GROUP}; \
    adduser -D -g ${GID} -G ${GROUP} -s /bin/sh -u ${UID} ${USER}; \
    mkdir -p ${WORKDIR}; \
    chown ${UID}:${GID} ${WORKDIR}
