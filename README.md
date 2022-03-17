# Local Worker Pool

Run a worker pool locally with Docker Compose.

## Requirements

The Docker engine and Docker Compose must be installed on the local machine for this to work.

The easiest way to achieve install those tools is probably to install [Docker Desktop](https://www.docker.com/products/docker-desktop).

## Installation

- Copy the `.env.example` file into `.env`.
- Edit the `.env` file to set the Spacelift worker pool token and your certificate private key as described in [the documentation](https://docs.spacelift.io/concepts/worker-pools#setting-up).

## Usage

- Start the worker pool: Run `docker-compose up` .
- Stop the worker pool: Press `ctrl-c` .
- Delete the worker pool Docker containers: Run `docker-compose down -v` .
