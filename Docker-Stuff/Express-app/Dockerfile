# Stage 1 ---- Build stage
FROM node:22-alpine AS build-stage

WORKDIR /app

COPY package*.json ./

RUN npm install 

COPY . .

# Stage 2 -- Production STage 
FROM node:22-alpine 

WORKDIR /app

COPY --from=build-stage /app /app

EXPOSE 3000

ENV PORT=3000

CMD ["node", "index.js"]
