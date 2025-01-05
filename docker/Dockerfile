FROM ubuntu:latest

WORKDIR /vlang

RUN apt update && apt install -y \
    git \
    make \
    gcc \
    libpq-dev \
    libssl-dev \
    libsqlite3-dev \
    build-essential \
    wget \
    unzip

ENV V_VERSION=0.4.9
RUN wget https://github.com/vlang/v/releases/download/${V_VERSION}/v_linux.zip \
    && unzip v_linux.zip \
    && cd ./v \
    && ./v symlink

WORKDIR /app

COPY v.mod v.mod
RUN v install

COPY . .

CMD ["v", "run", "."]
