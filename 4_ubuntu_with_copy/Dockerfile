FROM ubuntu:latest

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/
WORKDIR /app
RUN uv init
COPY app.py .
