# Use a imagem oficial do OpenJDK com a versão LTS (ex: OpenJDK 17)
FROM openjdk:21-jdk-slim

# Instalar Maven
RUN apt-get update && apt-get install -y maven

# Instalar o JDK (Java Development Kit)
RUN apt-get update && apt-get install -y default-jdk

# Install basic tools
RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    htop \
    nano \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Configure git
RUN git config --global user.name "Tales"
RUN git config --global user.email "dev.tj@protonmail.com"
RUN git config --global credential.helper cache
RUN git config --global credential.helper store
RUN git config --global --add safe.directory /workspace

# Configurar o PATH para Maven e Node.js
ENV MAVEN_HOME=/usr/share/maven
ENV PATH=${MAVEN_HOME}/bin:${PATH}

# Criar diretório de trabalho
WORKDIR /workspace

# Adicionar o conteúdo do diretório atual ao container
COPY . /workspace