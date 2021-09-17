# Hume Workshop 2021

## Requirements

Laptop with minumum 6GB of RAM dedicated to the Docker engine ( MAC -> https://docs.docker.com/desktop/mac/#resources, Windows -> https://docs.docker.com/desktop/windows/#resources)

## Installation

1. Clone this repository
2. Login with your docker credentials `docker login docker.graphaware.com`

This package contains the following softwares : 

- Neo4j Enterprise Edition
- Hume Core
- Elasticsearch and Kibana

Trying to launch all the above at the same time could be problematic depending on your laptop hardware.

**Launch first the Neo4j containers:**

```shell
docker-compose --profile neo4j up -d
```

Monitor the logs until there is no more activity , CTRL-C for exiting logs

```shell
docker-compose logs --tail 100 -f
```

**Launch then the Hume containers:**

```shell
docker-compose --profile hume up -d
```

Hume and Neo4j will be up and running : 

- Hume : localhost:8081 , login : `admin@hume.ga` / password : `password`
- Neo4j : localhost:7474, login : `neo4j` / password : `password`

Neo4j and Hume will be populated with the movies graph.

**Optionally launch the Elasticsearch and Kibana containers:**

```shell
docker-compose --profile elastic up -d
```

