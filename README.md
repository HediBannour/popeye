# Popeye

Containerisation of a microservice voting app with Docker: a Python/Flask poll page writes votes to Redis, a Java worker copies them to PostgreSQL, and a Node.js page shows the results live. The application code was provided; the containerisation is mine.

- **Team:** solo project
- **My part:** three Dockerfiles (including a multi-stage Maven build for the worker) and the docker-compose: networks, volume, restart.

## Run

Requirements: Docker with Docker Compose.

```sh
export POSTGRES_PASSWORD=choose-a-password   # optional, defaults to "changeme"
docker compose up --build
```

Vote on http://localhost:5000, see results on http://localhost:5001.

Note: `schema.sql` must be loaded into the database for the worker to store votes (it is not mounted automatically).

---

School project at Epitech (France). More projects: [hedibannour.com](https://hedibannour.com/#projects)
