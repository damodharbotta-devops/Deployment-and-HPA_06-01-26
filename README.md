# Deployment-and-HPA

## Commands

# Deployment:
kubectl create -f deploymenty.yml
kubectl get deploy
kunectl get po
kubectl get po -o wide
kubectl delete pod --all
kubectl set image deploy flm cont1=shaikmustafa/paytm:bank   ----> Manually update the image
kubectl rollout status deploy flm   -----> check the image rollout status


## Service :

kubectl create -f service.yml
kubectl get svc
kubectl get svc -o wide

## Rollback:

kubectl rollout undo deployment flm --to-revision=2     ----> rollout to 2 version
kubectl rollout history deploy flm    --------> rollout history


### Scaling:


1.Manual scaling:

kubectl scale deploy flm --scale=6   ----> scaleup
kubectl scale deploy flm --scale=2   ----> scaledown



2. Auto scaling:

### HPA:

kubectl apply -f hpa.yml
kubectl get hpa
kubectl exec -it pod name -- bash
kubectl get po -w     -------> watch in live created pods 

### Install stress package on pod

apt install -y
apt install stress -y
stress -c 4 -t 300 -v
