# Bridges

The NEURO token, although being the native token of the NeuroWeb blockchain, is designed for cross-chain utility in knowledge mining. To enable the movement of NEURO tokens between different blockchains, different bridges can be used.

### Bridging to Base blockchain

To move NEURO between Base and Neuroweb blockchains, you can use [the bridge interface](https://neuroweb.ai/bridges).

The underlying infrastructure for bridging relies on [Wormhole](https://wormhole.com/) and [Moonbeam](https://moonbeam.network/) technology, which at the moment requires a two-step bridging process, which is explained in detail in the following video:

{% embed url="https://youtu.be/9Zpr1vbP7Fw" %}

{% hint style="info" %}
The v2 Bridge interface will focus on improving the user experience of the bridging process, reducing the number of steps, and speeding up the process.
{% endhint %}

### Bridging to Polkadot blockchains

NEURO can be bridged to Polkadot parachains via the Polkadot-native [XCM](https://wiki.polkadot.network/docs/learn-xcm) transfer technology.&#x20;

### Bridging to Moonbeam

The easiest way to bridge Neuro to Moonbeam is by using the Moonbeam dapp.

1. Visit [Moonbeam Dapp - Parachain bridges page](https://apps.moonbeam.network/moonbeam/xcm).
2. Click on the "Connect wallet" in the top right corner:
   1. Choose Moonbeam for the network.
   2. Connect your EVM wallet that will receive NEURO tokens on Moonbeam. This can be done using Metamask or any other wallet provided as an option in the interface.
   3. Connect your Substrate wallet that will send NEURO tokens from NeuroWeb. This can be done using the Polkadot.js extension wallet or any other wallet that is provided as an option in the interface.
3. Choose NEURO as the token.
4. Choose OriginTrail Parachain as 'to' and Moonbeam as 'from', then click "Connect wallet" for both chains.
5. Select the amount of tokens to bridge.&#x20;
6. Observe the estimation of how many NEURO tokens you will receive after the fees are paid.
7. Click "Send".
