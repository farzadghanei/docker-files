********************
Robomongo Dockerfile
********************

Build Docker image for `robomongo <https://robomongo.org>`_.

Then run the app wih something like this:

.. code-block:: bash

    docker build -t local/robomongo
    docker run --rm -it -v /tmp/.X11-unix/:/tmp/.X11-unix -e DISPLAY=$DISPLAY local/robomongo


