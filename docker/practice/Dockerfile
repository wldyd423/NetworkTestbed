FROM gcc:latest

COPY . /usr/src
WORKDIR /usr/src
RUN gcc test.c -o test
CMD ["./test"]