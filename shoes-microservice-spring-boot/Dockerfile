#FROM maven as build
#WORKDIR /app
#COPY . .
#RUN mvn install

#FROM openjdk:11.0.10-jre
#WORKDIR /app
#COPY --from=build /app/target/shoes-0.0.1-SNAPSHOT.jar /app/
#EXPOSE 1002
#CMD [ "java", "-jar", "shoes-0.0.1-SNAPSHOT.jar"]

#FROM openjdk:11.0.10-jre-slim

#WORKDIR /app

# Install Maven (not recommended for production)
#RUN apt-get update && \
 #   apt-get install -y maven && \
  #  rm -rf /var/lib/apt/lists/*

# Copy project files
#COPY . .

# Build the project
#RUN mvn clean package

# Expose port
#EXPOSE 1002

# Run the application
#CMD ["java", "-jar", "target/shoes-0.0.1-SNAPSHOT.jar"]

FROM openjdk:11-slim
WORKDIR /app
RUN apt-get update && apt-get install -y maven
COPY . .
RUN mvn clean package -DskipTests=true
EXPOSE 1002
ENTRYPOINT ["java", "-jar", "target/shoes-0.0.1-SNAPSHOT.jar"]
