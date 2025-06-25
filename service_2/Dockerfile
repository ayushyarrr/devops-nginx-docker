# Dockerfile for service_2 (Python app)
FROM python:3.13-slim

# ✅ Make apt more reliable and silent
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY . .

RUN pip install --upgrade pip
RUN pip install .

EXPOSE 8002

CMD ["python", "app.py"]
