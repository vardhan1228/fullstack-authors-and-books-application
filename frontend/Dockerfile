# Stage 1: Build React App
FROM node:18 AS build

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm install

COPY . .
RUN npm run build

# Stage 2: Serve with Apache HTTP Server
FROM httpd:2.4

# Copy the build output from the previous stage
COPY --from=build /app/dist/ /usr/local/apache2/htdocs/


# Expose port 80
EXPOSE 80

# Run the script before starting Apache
 CMD ["httpd-foreground"]
