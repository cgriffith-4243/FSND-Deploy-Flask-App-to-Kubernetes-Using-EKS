# Kubernetes Flask App

## Demo App

This project is a demo application meant to demonstrate the capability of containerizing and deploying a Flask based API to a Kubernetes cluster using Docker, AWS, EKS, CodePipeline, and CodeBuild.

The Flask app that will be used for this project consists of a simple API with three endpoints:

- `GET '/'`: This is a simple health check, which returns the response 'Healthy'. 
- `POST '/auth'`: This takes a email and password as json arguments and returns a JWT based on a custom secret.
- `GET '/contents'`: This requires a valid JWT, and returns the un-encrpyted contents of that token. 

The app relies on a secret set as the environment variable `JWT_SECRET` to produce a JWT. This application uses [Gunicorn](https://gunicorn.org/) server when deploying the app.
     
## Deployment Steps Overview

The following steps were taken in order to deploy the API:

1. Wrote a Dockerfile for a simple Flask API
2. Built and tested the container locally
3. Created an EKS cluster
4. Stored a secret using AWS Parameter Store
5. Created a CodePipeline pipeline triggered by GitHub checkins
6. Created a CodeBuild stage which will build, test, and deploy your code

This resulted in a successful deployment of the API to the AWS cloud.

## Reflection

This was a project created while learning full stack development in Flask and Python. The project goals were to teach myself new skills, furthering my understanding of AWS and Kubernetes. The idea is that the steps taken in this project can be used to containerize and deploy any Flask application to the AWS cloud.

## Authors

Cameron Griffith added / set up the configuration files for Docker, AWS, EKS, CodePipeline, and CodeBuild.

The base code for this project was created by [`Udacity`](https://www.udacity.com) as part of the [`Full Stack Web Developer Nanodegree`](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd0044) program.
