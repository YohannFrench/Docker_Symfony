FROM nginx:latest

#COPY nginx.conf /etc/nginx/
COPY docker/nginx/conf.d/symfony.conf /etc/nginx/conf.d/

RUN echo "upstream php-upstream { server php:8000; }" > /etc/nginx/conf.d/upstream.conf

# Verify the installation
CMD ["nginx"]

EXPOSE 80
EXPOSE 443 