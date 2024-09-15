
# CIS Hardened Docker Images

![Docker](https://img.shields.io/badge/Docker-CIS%20Hardened-blue)
![MongoDB](https://img.shields.io/badge/MongoDB-Hardened-brightgreen)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Hardened-brightgreen)
![NGINX](https://img.shields.io/badge/NGINX-Hardened-brightgreen)

## 📚 About This Repository

This repository contains **CIS-hardened** Docker images for the following services:
- **MongoDB**
- **PostgreSQL**
- **NGINX**

Each service is hardened according to the [CIS Security Benchmarks](https://www.cisecurity.org/cis-benchmarks/), focusing on critical security controls to improve the system's resilience and protect sensitive data.

The security configurations include:
- Enforcing strict **access control policies**.
- Implementing **TLS encryption** for data in transit.
- Enabling detailed **audit logging**.
- Ensuring strong **authentication** and **password policies**.
- Limiting buffer sizes and setting **secure headers**.

---

## 🛠 Services

### 1. MongoDB

MongoDB is configured following the [CIS MongoDB Benchmark](https://downloads.cisecurity.org/#/). Key hardening measures include:
- Enforcing **TLS encryption** for all client connections.
- Disabling unauthenticated bindings.
- Enabling **Authorization** and **Role-Based Access Control (RBAC)**.
- Configuring **audit logging** to track user activities and system changes.

#### Example Usage:
```bash
docker build -t hardened-mongodb ./mongodb
docker run -d -p 27017:27017 hardened-mongodb
```

### 2. PostgreSQL

PostgreSQL is hardened using the [CIS PostgreSQL Benchmark](https://downloads.cisecurity.org/#/). Critical configurations include:
- Restricting **host-based authentication (HBA)**.
- Enforcing **TLS** to secure all connections.
- Implementing strong **password policies** using SCRAM-SHA-256 encryption.
- Logging all connection and disconnection events.

#### Example Usage:
```bash
docker build -t hardened-postgresql ./postgresql
docker run -d -p 5432:5432 hardened-postgresql
```

### 3. NGINX

NGINX is secured by following the [CIS NGINX Benchmark](https://downloads.cisecurity.org/#/). The configuration includes:
- Enforcing **HTTPS** with strong TLS configurations (1.2+).
- Implementing **HSTS** to prevent protocol downgrades.
- Using security headers to prevent XSS, clickjacking, and MIME sniffing.
- Limiting buffer sizes to prevent buffer overflow attacks.

#### Example Usage:
```bash
docker build -t hardened-nginx ./nginx
docker run -d -p 80:80 -p 443:443 hardened-nginx
```

---

## 🚀 Quick Start Guide

1. **Clone this repository**:
   ```bash
   git clone https://github.com/your-username/cis-hardened-repository.git
   cd cis-hardened-repository
   ```

2. **Build and Run the Containers**:
   Use the provided Dockerfiles to build the hardened images.
   ```bash
   docker-compose up --build
   ```

3. **Access Services**:
   - MongoDB: `localhost:27017`
   - PostgreSQL: `localhost:5432`
   - NGINX: `localhost:443`

---

## 🛡️ Security Features

### 🔐 Encryption

- **MongoDB**: TLS encryption for all client-server communication.
- **PostgreSQL**: SSL/TLS enforced for data in transit.
- **NGINX**: TLS 1.2+ for encrypted communication.

### 🧑‍💻 Authentication

- **MongoDB**: Role-based access control (RBAC) enabled with strong password policies.
- **PostgreSQL**: SCRAM-SHA-256 for secure password encryption.
- **NGINX**: HTTPS with secure headers for robust security.

### 📝 Auditing and Logging

- **MongoDB**: Detailed audit logs for user actions, including authentication and database operations.
- **PostgreSQL**: Logging of all connections, disconnections, and query duration for tracking potential misuse.
- **NGINX**: Access logs and error logs enabled for auditing web traffic and errors.

---

## 📚 Documentation

- [CIS MongoDB Benchmark](https://downloads.cisecurity.org/#/): Official MongoDB CIS Benchmark documentation.
- [CIS PostgreSQL Benchmark](https://downloads.cisecurity.org/#/): Official PostgreSQL CIS Benchmark documentation.
- [CIS NGINX Benchmark](https://downloads.cisecurity.org/#/): Official NGINX CIS Benchmark documentation.
- [Docker CIS Benchmark](https://www.cisecurity.org/benchmark/docker/): Recommendations for securely running Docker containers.

---

## 📄 License

This project is licensed under the MIT License. Feel free to use, modify, and distribute as needed.

---

## 👤 Author

Created and maintained by [Milad Ahmadi](https://github.com/milad-ahmd).

---

## 🎯 Contribute

Feel free to submit issues or pull requests if you have any improvements or additional hardening recommendations!
