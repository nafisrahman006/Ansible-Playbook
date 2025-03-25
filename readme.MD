# Ansible Automation Project

This project is an Ansible-based automation setup for managing servers and deploying applications. It includes playbooks and roles for installing Docker, Jenkins, and performing basic server management tasks.

## Features

- **Automated Server Management**: Manage servers using Ansible with minimal manual intervention.
- **Docker Installation**: Install and configure Docker on remote servers.
- **Jenkins Deployment**: Install and configure Jenkins with custom settings.
- **Customizable Inventory**: Easily manage server configurations using an inventory file.

---

## Project Structure

### Inventory

The `inventory.ini` file contains the list of servers to be managed by Ansible. It specifies the IP addresses, SSH users, and private key files for authentication.

### Roles

#### Jenkins Role

The `roles/jenkins/tasks/main.yml` file contains tasks to install and configure Jenkins. Key tasks include:

1. Downloading the Jenkins GPG key.
2. Adding the Jenkins APT repository.
3. Installing Jenkins with a specific version.
4. Ensuring Jenkins is running as a service.
5. Waiting for Jenkins to become reachable on the specified port.

### Docker Role
The `Playbook/docker-install.yaml` playbook performs the following tasks:

1. Updates the apt cache.
2. Installs required packages (e.g., `ca-certificates`, `curl`).
3. Ensures the Keyrings directory exists.
4. Downloads and adds the Docker GPG key.
5. Adds the Docker APT repository.
6. Installs Docker packages (e.g., `docker-ce`, `docker-compose-plugin`).
7. Ensures the Docker service is running.
8. Adds the `ubuntu` user to the Docker group.

