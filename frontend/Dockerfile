# Use Node.js to build React app
FROM node:18 AS builder
WORKDIR /app
COPY . .
RUN npm install && npm run build

# Use Nginx to serve React app
FROM nginx:latest
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]