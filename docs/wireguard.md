## Setup wireguard

=== "Command"

    ```bash
    apt update
    apt upgrade -y
    apt install -y wireguard
    ```

## Setup Docker

=== "Command"

    ```bash
    apt-get remove docker docker-engine docker.io containerd runc
    apt-get install -y \
      apt-transport-https \
      ca-certificates \
      curl \
      gnupg \
      lsb-release
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    echo   "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
      $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    apt-get update
    apt-get install -y docker-ce docker-ce-cli containerd.io
    ```

## Setup Docker compose

=== "Command"

    ```bash
    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
    chmod +x /usr/bin/docker-compose
    ```
    
## Firewall config

### Clear docker stuff
=== "Command"

    ```bash
    iptables --flush
    iptables -X
    ```
    
### Wireguard rules
Forward rules
=== "Command"

    ```bash
    iptables -I FORWARD 1 -i eth0 -o wg0 -j ACCEPT
    iptables -I FORWARD 1 -i wg0 -o eth0 -j ACCEPT
    ```    
    
Masquerade rules
=== "Command"

    ```bash
    iptables -t nat -I POSTROUTING -o eth0 -j MASQUERADE
    ```    
    
Persistint rules:    
=== "Command"

    ```bash
    apt install -y iptables-persistent
    ```
    
## Setup Wirefuard UI    
Create project directory:
=== "Command"

    ```bash
    mkdir /opt/wg-gen-web
    cd /opt/wg-gen-web
    ```
    
Docker compose file:    
=== "/opt/wg-gen/web/docker-compose.yml"

    ```yaml
    version: '3.6'
    services:
      wg-gen-web:
        image: vx3r/wg-gen-web:latest
        container_name: wg-gen-web
        restart: unless-stopped
        ports:
          - "8080:8080"
        environment:
          - WG_CONF_DIR=/data
          - WG_INTERFACE_NAME=wg0.conf
          - SMTP_HOST=smtp.gmail.com
          - SMTP_PORT=587
          - SMTP_USERNAME=no-reply@gmail.com
          - SMTP_PASSWORD=******************
          - SMTP_FROM=Wg Gen Web <no-reply@gmail.com>
          - OAUTH2_PROVIDER_NAME=fake
          #- OAUTH2_PROVIDER=https://github.com
          #- OAUTH2_CLIENT_ID=******************
          #- OAUTH2_CLIENT_SECRET=******************
          #- OAUTH2_REDIRECT_URL=https://wg-gen-web-demo.127-0-0-1.fr
          - WG_STATS_API=http://172.17.0.1:8182
        volumes:
          - /etc/wireguard:/data
      wg-json-api:
        image: james/wg-api:latest
        container_name: wg-json-api
        restart: unless-stopped
        cap_add:
          - NET_ADMIN
        network_mode: "host"
        command: wg-api --device wg0 --listen 172.17.0.1:8182
    ```

Start docker-compose project:
=== "Command"

    ```bash
    docker-compose up -d
    ```
    
## Dnsmasq

```
domain-needed
bogus-priv

# Hosts file
domain=domain.local
expand-hosts

# Local domains
local=/domain.local/

listen-address=127.0.0.1,10.9.0.254
bind-interfaces

# Forward servers
server=10.134.0.2

#address=/paas.domain.local/10.66.0.30
```
