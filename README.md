# MySQL Database Containerization 

A MySQL database containerization with initialization scripts and data persistence. 

## Project Structure
mysql-docker/
├── Dockerfile         # MySQL image configuration
├── docker-compose.yml # Container orchestration
├── init.sql          # Database initialization
└── README.md         # Project documentation


## Prerequisites
- Docker installed on your system
- Docker Compose installed on your system



#. Start the container
- docker-compose up -d

3. Verify container is running
- docker ps

4. Connect to MySQL
mysql -h localhost -P 3306 -u user -p
# Enter password: password

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
- docker-compose up -d


Stop containers:
- docker-compose down

View logs:
- docker-compose logs


Access MySQL shell:
- docker exec -it mysql-docker-db-1 mysql -u user -p

Remove everything including volumes:
- docker-compose down -v


## Data Persistence
Database data is persisted using Docker volumes. The data remains intact even if the container is removed.

## Development

1. Modify init.sql to change initial database structure
2. Update docker-compose.yml for configuration changes
3. Rebuild container after changes:
- docker-compose down
- docker-compose up -d --build

