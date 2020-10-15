# udacity-c3-deployment

Config for Udagram project

# GitHub Repos & Travis CI

There are four GitHib repos.  One for each microservice, one for a reverse proxy, and one for the front end.  Each repo containa Travis CI yaml file.

https://github.com/herniated/udacity-c3-restapi-user
https://github.com/herniated/udacity-c3-restapi-feed
https://github.com/herniated/udacity-c3-reverseproxy
https://github.com/herniated/udacity-c3-frontend

# Dependencies

### Database
A PostgreSQL database either locally or on AWS RDS.  Instructions included in microservices' repos.

### S3
An AWS S3 bucket.  Instructions included in the feed repo.

# Install

Instructions to install the microservices manually in a local environment are in each repo.

# Docker Hub Images

https://hub.docker.com/repository/docker/herniated/udacity-c3-restapi-user
https://hub.docker.com/repository/docker/herniated/udacity-c3-restapi-feed
https://hub.docker.com/repository/docker/herniated/udacity-c3-reverseproxy
https://hub.docker.com/repository/docker/herniated/udacity-c3-frontend

# Kubernetes Configuration

1. Add Env Vars to Config Map (update yaml with appropriate values)
    ```bash
    kubectl apply -f env-configmap.yaml
    ```
2. Add Secret Env Vars to Secrets (update yaml with appropriate values)
    ```bash
    kubectl apply -f env-secret.yaml
    ```
3. Add AWS Config as a Volume (update yaml with appropriate values)
    ```bash
    kubectl apply -f aws-secret.yaml
    ```
4. Add user deployment
    ```bash
    kubectl apply -f backend-user-deployment.yaml
    ```
5. Add user service
    ```bash
    kubectl apply -f backend-user-service.yaml
    ```
4. Add feed deployment
    ```bash
    kubectl apply -f backend-feed-deployment.yaml
    ```
5. Add feed service
    ```bash
    kubectl apply -f backend-feed-service.yaml
    ```
6. Add reverseproxy deployment
    ```bash
    kubectl apply -f reverseproxy-deployment.yaml
    ```
7. Add reverseproxy service
    ```bash
    kubectl apply -f reverseproxy-service.yaml
    ```
8. Add frontend deployment
    ```bash
    kubectl apply -f frontend-deployment.yaml
    ```
9. Add frontend service
    ```bash
    kubectl apply -f frontend-service.yaml
    ```
10. Add port forwarding (for testing only)
    ```bash
    kubectl port-forward service/frontend 8100:8100
    ```

# Screenshots

See screenshots directory to help with review.
