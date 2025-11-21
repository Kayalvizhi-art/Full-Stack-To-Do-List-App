# -----------------------------------------------
# 1️⃣ Stage 1 — Build Angular App
# -----------------------------------------------
FROM node:18-alpine AS build

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy project files
COPY . .

# Build Angular for production
RUN npm run build --prod

# -----------------------------------------------
# 2️⃣ Stage 2 — Serve Angular using NGINX
# -----------------------------------------------
FROM nginx:alpine

# Copy built files to NGINX html folder
COPY --from=build /app/dist/* /usr/share/nginx/html

# Expose frontend port
EXPOSE 80

# Start NGINX
CMD ["nginx", "-g", "daemon off;"]
