# Environment Playground

A collection of Vagrant and Docker Compose configurations for various development and server environments.

## 📁 Repository Structure

```
├── vagrant/
│   ├── java/           # Java development environment
│   ├── weblogic/       # Oracle WebLogic Server
│   ├── tomcat/         # Apache Tomcat
│   ├── wildfly/        # WildFly Application Server
│   ├── n8n/            # n8n Workflow Automation
│   ├── ollama/         # Ollama AI Server
│   └── apache-httpd/   # Apache HTTP Server
└── docker/
    ├── docker-compose.java.yml
    ├── docker-compose.weblogic.yml
    ├── docker-compose.tomcat.yml
    ├── docker-compose.wildfly.yml
    ├── docker-compose.n8n.yml
    ├── docker-compose.ollama.yml
    └── docker-compose.apache-httpd.yml
```

## 🖥️ Vagrant Environments

### Prerequisites

- [VirtualBox](https://www.virtualbox.org/) (or another supported provider)
- [Vagrant](https://www.vagrantup.com/)

### Usage

Navigate to the desired environment directory and run:

```bash
cd vagrant/<environment>
vagrant up
```

### Available Environments

| Environment | IP Address | Ports | Description |
|-------------|------------|-------|-------------|
| Java | 192.168.56.10 | 8080, 8443 | OpenJDK 17, Maven, Gradle |
| WebLogic | 192.168.56.11 | 7001, 7002, 8001 | Oracle WebLogic 14.1.1 |
| Tomcat | 192.168.56.12 | 8082, 8444, 8009 | Apache Tomcat 10.1 |
| WildFly | 192.168.56.13 | 8083, 8445, 9990 | WildFly 30 |
| n8n | 192.168.56.14 | 5678 | n8n Workflow Automation |
| Ollama | 192.168.56.15 | 11434 | Ollama AI Server |
| Apache HTTPD | 192.168.56.16 | 8084, 8446 | Apache HTTP Server |

### Common Vagrant Commands

```bash
vagrant up          # Start the VM
vagrant ssh         # SSH into the VM
vagrant halt        # Stop the VM
vagrant destroy     # Remove the VM
vagrant provision   # Re-run provisioning scripts
```

## 🐳 Docker Compose Environments

### Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

### Usage

Navigate to the docker directory and run:

```bash
cd docker
docker compose -f docker-compose.<environment>.yml up -d
```

### Available Compose Files

| File | Services | Ports |
|------|----------|-------|
| docker-compose.java.yml | Java development container | 8080, 8443 |
| docker-compose.weblogic.yml | WebLogic Server | 7001, 7002, 8001 |
| docker-compose.tomcat.yml | Tomcat, Tomcat Manager | 8080, 8081 |
| docker-compose.wildfly.yml | WildFly, WildFly Admin | 8080, 8081, 9990, 9991 |
| docker-compose.n8n.yml | n8n, n8n with PostgreSQL | 5678, 5679 |
| docker-compose.ollama.yml | Ollama, Open WebUI | 11434, 11435, 3000 |
| docker-compose.apache-httpd.yml | Apache, Apache SSL, Apache Proxy | 80, 443, 8080, 8443, 8081 |

### Common Docker Commands

```bash
docker compose -f <file> up -d      # Start services
docker compose -f <file> down       # Stop services
docker compose -f <file> logs -f    # View logs
docker compose -f <file> ps         # List running services
```

## 📝 Environment Details

### Java Development

A complete Java development environment with:
- OpenJDK 17
- Apache Maven
- Gradle
- Git

### WebLogic

Oracle WebLogic Server setup. Note: WebLogic requires:
- Manual download of installer (Vagrant) or
- Oracle Container Registry authentication (Docker)

### Tomcat

Apache Tomcat 10.1 with:
- HTTP/HTTPS support
- Systemd service (Vagrant)
- Manager app option (Docker)

### WildFly

WildFly 30 Application Server with:
- Admin console enabled
- Pre-configured admin user (admin/admin123)
- Deployment directory mounted

### n8n

n8n workflow automation platform with:
- Web interface
- PostgreSQL option for production
- Persistent workflow storage

### Ollama

Ollama AI server for running LLMs locally with:
- API endpoint
- Open WebUI chat interface option
- Model persistence

### Apache HTTPD

Apache HTTP Server with:
- SSL support
- Reverse proxy configuration
- Common modules enabled

## 🔧 Customization

Each environment includes shared folders for easy customization:

- **Vagrant**: Folders are mapped in the Vagrantfile
- **Docker**: Volumes are defined in the compose files

## 📄 License

This project is open source and available under the MIT License.