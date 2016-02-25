# Robomongo Dockerfile
# Native and cross-platform MongoDB manager
# https://robomongo.org/
FROM ubuntu

WORKDIR /root
RUN apt-get update && \
    apt-get install --no-install-recommends -qy \
                ca-certificates curl \
                libglib2.0-0 libxext6 libgl1-mesa-glx libxi6 libgconf-2-4 \
                libsm6 libfontconfig1 libxrender1 libxcb-render-util0 \
                libxcb-render0 libxcb-randr0 &&\
    apt-get clean && rm -rf /var/{lib,cache}/apt

RUN curl -L https://download.robomongo.org/0.9.0-rc4/linux/robomongo-0.9.0-rc4-linux-x86_64-8c830b6.tar.gz | tar -zx && \
        mv robomongo-0.9.0-rc4-linux-x86_64-8c830b6 /opt/robomongo

RUN echo '8e0faa71ed6f98faff3c77ad56cd0e5b' > /etc/machine-id

ENV QT_GRAPHICSSYSTEM native
ENV QT_X11_NO_MITSHM 1

CMD ["/opt/robomongo/bin/robomongo"]
