# AgroCD start

1. Start minikube : 
```console
minikube start
```

2. Check if minikube works properly :
```console
minikube status
```

3. Install Argo CD :
```console
kubectl create namespace argocd && kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

4. Check status node:
```console
kubectl get all -A
```


4. Run agrocd :
```console
kubectl port-forward svc/argocd-server -n argocd 8080:443&
```

5. Get password :
```console
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}"|base64 -d;echo
```

You will be able to open https://localhost:8080
Note, You must use https to open agrocd!
Use login **admin** and password you get in step 4.

# Demo
![Image](../data/651380.gif)



