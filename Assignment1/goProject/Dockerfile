# Stage 1: Build the Go application
FROM golang:1.19-alpine AS builder

# Set the working directory
WORKDIR /app

# Copy the Go code to the container
COPY main.go .

# Compile the Go application
RUN go build -o hello

# Stage 2: Create a lean runtime image
FROM alpine:latest

# Set the working directory
WORKDIR /app

# Copy the compiled binary from the builder stage
COPY --from=builder /app/hello .

# Run the binary
ENTRYPOINT ["./hello"]
