# Local Worker Pool

Run a worker pool (and VCS Agent, if applicable) locally with Docker Compose.

## Requirements

The Docker engine and Docker Compose must be installed on the local machine for this to work.

The easiest way to achieve install those tools is probably to install [Docker Desktop](https://www.docker.com/products/docker-desktop).

## Installation

- Copy the `.worker.env.example` file into `.worker.env`.
- Edit the `.worker.env` file to set the Spacelift worker pool token and your certificate private key as described in [the documentation](https://docs.spacelift.io/concepts/worker-pools#setting-up).

### Allowing the worker pool to resolve private dns

- Copy the `.docker-daemon.json.example` file into `.docker-daemon.json`.
- Edit the `.docker-daemon.json` file to configure the private DNS IPs.
- Uncomment the `services.dind_sidecar.volumes` section in docker-compose.yml to mount the config file to the correct path.

In case of running a selfhosted VCS Agent Pool, add this additional configuration:

- Copy the `.vcs.env.example` file into `.vcs.env`.
- Edit the `.vcs.env` file to set the Spacelift VCS Agent Pool token as described in [the documentation](https://docs.spacelift.io/concepts/vcs-agent-pools.html#running-the-vcs-agent).
- Uncomment the `services.vcs` section in docker-compose-yml to create the VCS Agent Pool container

## Usage

- Start the worker pool in the background: `docker compose up -d`.
- (optional) Watch the logs: `docker compose logs -f`.
- Delete the worker pool Docker containers: `docker compose down -v`.
