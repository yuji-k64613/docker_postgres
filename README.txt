# https://hub.docker.com/_/postgres/
docker build -t yuji/postgres .
docker run -d --name some-postgres -p 5432:5432 -v "${PWD}/data":/var/lib/postgresql/data yuji/postgres
docker exec -it $(docker ps | grep postgres | awk '{print $1}') /bin/bash
psql -h localhost -U postgres
