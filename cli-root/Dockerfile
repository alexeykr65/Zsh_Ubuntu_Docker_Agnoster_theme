FROM ubuntu:18.04

ENV LANG en_US.UTF-8 

RUN apt-get update \
    && apt-get install  -y \
                        locales \
                        zsh \
                        curl \
                        git \
                        vim \
                        nano \
                        ca-certificates \
                        wget \
                        sudo \
                        python3 \
                        libasound2 

RUN cd && chsh -s /bin/zsh && \
    useradd -m -s /usr/bin/zsh user && \
    sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8 && \
    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh && \
    sed -i -e 's/robbyrussell/agnoster/' .zshrc && \
    git clone https://github.com/powerline/fonts.git --depth=1 && \
    cd   fonts && \
    ./install.sh
