# Use the official Nginx base image
FROM nginx:latest

# Copy your website files into the container
COPY /build/web /usr/share/nginx/html

# Expose port 80 to allow outside access
EXPOSE 80

# Start Nginx when the container launches
CMD ["nginx", "-g", "daemon off;"]
