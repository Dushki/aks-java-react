FROM maven:3.8.4-openjdk-11-slim
# Set the working directory in the container
WORKDIR /app
# Copy the Maven configuration file and package.json to the working directory
COPY pom.xml .
COPY package.json .
# Download dependencies defined in the pom.xml
RUN mvn dependency:go-offline
# Copy the application source code
COPY . .
# Build the application
RUN mvn -B -DskipTests package
# Expose the port that the application runs on
EXPOSE 8080
# Command to run the application
CMD ["java", "-jar", "target/backend.jar"]
