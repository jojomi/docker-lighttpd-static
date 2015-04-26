# docker-lighttpd-static

Docker container for serving static content using lighttpd


## Executing

    docker run --name "my-lighttpd" -P -v $(pwd)/example-content:/var/www jojomi/lighttpd-static

Find your container:

    docker ps | grep "my-lighttpd"
    CONTAINER ID        IMAGE                           COMMAND                CREATED             STATUS              PORTS                   NAMES
    ba00b5c238fc        jojomi/lighttpd-static:latest   "lighttpd -D -f /etc   1 second ago        Up 1 second         0.0.0.0:49153->80/tcp   my-lighttpd

Check if it works:

    curl localhost:49153
    This is your content.


## Building The Image Yourself (optional)

    docker build -t jojomi/latex .

The image is conveniently small at **below 7 MB** thanks to [alpine](http://gliderlabs.viewdocs.io/docker-alpine):

    docker images | grep lighttp
    jojomi/lighttpd-static   latest              b2e7a8364baa        1 second ago      6.451 MB