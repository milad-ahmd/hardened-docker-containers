FROM postgres:latest

# Copy the hardened PostgreSQL configuration
COPY cis-postgresql.conf /etc/postgresql/postgresql.conf
COPY pg_hba.conf /etc/postgresql/pg_hba.conf

# Set appropriate permissions
RUN chmod 600 /etc/postgresql/postgresql.conf /etc/postgresql/pg_hba.conf

CMD ["postgres", "-c", "config_file=/etc/postgresql/postgresql.conf"]
