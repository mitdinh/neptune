FROM python:3.11-slim

WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy agent package
COPY . /app

# Cloud Run listens on PORT
ENV PORT=8080
EXPOSE 8080

# ADK provides the web server + Dev UI
CMD ["sh", "-c", "adk web --host 0.0.0.0 --port ${PORT} /app"]
