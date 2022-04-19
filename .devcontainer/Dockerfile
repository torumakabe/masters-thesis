FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    xdvik-ja \
    evince \
    texlive-lang-cjk \
    texlive-latex-extra \
    texlive-extra-utils \
    latexmk \
    language-pack-ja \
    wget \
    curl \
    xzdec \
    git \
    cpanminus \
    make \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN tlmgr init-usertree
RUN kanji-config-updmap-sys ipaex
RUN cpanm Log::Log4perl Log::Dispatch::File YAML::Tiny File::HomeDir Unicode::GCString

WORKDIR /workdir

VOLUME ["/workdir"]

CMD ["bash"]
