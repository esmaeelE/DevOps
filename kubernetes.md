# Kubernetes

## k3s as a simple Kubernetes distribution 

### Install On ubuntu

### Official installation method
```
curl -sfL https://get.k3s.io | sh -
```

# Configs
```
echo "export KUBECONFIG=~/.kube/config" >> ~/.bashrc
mkdir ~/.kube 2> /dev/null
sudo k3s kubectl config view --raw > "$KUBECONFIG"
chmod 600 "$KUBECONFIG"
```

# login and logout

* [Evan Carroll answer on DevOps](https://devops.stackexchange.com/a/16109/42890)
* [baeldung](https://www.baeldung.com/ops/k3s-getting-started)

# Kubernetes cheatsheet

## Run
```
kubectl get nodes
kubectl get pods
kubectl get pods --all-namespaces
```


