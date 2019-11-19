# dns
 - export
    docker run -it --rm \
    -e CLOUDFLARE_EMAIL=cloudflare@email.net \
    -e CLOUDFLARE_TOKEN=xxxxx \
    -v /home/lxk/dns/config:/opt/dns/config \
    parkr/octodns:v0.9.4 \
    octodns-dump \
    --config-file /opt/dns/config/production.yaml \
    --output-dir /opt/dns/config \
    "domain.com." \
    cloudflare
 - sync
    docker run -it --rm \
    -e CLOUDFLARE_EMAIL=yourlogin@gmail.com \
    -e CLOUDFLARE_TOKEN=yourtoken \
    -v $(pwd):/opt/dns \
    parkr/octodns:v0.9.4 \
    octodns-sync --config-file /opt/dns/config/production.yaml
