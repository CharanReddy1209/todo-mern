FROM node:14-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY . .

FROM node:14-alpine 
WORKDIR /app
COPY --from=build /app .
EXPOSE 8080
CMD ["node", "index.js"]