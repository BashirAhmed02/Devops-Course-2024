# Devops-Course-2024


## Guide to My Learning and Contribution to DevOps

My journey in DevOps has been driven by a curiosity to understand how modern software systems are built, deployed, and managed efficiently. Through hands-on projects, research, and writing, I've gained valuable insights and developed skills in key areas of DevOps. Below is an outline of my contributions and learnings so far.

---

### 1. Practical DevOps Project: Spring PetClinic Application with CI/CD and Cloud-Native Tooling

To solidify my DevOps skills, I undertook a comprehensive project to build and automate the deployment pipeline for the **Spring PetClinic** application. This project allowed me to explore and apply essential DevOps tools and concepts, including:

- **Docker**: Containerized the application to provide an isolated and consistent environment, improving portability across different stages of development.
- **Kubernetes**: Deployed the application on a Kubernetes cluster to enable container orchestration, ensuring scalability and high availability.
- **Knative**: Configured Knative to enable serverless capabilities, allowing the application to scale based on demand.
- **Kyverno**: Integrated policy management to enforce security and configuration standards across Kubernetes resources.
- **Istio**: Implemented a service mesh to manage traffic, enhance security, and gain observability into application performance.

This project gave me hands-on experience with CI/CD practices, containerization, and cloud-native tooling, further reinforcing my understanding of how DevOps practices optimize the software lifecycle.

---

### 2. Knowledge Sharing: Blog Articles on DevOps Concepts

In addition to practical experience, I've shared my knowledge by authoring blog articles, which allowed me to reflect on what I've learned and contribute to the DevOps community.

- **[Understanding Continuous Integration and Continuous Delivery (CI/CD) Pipelines with Jenkins](https://medium.com/@bashir.a.khan02/understanding-continuous-integration-and-continuous-delivery-ci-cd-pipelines-with-jenkins-9aba6a755a73)**:
  This blog explains the fundamentals of CI/CD and demonstrates how Jenkins can be used to implement these practices. CI/CD is essential for DevOps as it enables faster, reliable software delivery by automating build, test, and deployment processes.

- **Continuous Integration (CI)**: CI focuses on integrating code changes frequently to a shared repository, where each integration is verified by an automated build to detect issues early.
- **Continuous Delivery (CD)**: CD extends CI by automating the deployment process, ensuring code can be deployed to production at any time with minimal effort.
- **Using Jenkins for CI/CD**: Jenkins is a popular open-source tool that helps automate parts of the CI/CD pipeline. The blog covers setting up Jenkins, configuring jobs, and creating pipelines to automate builds, tests, and deployments.
- **Benefits of CI/CD**: Faster releases, fewer integration issues, improved quality, and streamlined deployment processes.

This article provides a hands-on approach to setting up Jenkins for CI/CD, showing its effectiveness in managing code changes and reducing errors in deployments.

- **[Knative: Simplifying Serverless, Event-Driven Architectures on Kubernetes](https://medium.com/@bashir.a.khan02/knative-simplifying-serverless-event-driven-architectures-on-kubernetes-fd161170b0b5)**:
  This blog introduces Knative, a Kubernetes-based platform designed to simplify building and deploying serverless, event-driven applications.

- **What is Knative?** Knative is an open-source project that enables serverless workloads on Kubernetes, abstracting complexities of scaling and managing applications in a Kubernetes environment.
- **Core Components**:
  - **Knative Serving**: Handles requests by automatically scaling applications up or down based on demand, providing a smooth serverless experience.
  - **Knative Eventing**: Manages event-driven architecture, allowing components to trigger events and handle them asynchronously.
- **Benefits of Knative**: Knative simplifies the deployment of serverless workloads on Kubernetes, improves scalability, and supports event-driven architectures. It's suitable for organizations looking to leverage serverless computing while maintaining control over their Kubernetes infrastructure.
- **Use Cases**: Knative is ideal for microservices and event-driven architectures, enabling on-demand scaling and reducing infrastructure costs.

This blog provides insights into setting up Knative and demonstrates its effectiveness in creating scalable, serverless applications on Kubernetes.

---

### 3. Continuous Learning Path

Moving forward, my goal is to deepen my expertise in DevOps by exploring the following areas:

- **Infrastructure as Code (IaC)**: Learn tools like Terraform and Ansible to automate infrastructure provisioning and management.
- **Advanced Monitoring and Observability**: Delve into monitoring tools like Prometheus, Grafana, and ELK stack to gain visibility into system performance and reliability.
- **Security and Compliance**: Study DevSecOps practices to integrate security more seamlessly into the development pipeline.

Through consistent learning, practical projects, and sharing knowledge, I hope to continue contributing to the DevOps field and develop as a proficient DevOps engineer.

---

This guide provides an overview of my DevOps learning journey, my hands-on contributions through projects, and the knowledge I've shared with the community. I look forward to furthering my expertise and making a meaningful impact in the field of DevOps.



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

The proof of each DevOps tool applied in this project is documented [here](proof-of-concepts/proof.md).


---

## Expanding on DevOps Knowledge

In this section, I’ll provide a deeper look into the DevOps tools used in this project. Each guide includes the purpose of the tool, how it was applied, key concepts, and some common issues with solutions.

---

#### Docker: Containerization and Image Management
- **Purpose**: Docker allows for packaging applications into portable containers, which can run consistently across various environments.
- **Application in Project**: Containerized the Spring PetClinic application, making it easier to deploy and manage across different environments.
- **Key Commands**:
  - `docker build -t spring-petclinic .` - Build a Docker image from the Dockerfile.
  - `docker run -p 8080:8080 spring-petclinic` - Run the container, exposing the application on port 8080.
- **Common Issues and Solutions**:
  - **Issue**: Image build failure due to a missing dependency.
    - **Solution**: Check the Dockerfile for missing dependencies and ensure all required files are included in the build context.
  - **Issue**: "Container not found" error.
    - **Solution**: Use `docker images` to confirm the image name and tag. Rebuild if necessary.

---

#### Kubernetes: Deployment, Scaling, and Management
- **Purpose**: Kubernetes automates the deployment, scaling, and management of containerized applications.
- **Application in Project**: Deployed the Spring PetClinic application on Kubernetes, enabling auto-scaling and resilient management.
- **Key Concepts**:
  - **Pods**: The smallest deployable unit in Kubernetes, representing a single instance of the application.
  - **Services**: Expose Pods to the network, allowing communication between components.
  - **Deployments**: Manage and update sets of Pods.
- **Key Commands**:
  - `kubectl apply -f k8s-deployment.yaml` - Deploys or updates the application.
  - `kubectl get pods` - Lists all running pods in the cluster.
- **Common Issues and Solutions**:
  - **Issue**: "ImagePullBackOff" or "ErrImagePull" errors.
    - **Solution**: Ensure the image name and tag are correct, and the image is accessible in the registry.
  - **Issue**: Service not accessible.
    - **Solution**: Verify that the Service type (e.g., LoadBalancer, NodePort) is correctly configured for the desired level of access.

---

#### Knative: Serverless Capabilities and Automatic Scaling
- **Purpose**: Knative enables serverless deployment on Kubernetes, allowing the application to scale automatically based on demand.
- **Application in Project**: Configured Knative to handle dynamic scaling of the Spring PetClinic application based on traffic.
- **Key Components**:
  - **Services**: Manage the lifecycle and routing of the application.
  - **Revisions**: Track different versions of the application for seamless rollbacks and updates.
- **Key Commands**:
  - `kubectl apply -f knative-service.yaml` - Deploys the Knative service configuration.
  - `kubectl get ksvc` - Lists Knative services and their status.
- **Common Issues and Solutions**:
  - **Issue**: Knative service not reachable.
    - **Solution**: Ensure the Ingress configuration is correct, and verify if Knative Ingress Gateway is accessible.
  - **Issue**: Scaling not behaving as expected.
    - **Solution**: Check Knative autoscaler settings, and ensure resource requests and limits are properly configured.

---

#### Kyverno: Policy Management for Kubernetes
- **Purpose**: Kyverno provides Kubernetes-native policy management, enforcing best practices and security policies on resources.
- **Application in Project**: Applied policies to ensure that all Pods have specific labels, such as environment designation (e.g., `env: dev`).
- **Key Concepts**:
  - **Policies**: Define rules for compliance checks and validation.
  - **Admission Controllers**: Enforce policies during the creation or modification of resources.
- **Key Commands**:
  - `kubectl apply -f require-label.yaml` - Deploys a policy that requires all Pods to have the label `env: dev`.
  - `kubectl get cpol` - Lists all ClusterPolicies.
- **Common Issues and Solutions**:
  - **Issue**: Policy not enforced.
    - **Solution**: Verify that Kyverno is running and the policy YAML file is correctly applied.
  - **Issue**: Resource creation blocked by policy.
    - **Solution**: Check the policy details for required attributes and update the resource YAML to comply with policy rules.

---

#### Istio: Service Mesh and Traffic Management
- **Purpose**: Istio provides a service mesh to manage microservices traffic, security, and observability within Kubernetes clusters.
- **Application in Project**: Configured Istio to manage traffic routing for the Spring PetClinic application, enabling controlled ingress and observability.
- **Key Concepts**:
  - **Gateways**: Manage inbound traffic for the service mesh.
  - **Virtual Services**: Define traffic routing rules for services.
  - **Destination Rules**: Set policies for traffic flow to specific service versions.
- **Key Commands**:
  - `kubectl apply -f gateway.yaml` - Creates a Gateway for managing inbound traffic.
  - `kubectl apply -f virtualservice.yaml` - Defines the traffic rules for the service.
  - `kubectl get svc -n istio-system` - Lists Istio-related services.
- **Common Issues and Solutions**:
  - **Issue**: Gateway or Virtual Service not routing traffic.
    - **Solution**: Ensure both Gateway and Virtual Service configurations reference the correct hosts and services.
  - **Issue**: Services within the mesh are unreachable.
    - **Solution**: Verify the service annotations and check if Istio sidecar injection is enabled.

---

## My DevOps Journey

This repository showcases my learning and growth with the skills and tools in DevOps, focusing on containerization, CI/CD, and cloud-native applications.


## My Resume
[View my resume](Bashir_Ahmed_Resume.pdf)
