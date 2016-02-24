********************
Robomongo Dockerfile
********************

Build Docker image for `robomongo <https://robomongo.org>`_.

Build the image

.. code-block:: bash

    docker build -t local/robomongo


Then run the app with a command like this:

.. code-block:: bash

    docker run --rm -it -v /tmp/.X11-unix/:/tmp/.X11-unix -e DISPLAY=$DISPLAY local/robomongo


Or if you wanted to connect to MongoDB running on the host:

.. code-block:: bash

    docker run --rm -it -v /tmp/.X11-unix/:/tmp/.X11-unix -e DISPLAY=$DISPLAY --add-host=dockerhost:$(ip -4 addr show scope global dev docker0 | grep inet | awk '{print $2}' | cut -d / -f 1) local/robomongo


Now when creating a new connection, use *dockerhost* as the hostname.


