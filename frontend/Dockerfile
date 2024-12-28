FROM node:20-alpine AS build

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers nécessaires
COPY package*.json ./
RUN npm install

# Copier tout le code
COPY . .

# Construire l'application Next.js
RUN npm run build

# Étape finale : Servir l'application
FROM node:20-alpine
WORKDIR /app
COPY --from=build /app ./

# Installer le serveur de production Next.js
RUN npm install next

# Exposer le port 3000
EXPOSE 3000

# Lancer l'application
CMD ["npm", "run", "start"]
