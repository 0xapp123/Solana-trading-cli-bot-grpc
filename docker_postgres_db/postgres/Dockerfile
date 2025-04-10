FROM postgres:16-alpine

# Create directory first
RUN mkdir -p /etc/postgresql

# Add custom configurations
COPY postgresql.conf /etc/postgresql/postgresql.conf
COPY init-scripts/ /docker-entrypoint-initdb.d/

# Set proper permissions (make postgres user own the config)
RUN chown postgres:postgres /etc/postgresql/postgresql.conf && \
    chmod 600 /etc/postgresql/postgresql.conf && \
    chmod -R 755 /docker-entrypoint-initdb.d/

# Use custom config file
CMD ["postgres", "-c", "config_file=/etc/postgresql/postgresql.conf"]