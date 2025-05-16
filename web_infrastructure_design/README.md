# Web Infrastructure Design

This repository contains diagrams and explanations for designing web infrastructures, from a simple single-server setup to a secure, distributed, and scalable system.

## 🧠 Learning Objectives

By completing this project, you will be able to:

* Draw and explain different web infrastructure setups.
* Identify and describe the role of each component in a web stack.
* Explain key concepts such as redundancy, SPOF (Single Point of Failure), and QPS (Queries Per Second).
* Understand and design secure and monitored systems.
* Understand the importance of high availability and scalability.

## 📚 Resources

* [Network basics](https://intranet.hbtn.io/concepts/49)
* [Servers and web servers](https://intranet.hbtn.io/concepts/67)
* [DNS and DNS record types](https://intranet.hbtn.io/concepts/12)
* [Load balancers](https://intranet.hbtn.io/concepts/68)
* [Monitoring](https://intranet.hbtn.io/concepts/139)
* [Databases and replication](https://intranet.hbtn.io/concepts/110)
* [HTTPS and firewalls](https://intranet.hbtn.io/concepts/111)

## 📁 Project Structure

Each task contains a whiteboard diagram and an explanation of the infrastructure.

### `0-simple_web_stack`

A basic one-server infrastructure using a **LAMP stack**:

* **Domain**: `foobar.com` with a `www` record pointing to IP `8.8.8.8`
* **Single Server** running:

  * Nginx (web server)
  * Application server
  * MySQL (database)
  * Application code

**Key Concepts**:

* Server, DNS, Web server, Application server, Database
* Communication via HTTP
* Weaknesses: SPOF, downtime for maintenance, no scalability

---

### `1-distributed_web_infrastructure`

An improved architecture using 3 servers and a load balancer:

* **Load Balancer**: HAProxy
* **2 Web Servers**: Each running Nginx, app server, code base, and MySQL
* **DNS** still points to the load balancer

**Key Concepts**:

* Load balancing algorithms (Round Robin, Least Connections, etc.)
* Active-Active vs Active-Passive configurations
* Master-Slave database replication
* Pros: redundancy, better availability
* Cons: no HTTPS, no firewalls, no monitoring

---

### `2-secured_and_monitored_web_infrastructure`

Adding security and monitoring to the infrastructure:

* **3 Firewalls** (one for each server)
* **SSL certificate** to serve traffic over HTTPS
* **Monitoring Clients** (e.g., for SumoLogic or other services)

**Key Concepts**:

* Role of firewalls
* Importance of HTTPS (data encryption and trust)
* Monitoring system metrics and logs
* QPS monitoring
* Limitations: SSL termination at the load balancer, single write-capable DB node, homogenous server setup

---

### `3-scale_up`

Infrastructure scaling and separation of concerns:

* Additional server
* Second HAProxy in cluster mode
* Split infrastructure:

  * Dedicated Web Server
  * Dedicated Application Server
  * Dedicated Database Server

**Key Concepts**:

* Scalability
* Load balancing clusters
* Separation of concerns for better performance and maintainability

---

## ✅ Requirements

* All diagrams are whiteboarded and uploaded as images.
* Each task is explained with clarity, focusing only on what's required.
* All content is written in English to support technical communication skills.
* The project is manually reviewed and requires live whiteboarding sessions.

## 📝 Acronyms to Remember

* **LAMP**: Linux, Apache/Nginx, MySQL, PHP
* **SPOF**: Single Point of Failure
* **QPS**: Queries Per Second

---

## 📦 Repository Info

* **GitHub Repo**: `holbertonschool-system_engineering-devops`
* **Directory**: `web_infrastructure_design`
