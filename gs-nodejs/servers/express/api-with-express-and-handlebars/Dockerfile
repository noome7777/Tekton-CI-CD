# servers/express/api-with-express-and-handlebars/Dockerfile
FROM node:18-alpine
WORKDIR /app

# 의존성 먼저
COPY package*.json ./
RUN npm ci --only=production

# 소스 복사
COPY . .

EXPOSE 3000
CMD ["npm","start"]
