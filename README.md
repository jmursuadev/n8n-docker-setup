# n8n Docker Setup

Docker Compose setup for n8n with PostgreSQL and Adminer.

## Services

- **n8n** - Workflow automation platform (port 5678)
- **PostgreSQL 16** - Database backend
- **Adminer** - Database management UI (port 8080)

## Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd n8n-docker-setup
   ```

2. **Create environment file**
   ```bash
   cp .env.example .env
   ```

3. **Configure environment variables** (optional)

   Edit `.env` to customize:
   ```
   POSTGRES_USER=n8n
   POSTGRES_PASSWORD=n8n_password
   POSTGRES_DB=n8n
   TIMEZONE=Asia/Manila
   ```

4. **Start the services**
   ```bash
   docker compose up -d
   ```

5. **Access the applications**
   - **n8n**: http://localhost:5678
   - **Adminer**: http://localhost:8080

## Adminer Connection

Use these settings to connect to PostgreSQL via Adminer:
- **System**: PostgreSQL
- **Server**: `postgres`
- **Username**: Value of `POSTGRES_USER`
- **Password**: Value of `POSTGRES_PASSWORD`
- **Database**: Value of `POSTGRES_DB`

## Commands

```bash
# Start services
docker compose up -d

# Stop services
docker compose down

# View logs
docker compose logs -f

# View n8n logs only
docker compose logs -f n8n

# Restart services
docker compose restart

# Update to latest images
docker compose pull
docker compose up -d
```

## Data Persistence

Data is persisted using Docker volumes:
- `postgres_data` - PostgreSQL database files
- `n8n_data` - n8n configuration and data
