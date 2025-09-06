# === Stage 1: Builder ===
FROM python:3.11-slim AS builder

WORKDIR /app

# Install build dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential gcc \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy project files (app.py + models)
COPY . .

# === Stage 2: Runtime ===
FROM python:3.11-slim

WORKDIR /app

# Copy installed packages + app from builder
COPY --from=builder /usr/local /usr/local
COPY --from=builder /app /app

# Expose port
EXPOSE 8080

# Run FastAPI
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8080"]
