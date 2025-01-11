# TNTK Orders

## Overview

The `tntk-orders` project is a microservice-based application designed to manage orders, products, and payments. It is built using Python and FastAPI, with a PostgreSQL database for data storage, Redis for caching, and RabbitMQ for message queuing. The application is containerized using Docker and can be deployed using Helm on Kubernetes.

## Project Structure

- **src/**: Contains the main application code, including models, routes, and utilities.
  - **order/**: Handles order-related operations.
  - **root/**: Contains core configurations and database setup.
  - **alembic/**: Manages database migrations.
- **Dockerfile**: Defines the Docker image for the application.
- **docker-compose.yml**: Provides a multi-container Docker application setup.
- **.github/workflows/ci.yml**: GitHub Actions workflow for CI/CD.
- **requirements.txt**: Lists the Python dependencies for the project.

## Prerequisites

- Docker
- Docker Compose
- Kubernetes and Helm (for deployment)
- Python 3.10 or later

## Getting Started

### Running Locally with Docker

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/tntk-orders.git
   cd tntk-orders
   ```

2. **Build and Run the Docker Containers**

   ```bash
   docker-compose up --build
   ```

   This command will build the Docker images and start the containers for the application, PostgreSQL, Redis, and RabbitMQ.

3. **Access the Application**

   The application will be accessible at `http://localhost:8001`.

### Deploying with Helm

1. **Package the Helm Chart**

   Ensure you have a Helm chart in your repository. If not, create one using:

   ```bash
   helm create tntk-orders-chart
   ```

2. **Deploy the Application**

   ```bash
   helm install tntk-orders ./tntk-orders-chart
   ```

   This command will deploy the application to your Kubernetes cluster using the Helm chart.

3. **Verify Deployment**

   Check the status of your deployment:

   ```bash
   kubectl get pods
   ```

   Ensure all pods are running successfully.

## CI/CD Pipeline

The project uses GitHub Actions for continuous integration and deployment. The workflow defined in `.github/workflows/ci.yml` builds Docker images and updates Kubernetes manifests on pushes to the `main` and `stage` branches.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any improvements or bug fixes.

## Contact

For any questions or issues, please contact the project maintainers at [support@tentek.com](mailto:support@tentek.com).
