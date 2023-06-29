FROM ubuntu:latest

RUN apt-get update && apt-get -y install git curl unzip openjdk-8-jdk

RUN apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir /home/codespace
WORKDIR /home/codespace

ENV PUB_CACHE=/home/codespace/.pub_cache
ENV PATH="/home/codespace/flutter/bin:$PATH"
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

RUN git clone https://github.com/flutter/flutter && \
    /home/codespace/flutter/bin/flutter config --enable-web && \
    /home/codespace/flutter/bin/flutter doctor --android-licenses

RUN /home/codespace/flutter/bin/flutter doctor

CMD ["/bin/bash"]
