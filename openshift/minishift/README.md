# Documentation

https://docs.okd.io/latest/minishift/index.html
https://docs.okd.io/latest/minishift/getting-started/quickstart.html

# Install minishift

 brew cask install minishift

# Start minishift

minishift start --vm-driver=virtualbox

# Usage:

minishift oc-env
oc login https://192.168.99.103:8443 -u developer
minishift console --url

https://192.168.99.103:8443/console/

## Sample Deployment
oc new-app https://github.com/openshift/nodejs-ex -l name=myapp
oc logs -f bc/nodejs-ex
oc expose svc/nodejs-ex
minishift openshift service nodejs-ex --in-browser

minishift stop
