# Dockerfile para frontend Vite/React
FROM node:20-alpine

# Definir build args
ARG VITE_API_URL

# Establecer como variable de entorno
ENV VITE_API_URL=$VITE_API_URL

WORKDIR /app

COPY package.json ./
RUN npm install --production
COPY . ./

RUN npm run build

EXPOSE 5173

CMD ["npm", "run", "preview"]
