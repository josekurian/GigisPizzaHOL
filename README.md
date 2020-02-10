# GigisPizzaHOL
Hands on Lab - Gigis pizza microservices/serverless app

HOL 5967 `<link>`: <https://github.com/oraclespainpresales/GigisPizzaHOL/blob/master/hol5967_userguide.md>
- oci version 2.9.1
- kubectl version 1.17.0

## Interesting information for the demo:

OVA VM machine [link](https://objectstorage.eu-frankfurt-1.oraclecloud.com/p/smpE_ekRW19rd4H31B4fPspIqXxRm-iSuaQ9kOc8_K8/n/wedoinfra/b/DevCS_Clone_WedoDevops/o/HOL5967-OOW2019%20OVAHOL5967-OOW2019.ova "ova hol")

### Python upgrade to python 3
```json
sudo yum install python3
```
### OCICLI upgrade to last version (OVA upgrade)
```
bash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"
```

### OCI SETUP repair permissions error
```
oci setup repair-file-permissions –file /home/holouser/.oci/private.pem
```
## Create OCIR Secret.
```
kubectl create secret docker-registry ocirsecret --docker-server=<region>.ocir.io --docker-username='<tenant_storage_namespace>/<your_user>' --docker-password='<your_auth_token>' --docker-email='<your_email>'
```
Example
```
kubectl create secret docker-registry ocirsecret --docker-server=fra.ocir.io --docker-username='wedoinfra/wedo.devops' --docker-password='xxxxxxxxxxxxx' --docker-email='test.email@oracle.com'
```
## Install Kubectl with curl
Download last version of kubectl
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
Change permission of the binary file
```
chmod +x ./kubectl
```
Move binary to you PATH
```
sudo mv ./kubectl /usr/local/bin/kubectl
```

## Oracle Cloud Regions:
https://docs.cloud.oracle.com/iaas/Content/General/Concepts/regions.htm

## Oracle OCIR Regions:
https://docs.cloud.oracle.com/iaas/Content/Registry/Concepts/registryprerequisites.htm#Availab

# OKE in Rancher UI

https://medium.com/swlh/oke-clusters-from-rancher-2-0-409131ad1293
