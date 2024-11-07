# Devops-Course-2024

## Spring PetClinic Project with GitHub Actions

In this project, I created a Spring PetClinic application and used GitHub Actions to automate testing and deployment. The workflow runs tests automatically on every push to the main branch, demonstrating the effectiveness of CI/CD pipelines.

[Spring PetClinic Project with GitHub Actions](https://github.com/BashirAhmed02/spring-petclinic-devops.git)

A Spring application featuring automated CI/CD with GitHub Actions.

---

## Skills and Tools
- **Version Control**: Git
- **Containerization**: Docker, Kubernetes, Knative
- **Cluster Management**: Minikube, Amazon EKS
- **Policy Management**: Kyverno
- **Service Mesh**: Istio

---
## Proof of Applied Tools

Below are the DevOps tools and processes applied in this project, with evidence to demonstrate each step.

#### Docker
- **Purpose**: Containerized the Spring PetClinic application to run in isolated environments.
- **Proof**:
  - Dockerfile:
  
    ![alt text](<../images/DockerFile.jpg>)

  - Docker Build Output:

    ![alt text](<../images/Dockerbuild.jpg>)

  - Docker Images List:

    ![alt text](<../images/Dockerimages.jpg>)

  - Application Running in Docker:

    ![alt text](<../images/Dockerrun.jpg>)


#### Kubernetes
- **Purpose**: Deployed the Spring PetClinic application on a Kubernetes cluster to manage and scale containers.
- **Proof**:
  - Deployment YAML Configuration::
  
    ![alt text](<../images/kubernates-yaml-file.jpg>)

  - kubectl Apply Output:

    ![alt text](<../images/kubectl-apply.jpg>)

  - Pods and Services

    ![alt text](<../images/Pods-Services.jpg>)

  - Application Running in Kubernetes:

    ![alt text](<../images/Kubernates-run.jpg>)


#### Knative
- **Purpose**: Configured Knative to enable serverless capabilities, allowing the Spring PetClinic application to scale automatically based on demand.
- **Proof**:
  - Knative Installation:
  
    ![alt text](<../images/knative-pods.jpg>)

  - Service YAML Configuration:

    ![alt text](<../images/knative-yaml-config.jpg>)

  - Service Creation and Service Status:

    ![alt text](<../images/knative.jpg>)

  - Application Running in Knative:

    ![alt text](<../images/knative-run.jpg>)


#### Kyverno
- **Purpose**: Implement policy management to enforce security and configuration standards across Kubernetes resources. In this project, Kyverno is used to ensure that every Pod created in the cluster includes the `env: dev` label.
- **Proof**:
  - Kyverno Installation:
  
    ![alt text](<../images/kyverno-instal.jpg>)

  - Policy Creation:

    ![alt text](<../images/policy.jpg>)

  - Blocked Pod Creation:

    ![alt text](<../images/blocked.jpg>)

  - Successful Pod Creation:

    ![alt text](<../images/success.jpg>)  


#### Istio
- **Purpose**: Configured Istio as a service mesh for the Spring PetClinic application, providing features such as traffic management, security, and observability.
- **Proof**:
  - Istio Installation:
  
    ![alt text](<../images/istio-install.jpg>)

  - Configure Istio Gateway and Virtual Service:

    ![alt text](<../images/gateway.jpg>)
    ![alt text](<../images/virtual.jpg>)

  - Accessing the Application:

    ![alt text](<../images/app.jpg>)

---


