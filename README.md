# Docker Compose Redis Master-Slave Setup

This repository contains Docker Compose configurations for setting up a Redis master-slave replication environment.

## Prerequisites
* Docker Engine
* Docker Compose
* Git (for cloning the repository)

## Quick Start
1. Clone the repository:
```bash
git clone https://github.com/dc-stacks/dc-redis-master-slave.git
cd dc-redis-master-slave
```

2. Create data directory:
```bash
mkdir -p data
```

# Master Setup
1. Copy the required files:
```bash
cp docker-compose.master.yml docker-compose.yml
cp master.env .env
```

2. Configure the environment variables in `.env`:
```env
COMPOSE_PROJECT_NAME="redis"
UID=1000
GID=1000
REDIS_MASTER_PASS="your_master_password"
REDIS_SLAVE_PASS="your_slave_password"
REDIS_PORT=6379
```

3. Start the Redis master:
```bash
docker compose up -d
```

# Slave Setup
1. Copy the required files:
```bash
cp docker-compose.slave.yml docker-compose.yml
cp slave.env .env
```

2. Configure the environment variables in `.env`:
```env
COMPOSE_PROJECT_NAME="redis"
UID=1000
GID=1000
REDIS_MASTER_HOST="master_ip_address"
REDIS_MASTER_PORT=6379
REDIS_MASTER_PASS="your_master_password"
REDIS_SLAVE_PASS="your_slave_password"
REDIS_PORT=6379
```

Note: Replace `master_ip_address` with your Redis master's actual IP address.

## Container Management
```bash
# View container status
docker compose ps

# View logs
docker compose logs

# Stop containers
docker compose down
```

## Security Notes
* Default passwords in env files should be changed in production
* Ensure proper network security between master and slave instances
* Consider implementing additional security measures for production environments

## License
MIT

## Contributing
Feel free to open issues and pull requests for any improvements.

---
Made with ❤️ by [Ariadata](https://github.com/ariadata)