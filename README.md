1) To test the app before deploy : kustomize build wisp-cluster/overlays/minikube/apps/ingress-nginx/envs/dev --enable-helm | kubectl apply -f -


2) To build and re-deploy all the apps
kubectl apply -k wisp-cluster/overlays/minikube/apps/argocd/envs/dev

3) get passwords for argocd

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d 

