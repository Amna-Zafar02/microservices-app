FROM mysql:5.7

# Set environment variables for MySQL
ENV MYSQL_ROOT_PASSWORD=rootpassword
ENV MYSQL_DATABASE=mydatabase
ENV MYSQL_USER=myuser
ENV MYSQL_PASSWORD=mypassword

# Expose the default MySQL port
EXPOSE 3306  # MySQL runs on port 3306

# Copy any initialization SQL scripts into the container
COPY ./init.sql /docker-entrypoint-initdb.d/

CMD ["mysqld"]

