FROM ubuntu:22.04

RUN apt-get update && apt-get install -y netcat

CMD while true; do \
h=$(hostname); \
if echo "$h" | grep -q "backend1"; then name="backend1"; else name="backend2"; fi; \
printf "HTTP/1.1 200 OK\r\nContent-Length: 28\r\nContent-Type: text/plain\r\n\r\nServed by backend: $name\n" \
| nc -l -p 8080 -q 1; \
done
