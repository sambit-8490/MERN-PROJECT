FROM node:18-slim

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm install --production

COPY . .

EXPOSE 5050

CMD ["npm", "start"]
