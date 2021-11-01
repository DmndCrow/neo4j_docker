# Neo4j

This project lets you install **Neo4j** database using docker service.

## Prerequisites

Make sure you have installed these:
- [Docker and Docker Compose](https://phoenixnap.com/kb/install-docker-compose-on-ubuntu-20-04) - Will install all the required packages and software.


## Installation

Make a copy of `.env.example` file named `.env`

```shell script
cp .env.example .env
```

---

Environment variables:
- **Neo4j** settings:
    - `IMAGE_TAG` - **Neo4j** image tag
    - `NEO4J_PASSWORD` - password for default user
    - `UI_PORT` - port on which user interface of **Neo4j** instance will be running.
    - `DB_PORT` - port, on which **Neo4j** instance will be running.
- `DATABASE_NETWORK` - network, on which our database will be accessible.

```dotenv
# Neo4j settings
IMAGE_TAG=4.1.8
NEO4J_PASSWORD=password
UI_PORT=7474
DB_PORT=7687

# Network settings
DATABASE_NETWORK=database_network
```

---

Create network with the name, that we have in `DATABASE_NETWORK` environment variable.

```shell script
docker network create database_network
```

---

Build the Docker image

```shell script
docker-compose build
```

## Running

Start
```
docker-compose up
```

Stop
```
docker-compose down
```

## Usage

- Access **Neo4j** interface instance through  `localhost:UI_PORT` from browser.
