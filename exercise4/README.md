# Exercise 4 — Docker Networking with Multiple Containers

## 1. Flask Docker Image Build and Initial API Test

The Flask application was successfully containerized, and the `flask-api` Docker image was built successfully.

![Flask Docker Image Build](flask-image-build.png)

---

## 2. Container-to-Container Communication

The Flask container successfully resolved and communicated with the MySQL and Redis containers through the `my-bridge-net` Docker bridge network.

![Container Networking](container-working.png)

---

## 3. MySQL Database Verification

The MySQL container was successfully initialized with the `devopsdb` database.

![MySQL Verification](mysql-verfication.png)

---

## 4. Final Multi-Container Configuration

The final configuration consisted of the Flask, MySQL, and Redis containers running on the same Docker bridge network.

![Final Docker Network](final-network-state.png)
