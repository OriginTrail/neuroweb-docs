# Bridges

The NEURO token, although being the native token of Neuroweb blockchain, is designed for cross chain utility in knowledge mining. To enable movement of NEURO tokens between different blockchains, different bridges can be used.

### Bridging to Base blockchain

To move NEURO between Base and Neuroweb blockchains you can use [the bridge interface](https://neuroweb.ai/bridges).

The underlying infrastructure for bridging relies on [Wormhole](https://wormhole.com/) and [Moonbeam](https://moonbeam.network/) technology, which at the moment requires a two step bridging process, which is explained in detail in the following video:

{% embed url="https://youtu.be/9Zpr1vbP7Fw" %}

{% hint style="info" %}
The v2 Bridge interface will focus on improving the user experience of the bridging process, lowering the number of steps and making the process faster.
{% endhint %}

### Bridging to Polkadot blockchains

NEURO can be bridged to Polkadot parachains through the Polkadot native transfer technology [XCM](https://wiki.polkadot.network/docs/learn-xcm).&#x20;

### Bridging to Moonbeam

The easiest way to bridge Neuro to Moonbeam is using the Moonbeam dapp.

1. Visit [Moonbeam Dapp - Parachain bridges page](https://apps.moonbeam.network/moonbeam/xcm).
2. Click on the connect the wallet in the top right corner:
   1. Choose Moonbeam for network.
   2. Connect your EVM wallet that will receive NEURO tokens on Moonbeam. This can be done using Metamask or any other wallet provided as option in the interface.
   3. Connect your Substrate wallet that will send NEURO tokens from NeuroWeb. This can be done using Polkadot.js extension wallet or any other wallet that is provided as option in the interface.
3. Choose NEURO as token.
4. Choose OriginTrail Parachain as 'to' and Moonbeam as 'from', and click connect wallet for both chains.
5. Select amount of tokens to bridge.&#x20;
6. Observe the estimation of how many NEURO tokens you will receive after the fees are paid.
7. Click send.
