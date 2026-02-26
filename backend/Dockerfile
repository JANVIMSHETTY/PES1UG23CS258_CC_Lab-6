FROM ubuntu:22.04

RUN apt-get update && apt-get install -y netcat

CMD while true; do \
name=$(hostname); \
if [ "$name" = "backend1" ]; then msg="backend1"; else msg="backend2"; fi; \
printf "HTTP/1.1 200 OK\r\nContent-Length: 30\r\nContent-Type: text/plain\r\n\r\nServed by backend: $msg\n" \
| nc -l -p 8080 -q 1; \
done
