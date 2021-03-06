
## consensus protocol: dpos - practical bft

boost the consensus gap from 162.5 seconds to 3-6 seconds

[source code changes](https://github.com/eosiosg/eos/compare/v1.4.4...eosiosg:feature/dpos-pbft)


# deploy test network using k8s

## sample configuration is in k8s/n-nodes.

following nodes are pre-configured:
- boot node named eosio
- 14 bp nodes, named as bpa, bpb, bpc ... bpn
- 14 full nodes, named as node-0, node-1, node-2 ... node-13

in pre-configured network topology:
- each bp connects to one different full node.
- eosio connects to node-0
- all node-x connect to node-0 node-4 node-8 node-12

the topology can be easily adjusted in k8s/n-nodes/configmap.yaml


## shuffle producer scripts is in k8s/scripts

1. use ```. ./env```to setup your env
2. use ```./start``` to deploy contracts and create accounts
3. use ```./cron-vote.sh``` to trigger producer shuffle
