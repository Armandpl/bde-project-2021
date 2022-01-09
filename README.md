# BDE Project 2021
DU PARC LOCMARIA Armand  
KOVACEVIC Veljko  
BDA GR02

## How to run
Start by creating a namespace and calling it 'ebc' (ethereum blockchain)  
`kubectl create namespace ebc`  
Then create the bootnode service to make it accessible to other pods.  
`kubectl create -f bootnode-service.yml`  
Run the bootnodes:  
`kubectl create -f bootnode.yml`  
Now that the bootnodes are accessible we have to create a bootnode registar to keep track of them.
```
kubectl create -f registrar-service.yml  
kubectl create -f registrar.yml
```
You can now run your miners with:  
`kubectl create -f miner.yml`  
If you want to interact with the blockchain you will need an RPC, so let's intialize it:  
```
kubectl create -f tx.yml  
kubectl create -f tx-service.yml
```

## Notes
This repo includes the file secret.yml which wouldn't be included in a production setup.  
Some config files are also redundant (for example miner and pool have common parts) and it should be possible to avoid that.

## Ressources
- [kubernetes 101](https://medium.com/google-cloud/kubernetes-101-pods-nodes-containers-and-clusters-c1509e409e16)
- [mining pool setup](https://medium.com/dragonfly-research/how-to-build-an-ethereum-mining-pool-6be356520b7a)
- [eth blochain on kubernetes](https://imti.co/ethereum-kubernetes/)
