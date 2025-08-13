# Go API

A simple REST API built with Go and the Gin web framework.

## Features

- RESTful API endpoints
- JSON responses
- Lightweight and fast
- Docker support

## API Endpoints

- `GET /` - Returns a welcome message
- `GET /tasks` - Returns a list of tasks

## Prerequisites

- Go 1.24.6 or later
- Docker (optional, for containerized deployment)

## Local Development

### Running with Go

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd go-api
   ```

2. Install dependencies:
   ```bash
   go mod download
   ```

3. Run the application:
   ```bash
   go run main.go
   ```

4. The API will be available at `http://localhost:8080`

### Testing the API

```bash
# Test the root endpoint
curl http://localhost:8080/

# Test the tasks endpoint
curl http://localhost:8080/tasks
```

## Docker Deployment

### Building the Docker Image

```bash
docker build -t go-api .
```

### Running the Container

```bash
docker run -p 8080:8080 go-api
```

### Docker Compose (Optional)

Create a `docker-compose.yml` file:

```yaml
version: '3.8'
services:
  api:
    build: .
    ports:
      - "8080:8080"
    restart: unless-stopped
```

Run with:
```bash
docker-compose up -d
```

## Project Structure

```
.
├── main.go          # Main application file
├── go.mod           # Go module file
├── go.sum           # Go dependencies checksum
├── Dockerfile       # Docker configuration
├── .dockerignore    # Docker ignore file
└── README.md        # This file
```

## Dependencies

- [Gin](https://github.com/gin-gonic/gin) - HTTP web framework

### Building for Production

```bash
CGO_ENABLED=0 GOOS=linux go build -o main .
```

## License

This project is open source and available under the [MIT License](LICENSE).
