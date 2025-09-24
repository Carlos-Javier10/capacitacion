# Dockerfile para frontend Vite/React
FROM node:20-alpine

ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL

WORKDIR /app

COPY package.json .
RUN npm install --production
COPY . .

RUN npm run build

EXPOSE 5173

CMD ["npm", "run", "preview"]
