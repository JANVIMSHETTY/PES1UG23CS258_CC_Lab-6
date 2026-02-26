FROM ubuntu:22.04

RUN apt-get update && apt-get install -y netcat

WORKDIR /app
COPY app.cpp .

CMD while true; do echo -e "HTTP/1.1 200 OK\r\n\r\nServed by backend: $(hostname)" | nc -l -p 8080; done
