# BDE Project 2021
DU PARC LOCMARIA Armand
KOVACEVIC Veljko
BDA GR02

## Quickstart/How to run
- create namespace

## Motivations

## Methodology

## Ressources
- [kubernetes 101](https://medium.com/google-cloud/kubernetes-101-pods-nodes-containers-and-clusters-c1509e409e16)
- [mining pool setup](https://medium.com/dragonfly-research/how-to-build-an-ethereum-mining-pool-6be356520b7a)
- [eth blochain on kubernetes](https://imti.co/ethereum-kubernetes/)

# notes
services vs deployment: deployment make sure set of pods keeps running, services provide network access

# how it works
- bootnode to aid discovery. stripped down node, only does discovery
    - has a service and a deployment
    - include a cli webserver that returns the enode address of the bootnode

- bootnode registrar
    - i think this is useful because we deploy the bootnodes on a cluster: we need smth to keep track of where the bootnodes are. that's what the registrar does

- miners 

-rpc, almost same config as miner, what changes is how we start geth

- secret configmap and initcontainers!