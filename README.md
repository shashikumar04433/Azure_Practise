# Aks deployment Steps:


## Run a pipeline github actions yml then connect to the aks using the below steps:
**Step1:**
```
* az login --service-principal --username <user-name> --password <Password> --tenant <tenant>
```
**Step2:**
```
* az aks get-credentials --resource-group <rg-name> --name <cluster-name>
It will save the credentials in your local
```
**Step3**
```
* az account set --subscription <sub_id>
```
**Step4**
```
az aks get-credentials --resource-group <rg-name>  --name <<cluster-name> --overwrite-existing
```
**Step5**
```
* kubelogin convert-kubeconfig -l azurecli
```
**Step6**
```
* kubectl get deployments --all-namespaces=true
* kubectl get service apache-service -n testns
* az acr repository list --name <acrname> --output table
* az network public-ip list --query "[].{Name:name,SKU:sku.name,IP:ipAddress}" -o table
* kubectl port-forward svc/apache-service 8080:80 -n <namespace>
```

