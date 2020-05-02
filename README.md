# NodeJS app boilerplate

Simple NodeJS boilerplate to create an Express application backend.

## Docker commands
```bash
docker build -t node_demo .
docker run -p 8080:8080 -d node_demo:latest
curl -i localhost:8080
```