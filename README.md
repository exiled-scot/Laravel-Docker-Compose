# Laravel Docker Boilerplate

This is a simple boilerplate for running a Laravel application using Docker. It sets up a PHP and MongoDB environment with the necessary dependencies.

## Usage

1. Clone this repository.

2. Build the Docker image and start the containers:
```
docker-compose up -d
```

3. Access the application in your browser at [http://localhost:8000](http://localhost:8000).

## Configuration

The default configuration assumes a Laravel application located in the `./blog` directory. You can change this by modifying the `volumes` section in the `docker-compose.yml` file.

## Services

The Docker environment consists of the following services:

### web

- Built from the `Dockerfile` in the current directory.
- Exposes port `8000`, which is forwarded to the host machine.
- Mounts the `./blog` directory as the document root.
- Depends on the `db` service.
- Uses the `laravel-network` network.
- Sets the `APP_ENV` environment variable to `local`.

### db

- Uses the `mongo` image.
- Exposes port `27017`, which is forwarded to the host machine.
- Creates a volume named `mongodata` to persist MongoDB data.
- Uses the `laravel-network` network.

## License

This project is licensed under the [MIT License](LICENSE).
