# Use the official Nginx base image
FROM nginx:alpine

# Set the working directory in the container
WORKDIR /usr/share/nginx/html

# Remove the default Nginx website files
RUN rm -rf ./*

# Copy your website files into the container
COPY ./ /usr/share/nginx/html/

# Expose port 80 for the web server
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]