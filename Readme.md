# Docker Symfony
- Composer
- Symfony
- Nginx

This docker allow you to create a new Symfony project with Nginx server.

In a terminal, create the containers :

    docker compose up

Then, go inside the php container with this command :

    docker exec -it php_container bash

A terminal is created inside the container where you can create a Symfony application :

    composer create-project symfony/skeleton:"7.1.*" symfony
    cd symfony
    composer install
    composer require webapp

It will ask you if you want docker configuration in your project. Depends on your requirements.
Finally, you can launch the application with :

    symfony serve" -> http://127.0.0.1:8000
    
