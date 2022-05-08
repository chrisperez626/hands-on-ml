FROM conda/miniconda3:latest

WORKDIR /usr/src/app

ENV SHELL "zsh"
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt-get update && apt-get install -y \
    curl \
    wget \
    vim \
    git \
    build-essential \
    libssl-dev \
    libffi-dev
RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.2/zsh-in-docker.sh)"

COPY ../environment.yml .

RUN conda env create -f envrionment.yml

COPY . /usr/src/app