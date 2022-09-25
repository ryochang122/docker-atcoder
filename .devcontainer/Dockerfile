# Ubuntuの公式コンテナを使用
FROM ubuntu:20.04

# インタラクティブモードは無効
ARG DEBIAN_FRONTEND=noninteractive
# タイムゾーンを日本に設定
ENV TZ=Asia/Tokyo

# インフラを整備
RUN apt-get update && \
    apt-get install -y zsh time tzdata tree git curl

# デフォルトシェルをZshに変更
RUN chsh -s /bin/zsh

# C++,node.js,npmの環境設定
RUN apt-get update && \
    apt-get install -y gcc-9 g++-9 python3.8 python3-pip nodejs npm

# コマンド設定
RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 30 && \
    update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 30 && \
    update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 30 && \
    update-alternatives --install /usr/bin/node node /usr/bin/nodejs 30

RUN pip install online-judge-tools==11.3.0
RUN npm install -g atcoder-cli@2.1.1

WORKDIR /root/problems
WORKDIR /root/library
