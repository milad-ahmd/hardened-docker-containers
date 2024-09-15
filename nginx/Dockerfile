FROM nginx:latest

# Copy hardened NGINX configuration
COPY cis-nginx.conf /etc/nginx/nginx.conf

# Set file permissions
RUN chmod 600 /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]
