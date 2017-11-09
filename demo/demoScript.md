# Manual Demo

Check current state

    docker images
    docker ps --all

Start container interactively

    docker run -i -t ubuntu /bin/bash
    
Update install Apache2 (back to slides)

    apt update && apt-get install -y apache2

Start Apache2 service

    service apache2 start

Check IP address and show function

    docker inspect container_name

Create Image

    docker commit container_name tgeorge/apache-manual
    
Show layers

    docker history tgeorge/apache-manual

# Dockerfile Demo

Build and run image

    docker build -t tgeorge/apache-auto apache/
    docker build -t tgeorge/apache-auto:0.1.0 apache/
    docker run -d -P tgeorge/apache-auto

Mount local volume to container

    docker run -d -P -v /home/tgeorge/Development/presentation-containerbasics/demo/www/:/var/www tgeorge/test
    
Clean up containers
    
    docker stop $(docker ps -q)
    docker rm $(docker ps -a -q)
