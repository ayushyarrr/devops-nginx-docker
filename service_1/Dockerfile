# Dockerfile for service_1 (Go app)
FROM golang:1.20-alpine

# ✅ Install curl for healthcheck
RUN apk add --no-cache curl

WORKDIR /app

COPY . .

RUN go build -o main main.go

EXPOSE 8001

CMD ["./main"]
