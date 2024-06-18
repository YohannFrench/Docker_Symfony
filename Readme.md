# Docker Symfony :
- Symfony: 7.1.1
- Nginx: latest

This docker allow you to create a new Symfony project with Nginx server.

In a terminal, create the containers :
    - "docker compose up"

Create Symfony application, by going inside the php container :
    - "docker exec -it php_container bash"
    - "composer create-project symfony/skeleton:"7.1.*" symfony"
    - "cd symfony"
    - "composer install"
    - "composer require webapp"
    - Say "No" for Docker configuration
    - "symfony serve" -> http://127.0.0.1:8000
    
