### Spring Boot based Java web application
_________________________________________
This is a simple Sprint Boot based Java application that can be built using Maven. Sprint Boot dependencies are handled using the pom.xml at the root directory of the repository.

This is a MVC architecture based application where controller returns a page with title and message attributes to the view.

### Execute the application locally and access it using your browser
_____________________________________________________________________
Checkout the repo and move to the directory
```bash
git clone https://github.com/vasim0909/end-to-end-cicd-pipeline/Java-Maven-Sonar-Argocd-K8s/sprint-boot-app
cd java-maven-sonar-argocd-helm-k8s/sprint-boot-app
```

Execute the Maven targets to generate the artifacts
```bash
mvn clean package
```

The above maven target stroes the artifacts to the target directory. You can either execute the artifact on your local machine (or) run it as a Docker container.

** Note: To avoid issues with local setup, Java versions and other dependencies, I would recommend the docker way. **

### Execute locally (Java 11 needed) and access the application on http://localhost:8080
```bash
java -jar target/spring-boot-web.jar
```

### The Docker Way
Build the Docker Image

```bash
docker build -t ultimate-cicd-pipeline:v1 .
```

```bash
docker run -d -p 8010:8080 -t ultimate-cicd-pipeline:v1
```

Hurray !! Access the application on http://<ip-address>:8010

### Next Step
## Configure Sonar Server  locally

```bash
System Requirements
Java 17+ (Oracle JDK, OpenJDK, or AdoptOpenJDK)
Hardware Recommendations:
   Minimum 2 GB RAM
   2 CPU cores
sudo apt update && sudo apt install unzip -y
adduser sonarqube
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.4.1.88267.zip
unzip *
chown -R sonarqube:sonarqube /opt/sonarqube
chmod -R 775 /opt/sonarqube
cd sonarqube-10.4.1.88267/bin/linux-x86-64
./sonar.sh start
```
