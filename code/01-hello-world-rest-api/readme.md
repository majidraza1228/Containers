# Hello World Rest API

This hello-world is built upon the opinionated spring-boot framework to get start on Microservices quickly.

## Steps to run this app in AWS Beanstalk:
1. Create deployable archive - Go to Terminal (Linux/MacOS)/Command prompt (Windows) and type/enter "mvn clean package"
2. Login to your aws account
3. Go to Beanstalk and Click on Create Application
4. Fill the application name of your choice
5. Select Java as your deployment Platform
6. Upload "01-aws-hello-world-rest-api-1.0.0-RELEASE.jar" file which is located under target folder
7. Click on Create Application; Within a minute, your application environment should be up
8. Security Group update - 
    8a. Find the Security Group associated to Beanstalk (Configuration --> Lookup the value for "EC2 security groups")
    8b. Go to EC2 --> Security Groups --> Paste the Security Group value for Search
    8c. Go to Inbound tab and Click on Edit
    8d. Click on Add Rule button,
    8e. Select Custom TCP Rule for Type, 
    8f. Enter 3100 under Port Range,
    8g. Hit Save
9. Go to the Hello World URL. <beanstalk_endpoint:3100>/hello-world
    9a. Go to Your Beanstalk Application home page,
    9b. Endpoint is listed under the Beanstalk Application Name

## Beanstalk Test URLs

- http://<beanstalk_endpoint>:3100/hello-world

```txt
Hello World
```

- http://<beanstalk_endpoint>:3100/hello-world-bean

```json
{"message":"Hello World - Changed"}
```

- http://<beanstalk_endpoint>:3100/hello-world/path-variable/in28minutes

```json
{"message":"Hello World, in28minutes"}
```


## About this Hello Work Java Service
- Main class com.in28minutes.rest.webservices.restfulwebservices.RestfulWebServicesApplication 


## Steps to run this app locally:
1. Create deployable archive - Go to Terminal (Linux/MacOS)/Command prompt (Windows) and type/enter "mvn clean package"
2. docker run --publish 3100:80 in28min/aws-hello-world-rest-api:0.0.1-SNAPSHOT

```
docker login
docker push @@REPO@@/aws-hello-world-rest-api:0.0.1-SNAPSHOT
```


## Test URLs

- http://localhost:3100/hello-world

```txt
Hello World
```

- http://localhost:3100/hello-world-bean

```json
{"message":"Hello World - Changed"}
```

- http://localhost:3100/hello-world/path-variable/in28minutes

```json
{"message":"Hello World, in28minutes"}
```


- If you change server.port to 80, you cannot run this app on local as it is configured to run on port 80 - https://serverfault.com/questions/112795/how-to-run-a-server-on-port-80-as-a-normal-user-on-linux. You can run it as a docker container as shown below
