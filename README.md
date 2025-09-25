# vtw-saas

## install Docker 
참고사이트 : https://docs.docker.com/engine/install/ubuntu/

1. Set up Docker's Apt repository.
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

i# Add the repository to Apt sources:
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

2. Install the Docker packages. 
```
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

3. Docker에 sudo 권한 부여 
```
$ sudo usermod -aG docker $USER
$ docker ps

if error blow:
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json": dial unix /var/run/docker.sock: connect: permission denied

$ sudo chmod 666 /var/run/docker.sock
```


## minikube 설치 
참고사이트 :https://minikube.sigs.k8s.io/docs/start/

1. Installation 
```
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ sudo install minikube-linux-amd64 /usr/local/bin/minikube

```

2. Start your cluster
```
$ minikube start
```

3. Interact with your cluster
```
$ kubectl get pod -A
```

4. minikube addons 설치  
```
# minikube addons enalbe [addons name]
$ minikube addons enalbe metrics-server
$ minikube addons enalbe ingress 
```

## kubectl 설치 및 자동완성 
참고 사이트 :
- https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-using-native-package-management
- https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#enable-shell-autocompletion

1. Install using native package management
```
$ snap install kubectl --classic
$ kubectl version --client
```

2. Enable shell autocompletion 
```
$ echo 'source <(kubectl completion bash)' >>~/.bashrc
$ echo 'alias k=kubectl' >>~/.bashrc
$ echo 'complete -o default -F __start_kubectl k' >>~/.bashrc
$ source ~/.bashrc
```

