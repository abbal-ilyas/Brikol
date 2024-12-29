# Étape de construction : construction de l'application
FROM eclipse-temurin:22-jdk-alpine as build

# Copier le fichier JAR du backend
COPY ./Brikol-0.0.1-SNAPSHOT.jar /app/brikol-backend.jar

WORKDIR /app

# Étape de runtime : utiliser une image plus légère pour l'exécution
FROM eclipse-temurin:22-jre-alpine

# Copier le JAR construit à partir de l'étape précédente
COPY --from=build /app/brikol-backend.jar /app/brikol-backend.jar

WORKDIR /app

# Exposer le port 8080 pour l'application
EXPOSE 8080

# Lancer l'application
CMD ["java", "-jar", "brikol-backend.jar"]
