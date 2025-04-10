FROM postgres:16-alpine

# Add custom configurations
COPY postgresql.conf /etc/postgresql/postgresql.conf

# Set proper permissions
RUN chmod 600 /etc/postgresql/postgresql.conf

# Use custom config file
CMD ["postgres", "-c", "config_file=/etc/postgresql/postgresql.conf"]