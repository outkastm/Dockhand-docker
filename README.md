# Dockhand for TerraMaster TOS 7

Dockhand is a lightweight web application for managing Docker containers and Compose stacks, optimized for deployment on TerraMaster TOS 7 NAS systems.

## 1. Overview & Source Repository

* **Application Name:** Dockhand

* **Container Image Source:** Pulled directly from official Docker Hub repository (`dockhand/dockhand:v*`)

* **Application Storage Path:** `/Volume1/DockerAppData/Dockhand-docker`

* **Official Upstream Project:** <https://dockhand.pro>

* **Upstream Source Repository:** <https://github.com/Finsys/dockhand>

* **Support:** <https://tmnascommunity.eu/forums/topic/dockhand-docker>

## 2. Port & Network Configuration

* **Host Published Port:** `3250`

* **Internal Container Port:** `3000`

* **Protocol:** HTTP

Upon installation via the TOS App Center, the web interface is accessible at `http://<NAS_IP_ADDRESS>:3250`.

## 3. Persistent Data Directories

To ensure configuration files, application databases, and Docker Compose stacks persist across package updates and system reboots, host directories are mapped directly to primary NAS storage (`/Volume1`):

| Host Path | Container Target Path | Purpose | 
| ----- | ----- | ----- | 
| `/Volume1/DockerAppData/Dockhand-docker/data` | `/app/data` | Application configuration, database, and local settings | 

## 4. Docker Socket Binding

For TOS 7 system compatibility, the host Docker daemon socket is mapped using the system-preserved path:

* **Host Path:** `/var/run/docker.sock`

* **Container Target Path:** `/var/run/docker.sock`

## 5. Privacy Policy & Data Handling (Compliance Item 4)

This application strictly operates locally on your TerraMaster NAS and complies with the upstream [Dockhand Privacy Policy](https://dockhand.pro/privacy.html).

* **Public Privacy Policy URL:** <https://dockhand.pro/privacy.html>

* **Bundled Application Privacy Statement:** Located on the container file system at `/app/PRIVACY.txt`.

### Privacy & Telemetry Statements:

1. **No External Tracking / Telemetry:** Dockhand stores all data locally on your infrastructure and contains no telemetry, tracking, or analytics. It does not transmit personal data or usage metrics to external servers.

2. **Local Storage:** All container configurations, login credentials, and operational logs remain exclusively on your local NAS device within `/Volume1/DockerAppData/Dockhand-docker/app_data`.

3. **Local Socket Communication:** All container management interactions take place locally between the application and the host system's Docker socket (`/var/api/docker.sock`).

## 6. Installation & Deployment Guide

### Installation via TOS App Center


1. Open **TOS App Center** on your TerraMaster NAS.

2. Search for **Dockhand** app and install it

4. Launch the application or navigate directly to `http://<NAS_IP>:3250`.


## 7. License

This application and upstream codebase are governed under the official [Dockhand License Terms](https://dockhand.pro/license.html).