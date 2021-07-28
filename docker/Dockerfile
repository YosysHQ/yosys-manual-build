FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN set -e -x ;\
    apt -y update ;\
    apt -y upgrade ;\
    apt -y install \
        build-essential clang bison flex libreadline-dev \
        gawk tcl-dev graphviz python3 pkg-config git \
        texlive-binaries \
        texlive-science \
        texlive-bibtex-extra \
        texlive-fonts-extra \
        texlive-publishers \
        make \
        wget; \
    apt -y autoremove ;\
    rm -rf /var/lib/apt/lists/*

RUN cd /tmp && wget https://tug.org/fonts/getnonfreefonts/install-getnonfreefonts && \
    texlua install-getnonfreefonts && \
    getnonfreefonts luximono --sys

WORKDIR /work
