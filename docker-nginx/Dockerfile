# Use the official Nginx image from Docker Hub
FROM nginx:alpine

# Copy your Nginx configuration file
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy your HTML file to the Nginx web root
COPY index.html /usr/share/nginx/html/index.html

# Expose port 80
EXPOSE 80

# Start Nginx when the container starts
CMD ["nginx", "-g", "daemon off;"]
