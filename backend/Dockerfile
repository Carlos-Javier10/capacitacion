# Dockerfile para backend Node.js
FROM node:20-alpine

ARG PORT=3000
ARG API_MESSAGE="Backend con variables de entorno 🚀"

# Variables de entorno
ENV PORT=$PORT
ENV API_MESSAGE=$API_MESSAGE

WORKDIR /app

COPY package.json .
RUN npm install --production
COPY . .

EXPOSE $PORT

CMD ["node", "index.js"]
