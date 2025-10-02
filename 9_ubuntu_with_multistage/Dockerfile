FROM ubuntu:22.04 AS base

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

RUN apt-get update && apt-get install -y vim git

WORKDIR /app

RUN uv python install 3.12

FROM base AS development

ARG UID
ARG GID

RUN groupadd -g ${GID} devuser && \
    useradd -u ${UID} -g ${GID} -m -s /bin/bash devuser

USER devuser

RUN uv python install 3.12