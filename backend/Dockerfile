FROM eclipse-temurin:22-jdk-alpine as build

# Copier le fichier JAR du backend
COPY ./Brikol-0.0.1-SNAPSHOT.jar /app/brikol-backend.jar

WORKDIR /app

# Exposer le port 8080
EXPOSE 8080

# Lancer l'application
CMD ["java", "-jar", "brikol-backend.jar"]
