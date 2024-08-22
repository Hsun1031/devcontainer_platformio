FROM mcr.microsoft.com/devcontainers/python:3.11

RUN pip3 install -U platformio
RUN pio upgrade
RUN pio remote update || true

RUN wget https://github.com/esp-rs/esp-web-flash-server/releases/download/v0.2.1/web-flash-x86_64-unknown-linux-gnu.zip && \
    unzip web-flash-x86_64-unknown-linux-gnu.zip && \
    mv web-flash /usr/local/bin/ && \
    rm web-flash-x86_64-unknown-linux-gnu.zip