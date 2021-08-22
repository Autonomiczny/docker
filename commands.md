# Docker

## Projects
- Web App- Python
- 2 Microservices - Currency Exchange and Currency Conversion


## Registry and Repositories

- https://hub.docker.com/u/autonomiczny
- https://hub.docker.com/u/autonomiczny/web-app

# Commands

```
docker --version

docker build -t autonomiczny/web-app:1.0.0 .
docker push autonomiczny/web-app:1.0.0

docker build -t autonomiczny/web-app:2.0.0 .
docker push autonomiczny/web-app:2.0.0

docker run -d 5000:5000 autonomiczny/web-app:1.0.0
docker run -p 5000:5000 autonomiczny/web-app:2.0.0
docker logs a67705a44809
docker logs 5cd6
docker images
docker container ls
docker container ls -a
docker container stop a6770
docker run -d -p 5001:8080 autonomiczny/web-app:1.0.0
docker pull mysql
docker search mysql
docker image history autonomiczny/web-app:1.0.0
docker image history 5cd689
docker image inspect 5cd689
docker image remove mysql
docker image remove autonomiczny/web-app:1.0.0
docker container rm 3e657ae9bd16
docker container ls -a
docker container pause 832
docker container unpause 832
docker container stop 832
docker container inspect ff521fa58db3
docker container prune
docker system
docker system df
docker system info
docker system prune -a
docker top 9009722eac4d
docker stats 9009722eac4d
docker container run -p 5000:5000 -d -m 512m autonomiczny/web-app:1.0.0
docker container run -p 5000:5000 -d -m 512m --cpu-quota=50000  autonomiczny/web-app:1.0.0
docker system events

docker container stats 4faca1ea914e3e4587d1d790948ec6cb8fa34f26e900c12632fd64d4722fd59a
docker stats 42f170966ce613d2a16d7404495af7b3295e01aeb9142e1fa1762bbdc581f502


docker run -d -p 5001:5000 autonomiczny/web-app:1.0.0 ping google.com


docker run -d -p 8000:8000 --name=currency-exchange in28min/currency-exchange:0.0.1-RELEASE
docker run -d -p 8100:8100 --name=currency-conversion in28min/currency-conversion:0.0.1-RELEASE

docker network ls
docker network inspect bridge

docker run -d -p 8100:8100 --env CURRENCY_EXCHANGE_SERVICE_HOST=http://currency-exchange --name=currency-conversion --link currency-exchange in28min/currency-conversion:0.0.1-RELEASE

docker network create currency-network
docker container stop currency-exchange
docker container stop currency-conversion
docker run -d -p 8000:8000 --name=currency-exchange --network=currency-network in28min/currency-exchange:0.0.1-RELEASE
docker run -d -p 8100:8100 --env CURRENCY_EXCHANGE_SERVICE_HOST=http://currency-exchange --name=currency-conversion --network=currency-network in28min/currency-conversion:0.0.1-RELEASE

docker-compose --version
cd ../../microservices/
docker-compose up
docker-compose up -d
docker container ls
docker network ls
docker network inspect microservices_currency-compose-network
docker-compose down
docker container ls -a
docker system prune -a
docker-compose config
docker-compose images
docker-compose ps
docker-compose top

### Host Networking in Docker for Mac and Windows

- https://docs.docker.com/network/host/

>The host networking driver only works on Linux hosts, and is not supported on Docker Desktop for Mac, Docker Desktop for Windows, or Docker EE for Windows Server.

