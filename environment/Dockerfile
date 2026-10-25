# hash:sha256:0268c8a6a78ee2acee97cd017b431a7134a43d3fd6e84e24c97e0c1ee7bb2bdc
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/kilosort4-base:4.1.7_cuda-12.0.0

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN pip3 install -U --no-cache-dir \
    aind-data-schema==2.8.1 \
    aind-log-utils==0.2.8 \
    scipy==1.17.1 \
    spikeinterface[full]==0.104.7

COPY postInstall /
RUN --mount=type=secret,id=secrets . /run/secrets/secrets \
    && /postInstall
