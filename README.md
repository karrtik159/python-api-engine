<h1 align="center">
  Python FastAPI Boilerplate with PostgreSQL
</h1>

## Overview

`Python FastAPI Boilerplate with PostgreSQL` is a boilerplate that can serve as a base for FastAPI with PostgreSQL.

🚀 FastAPI is a modern, fast (high-performance) web framework for building APIs with Python 3.6+ based on standard Python-type hints.
I made and used this boilerplate for projects that I’m working on. 🧑‍💻
it was powerful for building data-driven applications using schema for data validation, serialization, and documentation. 📝

## Technology Stacks

- 🐍 [Python 3.11](https://docs.python.org/3.11/) - A programming language that lets you work quickly and integrate systems more effectively.
- 🚀 [FastAPI](https://fastapi.tiangolo.com) - A modern, fast (high-performance), web framework for building APIs with Python 3.8+ based on standard Python type hints.
- 🐳 [Docker](https://docs.docker.com) - A platform designed to help developers build, share, and run container applications.
- 🐘 [PostgreSQL](https://www.postgresql.org/docs/) - An open-source object-relational database system.
- 💾 [SQLAlchemy](https://docs.sqlalchemy.org/en/20/) - the Python SQL toolkit and Object Relational Mapper.
- 📦 [Poetry](https://python-poetry.org/docs) - A tool for dependency management and packaging in Python.
- 🧪 [Pytest](https://docs.pytest.org/en/8.0.x/) -  A framework that makes writing small, readable tests easy.
- 🦀 [Ruff](https://docs.astral.sh/ruff/) - A fast Python linter and code formatter written in Rust.

## Development Features

- 🚫 JWT authentication, to ensure secure access to the API.
- 🎢 A Layered architecture (Controller, Service, Repository, Model).
- 📦 Dependency injection for better code organization.
- 📝 Swagger and Redoc for API documentation and testing.
- ♻️ Schema validation, to ensure that input and output data conform to the defined schema.

## Requirements

- Python 3.10+
- Poetry
- PostgreSQL
- Docker

## Getting Started

Every command below except `build` and `run` is executed in a docker container.

### Set Environment Variables

```bash
# Copy service env file
$ cp .env.example .env
# Copy db env file
$ cp .db.env.example .db.env
```

### Build and run the app with Docker Compose

```bash
# Build docker image
$ docker compose build

# Run the app in the background
$ docker compose up -d

# Watch logs
$ docker compose logs -f

# Execute a command in a running container
$ docker compose exec app <command>
```

### Migrate database

**before test or use the app, you need to migrate the database.**

```bash
# init User table
$ docker compose exec app poetry run alembic upgrade head
```

### Test

```bash
# Run unit tests using pytest
$ docker compose exec app poetry run pytest
```

### Lint and format

The Ruff is an extremely fast Python linter and code formatter written in Rust.
It can replace flake8, isort, and black at once.

```bash
# Run Ruff

## Code linting
$ docker compose exec app poetry run ruff check .

## Code formatting
$ docker compose exec app poetry run ruff format .
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.
