# Linux Server Configuration
---
Set up a Linux server with good security settings, install/configure a web server and database server to host web applications.


# System Configuration
---
IP Address (Static and Public): 35.182.80.124

SSH Port: 2200

Hosted Web Application Complete URL: http://<http://35.182.80.124.xip.io/>

A Summary of software installed and configurations made:

**PostgreSQL:**
- Disabled remote connection
 - Setup unix domain socket user "ubuntu" within the DB and granted privileges required to drive the web application
 - Setup a host user "catalog within the DB and granted limited privileges
 - run the following: ```psql -h localhost -U catalog```

**Gunicorn:**

- A Python WSGI HTTP Server installed.
- Configured to launch and serve the web application via port: 8000 
- Configured to launch the RESTFUL api services via port: 8001

**Supervisor:**

A package installed and configured, which is used to run, monitor and manage Gunicorn and applications it hosts(Item Catalog App, Item Catalog API)

**Nginx:**

- A Web Server installed
- Configured as a front-end reverse proxy

**xip.io:**

- A DNS Service, leveraged in order to set up OAuth for the web application


**Ubuntu 16.04:**

User Management:

- Created and configured user "grader" and granted sudo access
- Remote login for user "root" is disabled

Security:

Configured OS's  Uncomplicated firewall(UFW) to allow connections for the following:

- SSH port: 2200
- HTTP port: 80
- NTP port: 123

Authentication:

Configured  system, such that Key-based SSH authentication is enforced









