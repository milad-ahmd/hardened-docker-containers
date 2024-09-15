FROM mongo:latest

# Copy hardened MongoDB configuration file
COPY cis-mongodb.conf /etc/mongod.conf

# Set appropriate permissions for the configuration file
RUN chmod 600 /etc/mongod.conf

CMD ["mongod", "--config", "/etc/mongod.conf"]
