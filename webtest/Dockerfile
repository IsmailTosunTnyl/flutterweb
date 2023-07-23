# Use the official Flutter base image with the webdev tool installed
FROM ghcr.io/cirruslabs/flutter:3.10.6 as builder

# Set the working directory inside the container
WORKDIR /app

# Copy the entire Flutter web project to the container
COPY . .

# Install dependencies
RUN flutter pub get

# Build the Flutter web project
RUN flutter build web --release

# Use the official Nginx base image
FROM nginx:latest

# Copy the built Flutter web files into the Nginx HTML directory
COPY --from=builder /app/build/web /usr/share/nginx/html

# Expose port 80 to allow outside access
EXPOSE 80

# Start Nginx when the container launches
CMD ["nginx", "-g", "daemon off;"]
