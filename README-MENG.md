https://kubernetes.io/docs/tasks/extend-kubernetes/configure-multiple-schedulers/

## 

git checkout gpemu-v1.28.3



## install golang

```
sudo rm -rf /usr/local/go
cd /tmp
wget https://go.dev/dl/go1.21.4.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.21.4.linux-amd64.tar.gz
cd -
```

## Package the scheduler

```
make

sudo docker build -t wangm12/my-kube-scheduler .
sudo docker push wangm12/my-kube-scheduler
kubectl create -f my-scheduler.yaml
kubectl get pods --namespace=kube-system


kubectl describe pod my-scheduler-6497bc64c5-pbjcc --namespace=kube-system
kubectl logs my-scheduler-6497bc64c5-fcljs --namespace=kube-system

kubectl get pods --all-namespaces
```







## References:

https://cast.ai/blog/custom-kube-scheduler-why-and-how-to-set-it-up-in-kubernetes/

https://kubernetes.io/docs/reference/scheduling/config/

https://github.com/kelseyhightower/kubernetes-the-hard-way/issues/427

