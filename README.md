# DevOps Lab Exercises

Practical DevOps exercises covering containerization, orchestration, security, monitoring, and continuous integration. Each exercise is self-contained and includes the configuration, source files, and instructions needed to reproduce the work locally.

## Learning Path

| No. | Topic | What it covers |
|:---:|---|---|
| 01 | [Kubernetes Getting Started](exercise1) | Creating and exposing a first Nginx Pod with Minikube |
| 02 | [Minikube, kubectl and Flask](exercise2) | Deploying a Flask application with kubectl and Kubernetes YAML |
| 03 | [Scaling a Flask Application](exercise3) | Running and scaling application replicas with ReplicaSets |
| 04 | [Docker Networking](exercise4) | Connecting Flask, MySQL, and Redis containers on a bridge network |
| 05 | [Docker Security with AppArmor](exercise5) | Applying AppArmor controls to restrict container capabilities |
| 06 | [Grafana Real-time Monitoring](exercise6) | Monitoring delivery metrics with Prometheus, Grafana, and Jenkins |
| 07 | [Jenkins CI Automation](exercise7) | Building a basic continuous integration workflow with Jenkins |
| 08 | [Jenkins Hello World Job](exercise8) | Creating and running a Jenkins Freestyle project |
| 09 | [Jenkins Multi-stage Pipeline](exercise9) | Building, testing, deploying, and running a Python application through Jenkins |
| 10 | [Multi-Node Kubernetes Cluster with Multiple Applications and Replicasets](exercise10) | Building, testing, deploying, and running a Python application through Jenkins |

## Technology Focus

**Containers and orchestration**  
Docker, Kubernetes, Minikube, and kubectl

**Automation and delivery**  
Jenkins and declarative pipeline configuration

**Monitoring and observability**  
Prometheus and Grafana

**Application development and testing**  
Python, Flask, and unittest

**Container security**  
AppArmor and restricted container execution

## Repository Structure

Every directory under Exercises represents one focused lab. The individual README in each directory explains the objective, setup, commands, and expected results for that exercise.

The collection is organized into the following focused areas:

- Kubernetes fundamentals and application deployment
- Flask deployment and replica scaling
- Docker networking and container security
- Prometheus and Grafana monitoring
- Jenkins jobs, CI automation, and multi-stage pipelines

## Getting Started

1. Clone the repository.
2. Select an exercise from the learning path.
3. Review its README for prerequisites and setup instructions.
4. Run the exercise using the tools listed in that guide.

The exact prerequisites vary by exercise. Docker, Minikube, kubectl, Jenkins, and Python may be required depending on the lab.

## Author

Maintained by **Sourish Sharma** as a practical DevOps learning portfolio.
