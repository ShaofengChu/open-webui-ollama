# open-webui-ollama

open-webui-ollama is a web-based user interface for interacting with Ollama models. It provides a simple and intuitive way to run, manage, and interact with large language models locally or remotely.

## Table of Contents

- [Features](#features)
- [Screenshots](#screenshots)
- [Getting Started](#getting-started)
- [Docker Compose Setup](#docker-compose-setup)
- [Configuration](#configuration)
- [Usage](#usage)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## Features

- Easy-to-use web interface for Ollama models
- Model management (start, stop, switch models)
- Chat interface with conversation history
- REST API for programmatic access
- Persistent data storage using Docker volumes
- GPU acceleration support (optional)

## Screenshots

<!-- Add screenshots of your UI here -->
<img width="1910" height="1113" alt="image" src="https://github.com/user-attachments/assets/3dba2cd3-689b-419e-90c8-7d9eb8111efb" />


## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Docker Compose Setup

This project includes a `docker-compose.yml` file for easy deployment. It defines two services:

- **ollama**: Runs the Ollama backend for model inference.
- **open-webui**: Runs the web-based user interface.

### Steps

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/open-webui-ollama.git
    cd open-webui-ollama
    ```

2. Start the services:

    ```bash
    docker-compose up -d
    ```

3. Access the web UI at [http://localhost:3000](http://localhost:3000).

### Data Persistence

- Ollama data is stored in `./ollama_data` on your host.
- Web UI data is stored in `./open-webui_data` on your host.

### GPU Acceleration

If you have an NVIDIA GPU and want to enable GPU acceleration for Ollama, uncomment the relevant lines in `docker-compose.yml` under the `ollama` service.

## Configuration

- The `OLLAMA_BASE_URL` environment variable is set to `http://ollama:11434` to connect the web UI to the Ollama backend.
- Ports:
  - Ollama API: `11434`
  - Web UI: `3000` (mapped to container port `8080`)

## Usage

- Start and stop services with Docker Compose:

    ```bash
    docker-compose up -d   # Start
    docker-compose down    # Stop
    ```

- To view logs:

    ```bash
    docker-compose logs -f
    ```

## Development

For local development without Docker, see the [Getting Started](#getting-started) section above.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
