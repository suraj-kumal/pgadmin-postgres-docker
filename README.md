# PostgreSQL Server with pgAdmin

This project sets up a PostgreSQL database server with pgAdmin using Docker Compose.

## Prerequisites

- Docker Desktop
- Docker Compose
- Git (optional)

## Configuration

1. Clone this repository or create the following files in your project directory:

   - `docker-compose.yml`
   - `.env`

2. Create a `.env` file with the following environment variables:

```env
POSTGRES_USER=your_username
POSTGRES_PASSWORD=your_password
POSTGRES_DB=your_database_name
PGADMIN_DEFAULT_EMAIL=your_email@example.com
PGADMIN_DEFAULT_PASSWORD=your_pgadmin_password
```

## Usage

### Starting the Services

```bash
docker-compose up -d
```

### Checking Service Status

```bash
docker ps
```

### Stopping the Services

```bash
docker-compose down
```

### Stopping and Removing All Data

```bash
docker-compose down -v
```

## Service Access

- **PostgreSQL**

  - Host: `localhost`
  - Port: `5432`
  - Default Database: `${POSTGRES_DB}`
  - Username: `${POSTGRES_USER}`
  - Password: `${POSTGRES_PASSWORD}`

- **pgAdmin**
  - URL: `http://localhost:8080`
  - Email: `${PGADMIN_DEFAULT_EMAIL}`
  - Password: `${PGADMIN_DEFAULT_PASSWORD}`

## Connecting to PostgreSQL via pgAdmin

1. Open pgAdmin at `http://localhost:8080`
2. Login with your pgAdmin credentials
3. Right-click on "Servers" → "Create" → "Server"
4. In the "General" tab, give your connection a name
5. In the "Connection" tab, enter:
   - Host: `postgres`
   - Port: `5432`
   - Database: `${POSTGRES_DB}`
   - Username: `${POSTGRES_USER}`
   - Password: `${POSTGRES_PASSWORD}`

   
## Troubleshooting

- If services don't start, check Docker Desktop is running
- Verify all environment variables are set in `.env`
- Check ports 5432 and 8080 are not in use
- Review Docker logs: `docker-compose logs`

## License

This project is licensed under the MIT License - see the LICENSE file for details.
