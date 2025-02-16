https://github.com/WhatsApp/proxy   
`docker-compose.yml`
```bash
services:
  proxy:
    image: sheepgreen/waproxy
    container_name: waproxy
    restart: always
    ports:
      - "443:443"       #chat with tls
      - "5222:5222"     #chat without tls
      - "587:587"       #media
    environment:
      - PUBLIC_IP=YOUR_SERVER_IP
```
