---
description: OriginTrail Software Development Kit
---

# SDK

## SDK

The OriginTrail SDK is a set of software development tools that allows you to interact with the OriginTrail Decentralized Knowledge Graph (DKG). The DKG is a network of nodes that store and exchange data using semantic web standards and blockchain technology. With the OriginTrail DKG SDK, you can create, manage, and query knowledge assets on the DKG, as well as integrate with existing web3 applications.\


The OriginTrail SDK is available in two implementations: Javascript and Python. Each SDK library provides an easy-to-use interface to connect to a local or remote Origin Trail gateway node, which acts as a bridge between your application and the DKG network.

## Setting up SDK

To configure both the JavaScript and Python clients, you need to provide the private and public addresses of your wallet. These wallets play a crucial role in the Knowledge Mining process, as they are used to publish knowledge assets.&#x20;

It's important to remember that only Knowledge Assets that are published on the NeuroWeb mainnet are eligible for Knowledge Mining. Therefore, clients should be set up with this in mind.

To use the client, access to the DKG node is required. You can host the node yourself; more on node hosting can be found [here](https://docs.origintrail.io/build-with-dkg/quickstart-test-drive-the-dkg-in-5-mins). Or other node runners need to provide access.

### JavaScript Client — dkg.js

Full documentation on the JavaScript client can be found [here](https://docs.origintrail.io/build-with-dkg/quickstart-test-drive-the-dkg-in-5-mins/quickstart-with-node.js). Dkg.js is available on [github](https://github.com/OriginTrail/dkg.js) and [npm](https://www.npmjs.com/package/dkg.js).

### Python Client — dkg.py

Full documentation on Python client can be found [here](https://docs.origintrail.io/build-with-dkg/quickstart-test-drive-the-dkg-in-5-mins/quickstart-with-python). Dkg.py is available on [github](https://github.com/OriginTrail/dkg.py) and [pypi](https://pypi.org/project/dkg/).

{% hint style="info" %}
The OriginTrail SDK libraries are being built in various languages by the team and the community, expect more implementations in the future to become available!
{% endhint %}
