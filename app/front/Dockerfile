# Use apache as base image
FROM nginx

# Set environment variable for back-end URL
ENV WS_BACK_URL=http://localhost:8080

# Copy HTML files and style.css to Apache's default public directory
COPY . /usr/share/nginx/html

# Copy entrypoint script to container
COPY entrypoint.sh /usr/local/apache2/htdocs/entrypoint.sh

# Grant execute permission to entrypoint script
RUN chmod +x /usr/local/apache2/htdocs/entrypoint.sh

# Expose port 80
EXPOSE 80

# Use exec form for entrypoint
ENTRYPOINT ["/usr/local/apache2/htdocs/entrypoint.sh"]
