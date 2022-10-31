FROM ubuntu:latest

COPY ./app /usr/wldyd
WORKDIR /usr/wldyd

RUN apt update && apt install -y python3
RUN cd /usr/wldyd
RUN touch hi
