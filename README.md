# Create DMR Cluster

Python script and configs to setup DMR cluster with TLS and compression with multiple remote link support for HA and DR setup.

## Running

- Copy the sample-config.json to <your-config>.json
- change the values for your env.
- run with
 ```python3 create-dmr-cluster.py --cfgfile <your-config>.json```

### Sample Run

```
▶ python3 create-dmr-cluster.py --cfgfile private/nram-dev3-dmr.json
=== Processing local cluster cluster-aws-us-west-1a-4magebk8meb

*** Working on local dmrCluster (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters
    Status: 200
=== Processing 2 local links
--- Processing local link 1/2

*** Working on local externalLink (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links
    Status: 200

*** Working on local remoteAddress (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links/single-aws-us-east-1b-d3wyarxmbne/remoteAddresses
    Status: 200

*** Working on local vpnDmrBridge (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/msgVpns/nram-dev3-west/dmrBridges
    Status: 200

*** Working on local trustedCommonName (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links/single-aws-us-east-1b-d3wyarxmbne/tlsTrustedCommonNames
    Status: 200
--- Processing local link 2/2

*** Working on local externalLink (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links
    Status: 200

*** Working on local remoteAddress (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links/developerproductionu8utk2kcmfesolaceprimary0/remoteAddresses
    Status: 200

*** Working on local vpnDmrBridge (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/msgVpns/nram-dev3-west/dmrBridges
    Status: 200

*** Working on local trustedCommonName (post)
    post url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links/developerproductionu8utk2kcmfesolaceprimary0/tlsTrustedCommonNames
    Status: 200
=== Processing 2 remote links
--- Processing remote link 1/2

*** Working on remote dmrCluster (post)
    post url: https://mrd3wyarxmbne.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters
    Status: 200

*** Working on remote externalLink (post)
    post url: https://mrd3wyarxmbne.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-east-1b-d3wyarxmbne/links
    Status: 200

*** Working on remote vpnDmrBridge (post)
    post url: https://mrd3wyarxmbne.messaging.solace.cloud:943/SEMP/v2/config/msgVpns/nram-dev3-east/dmrBridges
    Status: 200
--- Processing remote link 2/2

*** Working on remote dmrCluster (post)
    post url: https://mr-u8utk2kcmfe.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters
    Status: 200

*** Working on remote externalLink (post)
    post url: https://mr-u8utk2kcmfe.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-gke-gcp-us-east4-a-u8utk2kcmfe/links
    Status: 200

*** Working on remote vpnDmrBridge (post)
    post url: https://mr-u8utk2kcmfe.messaging.solace.cloud:943/SEMP/v2/config/msgVpns/nram-dev3-east/dmrBridges
    Status: 200

*** Working on local enableLink (patch)
    patch url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links/single-aws-us-east-1b-d3wyarxmbne
    Status: 200

*** Working on local enableLink (patch)
    patch url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb/links/developerproductionu8utk2kcmfesolaceprimary0
    Status: 200

*** Working on remote enableLink (patch)
    patch url: https://mrd3wyarxmbne.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-east-1b-d3wyarxmbne/links/single-aws-us-west-1a-4magebk8meb
    Status: 200

*** Working on remote enableLink (patch)
    patch url: https://mr-u8utk2kcmfe.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-gke-gcp-us-east4-a-u8utk2kcmfe/links/single-aws-us-west-1a-4magebk8meb
    Status: 200

*** Working on local enableCluster (patch)
    patch url: https://mr4magebk8meb.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-west-1a-4magebk8meb
    Status: 200

*** Working on remote enableCluster (patch)
    patch url: https://mrd3wyarxmbne.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-aws-us-east-1b-d3wyarxmbne
    Status: 200

*** Working on remote enableCluster (patch)
    patch url: https://mr-u8utk2kcmfe.messaging.solace.cloud:943/SEMP/v2/config/dmrClusters/cluster-gke-gcp-us-east4-a-u8utk2kcmfe
    Status: 200
```

### Clusters

[dmr-cluster](images/dmr-clusters.png)

## Reference

- [Postman collection](https://www.getpostman.com/collections/e983b5599a9ef40194f7)

## Author

[Ramesh Natarajan](ramesh.natarajan@solace.com) (nram), Solace PSG
