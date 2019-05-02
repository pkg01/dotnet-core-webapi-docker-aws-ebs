These are the commands used to perform this experiment.

#### Create a docker image for dotnet core application (webapi)
1. Create a dotnet core webapi

    ```
    dotnet new webapi -o mywebapi
    ```

2. Create the Dockerfile to publish dotnet core application and to create an image containing published application

    ```
    Dockerfile
    ```

3. Build the docker image

    ```
    docker build -t pkg01/mywebapi:v1 .
    ```

4. Push docker image to docket hub repository

    ```
    docker login
    docker push pkg01/mywebapi:v1
    ```

Resources :

https://docs.docker.com/engine/examples/dotnetcore/

#### Run docker container locally
1. Run following command to run container on local system

    ```
    docker run -it --rm -p 80:80 --name mywebapi pkg01/mywebapi:v1
    ```

2. Go to http://localhost/api/values in favorite browser.

#### Deploy dotnet core container to AWS Elastic Beanstalk

1. Create a Dockerrun.aws.json file

    ```
    Dockerrun.aws.json
    ```

2. Create a Elastic Beanstalk application in AWS console
3. Create an environment in the new application by upload the Dockerrun.aws.json file and configuring vpc and security group.
4. Access application using elastic beanstalk url or instance private ip(Depending upon the elastic beanstalk and vpc configuration).

Resources:

[https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker_v2config.html#create_deploy_docker_v2config_dockerrun](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker_v2config.html#create_deploy_docker_v2config_dockerrun)

[https://www.youtube.com/watch?v=lBu7Ov3Rt-M](https://www.youtube.com/watch?v=lBu7Ov3Rt-M)
