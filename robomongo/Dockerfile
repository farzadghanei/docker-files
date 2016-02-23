# Robomongo Dockerfile
# Native and cross-platform MongoDB manager
# https://robomongo.org/
FROM ubuntu

RUN apt-get update

RUN apt-get install -qy curl
RUN apt-get install -qy libglib2.0-0 libxext6 libgl1-mesa-glx libxi6 libgconf-2-4 libsm6 libfontconfig1 libxrender1
RUN apt-get install -qy libxcb-render-util0 libxcb-render0 libxcb-randr0
RUN apt-get install -qy dbus
RUN dbus-uuidgen > /var/lib/dbus/machine-id

WORKDIR /root
RUN curl http://download.robomongo.org/0.9.0-rc4/linux/robomongo-0.9.0-rc4-linux-x86_64-8c830b6.tar.gz | tar -zx
RUN mv robomongo-0.9.0-rc4-linux-x86_64-8c830b6 /opt/robomongo

ENV QT_GRAPHICSSYSTEM native
ENV QT_X11_NO_MITSHM 1

CMD ["/opt/robomongo/bin/robomongo"]
