FROM alpine
 
# Install git, maven
RUN apk update && apk add git maven
 
# Set the working directory in the container
WORKDIR /app
 
# Clone the Spring Petclinic repository
RUN git clone https://github.com/dockersamples/spring-petclinic-docker.git
 
# Set the working directory to the cloned repository
WORKDIR /app/spring-petclinic-docker
 
# Build the Spring Petclinic application using Maven Wrapper
RUN ./mvnw package
 
# Expose the application port
EXPOSE 8080
 
# Correct the ENTRYPOINT line
CMD ["java", "-jar", "/app/spring-petclinic-docker/target/spring-petclinic-2.7.0-SNAPSHOT.jar"]
