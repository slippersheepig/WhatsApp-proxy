https://github.com/WhatsApp/proxy   
`docker-compose.yml`
```bash
services:
  proxy:
    image: sheepgreen/waproxy
    container_name: waproxy
    restart: always
    ports:
      - "80:80"     # HTTP
      - "443:443"   # HTTPS
      - "5222:5222" # JABBER
      - "8199:8199" # HAPROXY statistics page
      - "8080:8080" # HTTP with accept-proxy processing
      - "8443:8443" # HTTPS with accept-proxy processing
      - "8222:8222" # JABBER with accept-proxy processing
      - "587:587"   # whatsapp.net
      - "7777:7777" # whatsapp.net
    healthcheck:
      test: /usr/local/bin/healthcheck.sh
      interval: 10s
      start_period: 5s
```
