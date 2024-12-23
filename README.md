# MySQL Database Containerization Project

A simple Docker project demonstrating MySQL database containerization with initialization scripts and data persistence. This project is ideal for DevOps beginners learning database containerization concepts.

## Project Structure
```
mysql-docker/
├── Dockerfile         # MySQL image configuration
├── docker-compose.yml # Container orchestration
├── init.sql          # Database initialization
└── README.md         # Project documentation
```

## Prerequisites
- Docker installed on your system
- Docker Compose installed on your system
- Basic understanding of Docker commands
- Git for version control

## Quick Start

1. Clone the repository
```bash
git clone <your-repository-url>
cd mysql-docker
```

2. Start the container
```bash
docker-compose up -d
```

3. Verify container is running
```bash
docker ps
```

4. Connect to MySQL
```bash
mysql -h localhost -P 3306 -u user -p
# Enter password: password
```

## Configuration

### Database Credentials
- Database: mydb
- Username: user
- Password: password
- Root Password: rootpassword

### Port
- MySQL Port: 3306

## File Descriptions

### Dockerfile
- Base image: MySQL 8.0
- Sets environment variables
- Copies initialization script
- Exposes MySQL port

### docker-compose.yml
- Defines MySQL service
- Sets up port mapping
- Configures data persistence
- Manages container restart policy

### init.sql
- Creates users table
- Inserts sample data
- Runs automatically on container creation

## Common Commands

Start containers:
```bash
docker-compose up -d
```

Stop containers:
```bash
docker-compose down
```

View logs:
```bash
docker-compose logs
```

Access MySQL shell:
```bash
docker exec -it mysql-docker-db-1 mysql -u user -p
```

Remove everything including volumes:
```bash
docker-compose down -v
```

## Data Persistence
Database data is persisted using Docker volumes. The data remains intact even if the container is removed.

## Development

1. Modify init.sql to change initial database structure
2. Update docker-compose.yml for configuration changes
3. Rebuild container after changes:
```bash
docker-compose down
docker-compose up -d --build
```

## Security Notes
- Change default passwords in production
- Use environment files for sensitive data
- Restrict port exposure as needed
- Never commit sensitive data to Git

## Learning Objectives
- Database containerization
- Docker volume management
- Environment configuration
- Container networking
- Database initialization
- Docker Compose usage

## Contributing
Feel free to fork this repository and submit pull requests for improvements.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Author
[Your Name]

## Acknowledgments
- MySQL Docker documentation
- Docker documentation
- DevOps community

## Support
For support, please open an issue in the GitHub repository.
