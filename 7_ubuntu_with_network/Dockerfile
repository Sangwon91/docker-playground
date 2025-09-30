FROM ubuntu:latest

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

RUN apt-get update && apt-get install -y vim

WORKDIR /app

ARG UID
ARG GID

RUN groupadd -g ${GID} devuser && \
    useradd -u ${UID} -g ${GID} -m -s /bin/bash devuser

USER devuser

RUN uv python install 3.12
