# Use a imagem oficial do OpenJDK com a versão LTS (ex: OpenJDK 17)
FROM openjdk:17-jdk-slim

# Instalar Maven
RUN apt-get update && apt-get install -y maven

# Instalar o JDK (Java Development Kit)
RUN apt-get update && apt-get install -y default-jdk

# Criar diretório de trabalho
WORKDIR /workspace
