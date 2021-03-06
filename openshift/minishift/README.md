# Documentation

https://docs.okd.io/latest/minishift/index.html
https://docs.okd.io/latest/minishift/getting-started/quickstart.html

# Install minishift

```bash
 brew cask install minishift
```

# Start minishift

```bash
minishift start --vm-driver=virtualbox --cpus 6 --memory 8192
```

# Usage:

```bash
minishift oc-env
oc login https://192.168.99.103:8443 -u developer
minishift console --url
```

https://192.168.99.103:8443/console/

## Sample Deployment

```bash
oc new-app https://github.com/openshift/nodejs-ex -l name=myapp
oc logs -f bc/nodejs-ex
oc expose svc/nodejs-ex
minishift openshift service nodejs-ex --in-browser
```

```bash
minishift stop
```

/var/lib/minishift/bin/oc cluster up --base-dir /var/lib/minishift/base --public-hostname 192.168.99.100 --routing-suffix 192.168.99.100.nip.io
