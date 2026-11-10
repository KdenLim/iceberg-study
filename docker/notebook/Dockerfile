FROM ubuntu:22.04

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        ca-certificates \
        openjdk-11-jre-headless \
        python3-pip \
    && rm -rf /var/lib/apt/lists/*

RUN python3 -m pip install --no-cache-dir \
        pyspark==3.3.1 \
        notebook==6.5.7 \
        ipykernel==6.29.5 \
    && useradd --create-home --uid 1000 --shell /bin/bash docker

ENV PYSPARK_PYTHON=/usr/bin/python3 \
    PYSPARK_DRIVER_PYTHON=/usr/bin/python3

USER docker
WORKDIR /home/docker

EXPOSE 8888

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--no-browser"]
