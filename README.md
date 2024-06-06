# Capstone Helm Chart

This Helm chart is designed to deploy a vulnerable web application stack consisting of Nginx and PHP 8.3 (PHP-FPM) containers to a Kubernetes cluster. It provides a convenient way to deploy and manage the application stack using Helm.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed:

- Helm 3.x
- Kubernetes cluster

## Installation

To install the Helm chart, follow these steps:

1. Clone the repository:

```bash
git clone https://github.com/elysiansky/capstone-chart-vulnerable-php83.git
```

2. Navigate to the chart directory:
```bash
cd capstone-chart-vulnerable-php83
```

3. Install the Helm chart:
```bash
helm install my-release .
```

## Configuration

The following table lists the configurable parameters of the Helm chart and their default values. You can override these values by creating a custom values.yaml file or passing them as arguments during installation.

| Parameter           | Description                          | Default  |
|---------------------|--------------------------------------|----------|
| `replicaCount`      | Number of replicas                  | `1`      |
| `image.repository`  | Container image repository           | `nginx`  |
| `image.tag`         | Container image tag                  | `latest` |
| `service.type`      | Service type (ClusterIP, NodePort)   | `ClusterIP` |
| `service.port`      | Service port                         | `80`     |
| `ingress.enabled`   | Enable Ingress                       | `false`  |
| `resources.limits`  | Resource limits                      | `{}`     |
| `resources.requests`| Resource requests                    | `{}`     |



## Usage
Once the Helm chart is installed, you can access the application by forwarding the service port or configuring an Ingress.

To forward the service port:
```bash
kubectl port-forward svc/<RELEASE_NAME> 8080:80
```
Replace <RELEASE_NAME> with the name of your Helm release.

## Uninstallation
To uninstall the Helm chart, run:
```bash
helm uninstall my-release
```

### Contributing
If you find any issues with the Helm chart or have suggestions for improvements, please open an issue or submit a pull request.