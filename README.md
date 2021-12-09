# udagram-refactor

Udagram is a simple cloud application, which is developed while enrollment in the *Udacity Nanodegree - Cloud Developer*. 
The main achievement in this project was to refactor a monolith to a microservice based cloud application. 

This is achieved by splitting the monolith into 4 parts:
- Frontend
- Rest-Api-Feed
- Rest-Api-User
- A reverseproxy

Everything is deployed via EKS in AWS.

The subprojects are included in this repositor as submodules. For getting everything to work as excpected locally a `.env` file is required in each of the repository. In this file it is possible to store your environment variables. 
You can include such a file in Docker Compse with the parameter `--env-file .env`. 

## Udagram-api-frontend [![Docker Image CI + Push](https://github.com/samuelspagl/udagram-frontend/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/samuelspagl/udagram-frontend/actions/workflows/main.yml)

This project is build using Typescript and the Ionic framework. For more instructions how to start, please look into the repository.

## Udagram-api-feed [![Docker Image CI + Push](https://github.com/samuelspagl/udagram-api-feed/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/samuelspagl/udagram-api-feed/actions/workflows/main.yml)

## Udagram-api-user [![Docker Image CI + Push](https://github.com/samuelspagl/udagram-api-user/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/samuelspagl/udagram-api-user/actions/workflows/main.yml)

## Udagram-reverseproxy [![Docker Image CI + Push](https://github.com/samuelspagl/udagram-reverseproxy/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/samuelspagl/udagram-reverseproxy/actions/workflows/main.yml)

## Screenshots: 

### Creating GitHub Repositories for each of the parts, and dockerize them:
![Github Repositories](./screenshots/Git_Repositories.png)
![Docker Repositories](./screenshots/docker_repositories.png)

### Setting up a GitHub Actions CI Pipeline
This part differs a bit of the script, as I am not using TravisCI but Github Actions. This has two main reasons:
- First in a "real world" implementation each of the microservices would be independent repositories
- Second these repositories would be wanted to be build at seperate times, because multiple teams are working on these. 
Additionally TravisCI is requiring a CreditCard as they have a "Freemium" Model. Github Actions are completly free for public repositories.

![Sample Action](./screenshots/GitCI_sample_action.png)
![GitCi Frontend](./screenshots/GitCI_frontend.png)
![GitCi Api-Feed](./screenshots/GitCI_api_feed.png)
![GitCi Api-User](./screenshots/GitCI_api_user.png)
![GitCi ReverseProxy](./screenshots/GitCI_reverseproxy.png)

### Setting up a kubernetes cluster on AWS
![Kubernetes pods](./screenshots/kubectl_get_pods_2.png)
![Kubernetes services](./screenshots/kubectl_get_services.png)

### Finished work:
![Udagram](./Udagram_deployment_frontend.png)

More screenshots can be found in the screenshots folder.
