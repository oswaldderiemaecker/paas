# Documentation

https://rancher.com/docs/os/v1.x/en/quick-start-guide/
https://rancher.com/docs/rancher/v2.x/en/quick-start-guide/deployment/quickstart-manual-setup/

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

# Adding an Helm chart 

Goto catalog -> Add

https://github.com/helm/charts

# Node Cleanup Script

```bash
#!/bin/sh
docker rm -f $(docker ps -qa)
docker volume rm $(docker volume ls -q)
cleanupdirs="/var/lib/etcd /etc/kubernetes /etc/cni /opt/cni /var/lib/cni /var/run/calico"
for dir in $cleanupdirs; do
  echo "Removing $dir"
  sudo rm -rf $dir
done
```

https://octoperf.com/blog/2018/06/04/rancher-2-getting-started/

# Rancher on AWS

## First install Kubernetes on AWS:

https://github.com/oswaldderiemaecker/kops/blob/master/docs/aws.md

## Then Install Rancher:

https://rancher.com/checking-rancher-2-0-kops-aws-clusters/

```bash
kubectl create ns rancher-server
```

```bash
kubectl create -f rancher-deploy.yml
```
