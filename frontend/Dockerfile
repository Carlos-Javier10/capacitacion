# Stage 1: Build
FROM node:20-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

ARG API_URL
ENV VITE_API_URL=${API_URL}

RUN npm run build

# Stage 2: Serve
FROM node:20-alpine AS production

WORKDIR /app

# Instalar "serve" globalmente para servir la app
RUN npm install -g serve

# Copiar solo lo necesario del build
COPY --from=build /app/dist ./dist

EXPOSE 3000

# Usamos serve para servir la carpeta dist
CMD ["serve", "-s", "dist", "-l", "3000"]

