# Install argocd

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

username : admin

To get the password

```
$ kubectl get secret argocd-initial-admin-secret -n argocd -o yaml          
apiVersion: v1
data:
  password: eFJBU0JSV1dpVkdxQk93LQ==
kind: Secret
metadata:
  creationTimestamp: "2024-10-01T11:06:46Z"
  name: argocd-initial-admin-secret
  namespace: argocd
  resourceVersion: "705"
  uid: 9253dbd1-0397-4513-815e-7c979dda0d12
type: Opaque
$ echo eFJBU0JSV1dpVkdxQk93LQ== | base64 --decode                           
xRASBRWWiVGqBOw-
```

Then connect github from the ui from the ui

[http:](https://localhost:8000/)
