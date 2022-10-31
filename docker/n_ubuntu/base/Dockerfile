FROM ubuntu:20.04
COPY ./app /home/wldyd
WORKDIR /home/wldyd

RUN apt update && \
    apt install -y apt-transport-https curl gnupg && \
    curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor >bazel-archive-keyring.gpg && \
    mv bazel-archive-keyring.gpg /usr/share/keyrings && \
    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/bazel-archive-keyring.gpg] https://storage.googleapis.com/bazel-apt stable jdk1.8" | tee /etc/apt/sources.list.d/bazel.list && \
    apt update && apt install -y bazel && \
    apt install -y git  && \
    git clone https://github.com/protocolbuffers/protobuf.git && \
    cd protobuf && \
    git submodule update --init --recursive && \
    bazel build :protoc :protobuf && \
    cp bazel-bin/protoc /usr/local/bin



