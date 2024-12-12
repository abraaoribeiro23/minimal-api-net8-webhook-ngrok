# Minimal API with .NET 8.0 and ngrok Integration

This is a sample project demonstrating how to expose a local webhook using a .NET 8.0 Minimal API and ngrok configured within a Docker container.

## Features

- Minimal API built with .NET 8.0
- Integration with ngrok to expose the local environment
- Configuration via Docker and Docker Compose

## Requirements

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- [Docker](https://www.docker.com/)
- An account on [ngrok](https://ngrok.com/) and an authentication token (NGROK_AUTHTOKEN)

## Setup

1. Clone this repository:

   ```bash
   git clone https://github.com/abraaoribeiro23/minimal-api-net8-webhook-ngrok.git
   cd minimal-api-net8-webhook-ngrok
   ```

2. Generate your ngrok authentication token by visiting [here](https://dashboard.ngrok.com/get-started/your-authtoken).

3. Generate your ngrok domain by visiting [here](https://dashboard.ngrok.com/domains).

4. Create a `.env` file in the project root and add your ngrok domain and authentication token:

   ```env
   NGROK_AUTHTOKEN=your_authtoken_here
   NGROK_DOMAIN=your_domain_here
   ```

5. Run the following command to start the containers:

   ```bash
   docker-compose up
   ```

6. Or run using the development configuration:
	
	```bash
	docker-compose -f docker-compose-development.yaml up
	```

## How It Works

- The `docker-compose.yml` sets up two containers:
  - One for the Minimal API.
  - Another for ngrok, which exposes the API to the internet.
- The ngrok authentication token is used to configure ngrok via environment variables.

## Accessing the API

- After starting the containers, you can access the API through the domain `NGROK_DOMAIN`.

## Stopping the Containers

To stop the containers, use the following command:

```bash
docker-compose down
```

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more information.

