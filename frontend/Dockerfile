# Stage 1: Build the Angular app
FROM node:18 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine
# Copy the build output to replace the default nginx contents.
# NOTE: We use a wildcard (*) because Angular builds into 'dist/project-name'
COPY --from=build /app/dist/*/ /usr/share/nginx/html/

# Expose port 80
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
