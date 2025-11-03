FROM nvidia/cuda:12.2.2-base-ubuntu22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y software-properties-common git curl && \
    add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y python3.12 python3.12-venv && \
    update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.12 1

RUN python3.12 -m ensurepip
RUN git clone https://github.com/mannaandpoem/openmanus /openmanus
WORKDIR /openmanus
RUN python3.12 -m pip install --ignore-installed -e .
RUN curl -fsSL https://ollama.com/install.sh | sh
