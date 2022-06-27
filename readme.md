# jenkins master worker cluster on k3d


* Run jenkins as master worker in k8s near to production
* Use jenkins as code in helm charts
* Run jenkins pipeline in multicontainers
* build docker container in jenkins pipeline without docker demon
* Monitor Jenkins & jenkins job in graphana


## Jenkins as code



## pre-rquesties
* k3d
* helm

## commands

```bash
k3d cluster create jenkins-test \
  --api-port 127.0.0.1:6443 \
  -p 80:80@loadbalancer \
  -p 443:443@loadbalancer \
  --k3s-arg "--disable=traefik@server:0" \
	-a 1
```


add Traefik

* Traefik should be installed in kube-system namespace(for k3d)
```bash
helm install traefik traefik/traefik -n kube-system -f traefik.yaml
```