# Documentation

https://rancher.com/docs/os/v1.x/en/quick-start-guide/

# Create the docker-machine

```bash
docker-machine create -d virtualbox \
        --virtualbox-boot2docker-url https://releases.rancher.com/os/latest/rancheros.iso \
        --virtualbox-memory 2048 \
        <MACHINE-NAME>
```

# Starting Rancher

```bash
sudo docker run -d --restart=unless-stopped -p 80:80 -p 443:443 rancher/rancher
```
