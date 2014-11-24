FROM ubuntu:14.04

# isntall dependencies
RUN apt-get update -y && \
    apt-get install -y wget git openjdk-6-jre

# Install nvm
RUN wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.13.1/install.sh | bash -l && \
    echo 'source ~/.profile' | bash -l && \
    echo 'nvm install 0.11.13' | bash -l && \
    echo 'nvm alias default 0.11.13' | bash -l

# clone devkit2
RUN git clone https://github.com/gameclosure/devkit2.git && \
    cd devkit2 && \
    git checkout 62d867dc5d167c0d27134b14f0e59a323de64009

# Install devkit2
RUN echo 'cd devkit2 && \
    npm install -g \
    ' | bash -l

EXPOSE 9200
ENTRYPOINT /bin/bash