# Task 0: Simple Web Stack Blueprint

**Goal:** One server hosting a website (`www.foobar.com`) with Nginx, app server, database.

## Components & Roles

| Component              | Representation in Diagram        | Purpose                                                                                |
| ---------------------- | -------------------------------- | -------------------------------------------------------------------------------------- |
| **User**               | Person icon / PC icon            | Sends HTTP request from browser.                                                       |
| **DNS**                | Cloud with "DNS" label           | Translates `www.foobar.com` to IP `8.8.8.8` (A record).                                |
| **Web Server (Nginx)** | Box inside main server           | Handles HTTP requests, serves static content, forwards dynamic requests to app server. |
| **Application Server** | Box inside main server           | Runs the backend logic (PHP, Node.js, etc.).                                           |
| **Application Files**  | Document icon inside app server  | The actual website/app code.                                                           |
| **Database (MySQL)**   | Cylinder icon inside main server | Stores persistent data.                                                                |
| **Server**             | Large outer rectangle            | Physical/virtual machine hosting all above.                                            |

## Connections & Data Flow

1. User → DNS: Request IP for `www.foobar.com`.
2. DNS → User: Returns `8.8.8.8`.
3. User → Server: Sends HTTP request.
4. Web server → App server: Passes request for dynamic processing.
5. App server → Database: Queries/updates data.
6. Server → User: Sends HTTP response.

## Issues

- **SPOF**: If server fails, entire site is down.
- **Maintenance downtime**: Restarting Nginx/app server causes downtime.
- **Scalability limit**: Cannot handle high load.

# Task 1: Distributed Web Infrastructure Blueprint

**Goal:** Multiple servers, load balancing, database handling.

## Components & Roles

| Component                    | Representation in Diagram | Purpose                                                      |
| ---------------------------- | ------------------------- | ------------------------------------------------------------ |
| **User**                     | Person icon               | Sends HTTP request.                                           |
| **DNS**                      | Cloud                     | Points `www.foobar.com` to LB’s IP.                           |
| **Load Balancer (HAProxy)**  | Box with LB label         | Distributes traffic to app servers (round-robin, leastconn). |
| **Web/App Servers (2x)**     | Two boxes                 | Run Nginx + app logic, host codebase.                        |
| **Database (MySQL Primary)** | Cylinder                  | Handles writes (and reads unless replicas added).             |
| **Application Files**        | Document icon             | Deployed identically on both servers.                         |

## Connections & Data Flow

1. User → DNS: Get LB IP.
2. User → LB: Sends HTTP request.
3. LB → Web/App Servers: Distributes traffic based on algorithm.
4. Web/App Server → DB: Executes queries.
5. DB → Web/App Server → LB → User: Sends back response.

## Issues

- **SPOF**: Load balancer and single DB.
- **Security**: No firewall, no HTTPS.
- **No monitoring**: Can’t detect failures or traffic spikes automatically.


# Task 2: Secured & Monitored Web Infrastructure Blueprint

**Goal:** Secure connections, add firewalls, monitoring.

## Components & Roles

| Component                        | Representation in Diagram              | Purpose                                       |
| -------------------------------- | -------------------------------------- | --------------------------------------------- |
| **User**                         | Person icon                            | Sends HTTPS request.                          |
| **DNS**                          | Cloud                                  | Points `www.foobar.com` to LB IP.             |
| **External Firewall**            | Shield icon in front of LB             | Filters unwanted traffic.                     |
| **Load Balancer with SSL Cert**  | LB box + lock icon                     | Terminates SSL, distributes requests.         |
| **Internal Firewall (Web tier)** | Shield icon between LB and web servers | Protects app servers.                         |
| **Internal Firewall (DB tier)**  | Shield icon between app servers and DB | Protects DB layer.                            |
| **Web/App Servers (2x)**         | Two boxes                              | Run Nginx + app logic, with monitoring agent. |
| **Database (Primary + Replica)** | Two cylinders                          | Primary for writes, replica for reads.        |
| **Monitoring System**            | Magnifying glass or graph icon         | Collects metrics/logs from agents.            |

## Connections & Data Flow

1. User → DNS → External Firewall → LB (HTTPS).
2. LB → Web tier firewall → Web servers.
3. Web servers → DB tier firewall → DB primary/replica.
4. Monitoring agents → Monitoring system (send logs/metrics).

## Issues

- **SSL termination at LB**: Internal traffic unencrypted.
- **Single DB write node**: Scaling limits.
- **Identical servers**: Might cause unnecessary resource duplication.

