It is a template of Maven running in a docker container 

# Maven commands

Create a project

- mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false

| DgroupId = [package-name] 
| DartifactId = [project-name] 

Build project (it will create .jar)

- mvn package

- mvn -f [pom-project-path] clean package
- mvn -f /usr/app/my-app/pom.xml clean package

Run .jar

- java -cp target/[jar-name] [package-name].[class-name] 
- java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App 

Install packages

- mvn clean install (in a project already created)

# Useful links

- https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

# Install

mvn -DskipTests install
mvn install
mvn package

cd /usr/app/

cp /usr/app/lib/rt.jar /usr/local/openjdk-11/lib/

# Docker 

sudo service docker start
docker-compose up
docker-compose build --no-cache
docker exec -it flowdroid-securibench /bin/bash
cd /usr/app/app_folder_name

## Test

mvn compile test

mvn test -Dtest=soot.jimple.infoflow.test.securibench.AliasingTests
mvn test -Dtest=soot.jimple.infoflow.test.junit.TypeTests
mvn test -Dtest="soot.jimple.infoflow.test.junit.TypeTests#stringToObjectTest()"

mvn package -Dmaven.test.skip=true

mvn test -Dtest="soot.jimple.infoflow.test.securibench.**"
mvn test -Dtest="soot.jimple.infoflow.test.junit.**"
mvn test -Dtest=SessionTests
https://stackoverflow.com/questions/6819888/how-to-run-all-tests-in-a-particular-package-with-maven
