# Jenkins_full
Multiple configured docker images offering configured jenkins service with some quality contorl tools like sonarqube and checkstyle.

# How to use?
Execute `$ docker-compose up` in project folder after running docker.

## Network
After running docker compose, you can access to services each via custom port.

| service            | address                 |
| ------------------ |:------------------------|
| jekins             | http://localhost:8080   |
| sonarqube          | http://localhost:9000   |
| tomcat integration | http://localhost:8090   |
| tomcat production  | http://localhost:8091   |

# Example
This is an example of configured build and testing pipeline for maven project using docker image for each service.

This is example contains different steps:
1. Compile the project using `maven`
2. Parallel pipeline:  
  * test the code using `checkstyle` jenkins plugin
  * push the code to local `sonarqube` to analyse it
  * deploy the application in `tomcat` integration server
3. If the deployment was successfully done, the admin can deploy the code on the `tomcat production server` 
after revising the `checkstyle` and `sonarqube` report and testing the app on the `tomcat integration server`

# What's next ?
- Add fully configured jenkins image in dockerhub
- Provide other services to the project
