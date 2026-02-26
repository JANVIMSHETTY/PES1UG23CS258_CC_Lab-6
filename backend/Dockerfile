FROM ubuntu:22.04

RUN apt-get update && apt-get install -y netcat

CMD while true; do \
printf "HTTP/1.1 200 OK\r\nContent-Length: 30\r\nContent-Type: text/plain\r\n\r\nServed by backend: $(hostname)\n" \
| nc -l -p 8080 -q 1; \
done
