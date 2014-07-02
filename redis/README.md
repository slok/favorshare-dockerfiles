Build the image:

    docker build -t slok/redis .

Run the image with exposed ports:
    
    docker run -d -P slok/redis

Check that is running:

    docker ps

And the result:

    CONTAINER ID        IMAGE                COMMAND                CREATED             STATUS              PORTS                     NAMES
    6d4c1a61cefc        slok/redis2:latest   /usr/bin/redis-serve   39 seconds ago      Up 38 seconds       0.0.0.0:49153->6379/tcp   mad_brattain

We can connect to port 49153