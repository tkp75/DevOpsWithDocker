FROM python:slim
RUN apt-get update && \
    apt-get -y -o APT::Install-Suggests=0 -o APT::Install-Recommends=0 install wget ffmpeg rtmpdump && \
    pip install youtube-dl yle-dl && \
    rm -f -r /var/cache/* /var/log/* /root/.cache /root/.wget-hsts
WORKDIR /yle-dl
ENTRYPOINT ["/usr/local/bin/yle-dl"]
