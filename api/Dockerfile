# Use official Python base image
FROM python:3.9

# Install system dependencies
RUN apt-get update && apt-get install -y \
    libgpgme11-dev \
    libdbus-1-dev \
    libsystemd-dev \
    librpm-dev \
    libcomps-dev \
    gcc \
    g++ \
    libffi-dev \
    libssl-dev \
    python3-dev \
    pkg-config \
    && apt-get clean

# Set working directory inside the container
WORKDIR /app

# Expose your API port
EXPOSE 5050

# Copy the frozen requirements file
COPY requirements.txt ./

# Install dependencies using pip
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copy the rest of your project files
COPY . .

# Run your API
CMD ["python", "main.py"]
