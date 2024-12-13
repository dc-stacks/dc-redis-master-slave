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

cd {Related folder}

# make an env file from example
cp .env.example .env

# for with-config : edit config file inside config dir 
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