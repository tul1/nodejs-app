# NodeJS app boilerplate

Simple NodeJS boilerplate to create an Express application backend.

## Docker commands
```bash
docker build -t node_demo .
docker run -p 8080:8080 -d node_demo:latest
curl -i localhost:8080
```

## Run it in your local environment
```bash
npm install
npm start
curl -i localhost:8080
```

## Developpment tool like linting and testing
Linting is preset to follow [airbnb](https://github.com/airbnb/javascript) code style and you'll just have to run the following:
```bash
npm lint
```

And to run your test type following:
```bash
npm test
```

## References
- [Express](https://nodejs.org/fr/docs/guides/nodejs-docker-webapp/)
