# Bookinfo Rating Service

Rating service has been developed on NodeJS

## License

MIT License

## How to run

```bash
node ratings.js 8080
```
## How to run with Docker Compose

```bash
docker-compose up
```

## How to run MongoDB

```bash
docker run -d --name mongodb -p 27017:27017 \
  -v ~/ratings/databases:/docker-entrypoint-initdb.d bitnami/mongodb:5.0.2-debian-10-r2
```

## How to run with Docker

```bash
# Build Docker Image for ratings service
docker build -t ratings .

# Run ratings service on port 8080
docker run -d --name ratings -p 8080:8080 --link mongodb:mongodb \
  -e SERVICE_VERSION=v2 -e 'MONGO_DB_URL=mongodb://mongodb:27017/ratings' ratings
```

## Website

[Opsta (Thailand) Co., Ltd.](https://www.opsta.co.th)