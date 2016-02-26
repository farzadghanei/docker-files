Robomongo Dockerfile
====================

Build Docker image for [Robomongo](<https://robomongo.org>).

The image uses essential packages to run and use Robomongo.
Some features like changing the theme are not considered essential.

Installing *libqt5gui5* would fix this, but will increase the size of the image.


Build the image


```
docker build -t local/robomongo
```


Then run the app with a command like this:


```
docker run --rm -it -v /tmp/.X11-unix/:/tmp/.X11-unix -e DISPLAY=$DISPLAY local/robomongo
```


Or if you wanted to connect to MongoDB running on the host:


```
docker run --rm -it -v /tmp/.X11-unix/:/tmp/.X11-unix -e DISPLAY=$DISPLAY --add-host=dockerhost:$(ip -4 addr show scope global dev docker0 | grep inet | awk '{print $2}' | cut -d / -f 1) local/robomongo
```


Now when creating a new connection, use *dockerhost* as the hostname.
