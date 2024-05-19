# Use official OpenJDK image with
FROM openjdk:21-jdk-slim

# Install Maven
RUN apt-get update && apt-get install -y maven

# Install JDK (Java Development Kit)echo 'export JAVA_HOME=/usr/local/openjdk-21' >> ~/.bashrc
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

# Configure PATH
ENV MAVEN_HOME=/usr/share/maven
ENV PATH=${MAVEN_HOME}/bin:${PATH}

# Set JDK installation directory
ENV JAVA_HOME /usr/local/openjdk-21

# Update PATH to include JDK binary
ENV PATH $JAVA_HOME/bin:$PATH

# Create working directory
WORKDIR /workspace

# Add contents from current directory to the container
COPY . /workspace
