# Stage 1: Build the React frontend
FROM node:18-slim AS builder

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm install

COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy the built files from previous stage
COPY --from=builder /app/dist /usr/share/nginx/html

# Remove default nginx config and replace with custom (optional)
# COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
