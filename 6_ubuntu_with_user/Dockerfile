FROM ubuntu:22.04

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

WORKDIR /app

ARG UID
ARG GID

RUN groupadd -g ${GID} devuser && \
    useradd -u ${UID} -g ${GID} -m -s /bin/bash devuser

USER devuser
