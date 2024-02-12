# Use an official Debian-based image as a parent image
FROM debian:latest

# Install dependencies
RUN apt-get update && apt-get install -y \
    wget \
    unzip \
    libgl1-mesa-dev \
    libxrandr-dev \
    libxinerama-dev \
    libxcursor-dev \
    libxi-dev \
    libasound2-dev

# Download and extract Amulet
RUN wget -O amulet.zip https://github.com/ianmaclarty/amulet/releases/download/v1.21.10/amulet-v1.21.10-linux.zip && \
    unzip amulet.zip && \
    mkdir amulet && \
    cd amulet-v1.21.10 && \
    mv * ../amulet && \
    cd .. && \
    rmdir amulet-v1.21.10 && \\
    rm amulet.zip

# Add Amulet binaries to PATH
ENV PATH="/amulet/bin:${PATH}"

# Set the working directory in the container to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app
