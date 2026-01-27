FROM maven:3.8.3-openjdk-17
LABEL name="rushidholecom"

SHELL [ "/bin/bash" ]
USER root

#RUN apt update -y && apt install openjdk-17-jdk git maven -y

WORKDIR /opt

RUN git clone https://github.com/rushidholecom/EasyCRUD.git

WORKDIR /EasyCRUD/backend

COPY application.properties src/main/resources/application.properties

RUN mvn clean package -DskipTests

EXPOSE 8080

ENTRYPOINT [ "java", "-jar", "target/student-registration-backend-0.0.1-SNAPSHOT.jar" ]