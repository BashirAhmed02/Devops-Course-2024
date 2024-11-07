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
