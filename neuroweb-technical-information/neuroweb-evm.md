# NeuroWeb EVM

NeuroWeb supports two types of blockchain accounts:

* **Substrate accounts** (Polkadot native, used with Polkadot wallets such as Polkadot.js), which are used for native NeuroWeb functionality
* **Ethereum accounts** (Ethereum native, used with Ethereum wallets such as MetaMask), which are used within the EVM

This enables NeuroWeb users to benefit from "both worlds". To enable the EVM functionality, users need to create a **mapping between their Substrate and Ethereum accounts** (wallets) to the NeuroWeb through a one-time transaction, which can be performed through [this interface](https://neuroweb.ai/evm) (before going to this interface, you need to fund your wallets with NEURO and TRACE test tokens; instructions are available here).&#x20;

The interface uses an Ethereum wallet to sign the provided Substrate address and submit it as a transaction to the NeuroWeb, so that the Parachain runtime can verify that the two addresses are owned by the same user. Once the mapping is completed, you can use the NeuroWeb EVM functionalities. The account mapping interface doesn't have access to your wallet's private keys and only uses your wallet's signing and transaction functionalities to submit a valid transaction.

#### Why the need for two accounts? <a href="#why-the-need-for-two-accounts" id="why-the-need-for-two-accounts"></a>

NeuroWeb uses the native Substrate address format (H256), which is different from the Ethereum address format (H160), therefore it needs to enable usage of both in order to perform both Substrate native functionalities and Ethereum compatible activity. The Substrate address (wallet) is used for all native NeuroWeb functionality, such as NEURO transactions, collator delegation, governance features, etc, while the Ethereum address (wallet) is used for operations within the EVM environment, which include OriginTrail DKG transactions, deploying & interacting with Ethereum smart contracts deployed on NeuroWeb, and similar. In the future, the OriginTrail DKG is expected to move beyond the EVM implementation to a Substrate-native one, introducing capabilities such as Graph Contracts.

#### Which wallets can be used with NeuroWeb? <a href="#which-wallets-can-be-used-with-origintrail-parachain-then" id="which-wallets-can-be-used-with-origintrail-parachain-then"></a>

For all interactions with the EVM (including OriginTrail DKG), you can use any Ethereum-compatible wallet, such as e.g., MetaMask, in conjunction with a hardware wallet. For Substrate functionality, you need to use Substrate-based wallets.

#### Do I need to perform this mapping for my OriginTrail nodes? <a href="#do-i-need-to-perform-this-mapping-for-my-origintrail-v6-nodes" id="do-i-need-to-perform-this-mapping-for-my-origintrail-v6-nodes"></a>

The mapping should be performed for both management and operational wallets; otherwise, the node will not start.
