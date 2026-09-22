FROM python:3.13-slim

# Prevent Python from creating .pyc files
ENV PYTHONDONTWRITEBYTECODE=1

# Make Python output appear immediately
ENV PYTHONUNBUFFERED=1

# Working directory inside the container
WORKDIR /workspace

# Install useful system tools
RUN apt-get update && apt-get install -y \
    build-essential \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Upgrade pip
RUN pip install --upgrade pip

# Copy requirements.txt into the image
COPY requirements.txt /tmp/requirements.txt

# Install all Python libraries
RUN pip install --no-cache-dir -r /tmp/requirements.txt