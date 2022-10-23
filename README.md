# elastic

- Elastic [Docs](https://www.elastic.co/guide/index.html)
  - [github](https://github.com/elastic)
  - [support matrix](https://www.elastic.co/support/matrix)

## Install

- docker: [images](https://www.docker.elastic.co/)
- elastic cloud on [kubernetes](https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-quickstart.html)
  - github: [cloud-on-k8s](https://github.com/elastic/cloud-on-k8s)
- helm [charts](https://github.com/elastic/helm-charts): ~ 7.x 

### K8S

Start Ubuntu 22.04:

```bash
vagrant init generic/ubuntu2204
vagrant up
```

Install microk8s:

```bash
sudo snap install microk8s --channel=1.24/stable --classic
sudo usermod -a -G microk8s ubuntu
sudo chown -f -R ubuntu /home/ubuntu/.kube
echo "alias kubectl='microk8s kubectl'" >> /home/ubuntu/.bash_aliases # Alias
echo 'source <(kubectl completion bash)' >> /home/ubuntu/.bashrc # Command-line auto completion
microk8s enable dns storage ingress registry helm3 metallb
```
