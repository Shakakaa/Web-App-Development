# Stage 1: Build the Go application
FROM golang:1.19-alpine AS builder

# Set the working directory
WORKDIR /app

# Copy go.mod and go.sum (if exists) first to leverage Docker layer caching
COPY go.mod .

# Download dependencies
RUN go mod download

# Copy the rest of the application code
COPY . .

# Compile the Go application
RUN go build -o hello

# Stage 2: Create a minimal image to run the app
FROM alpine:latest

WORKDIR /app

# Copy the compiled binary from the builder stage
COPY --from=builder /app/hello .

# Run the application
ENTRYPOINT ["./hello"]
