# Submit a governance proposal

A proposal is a submission to the chain in which a token holder suggests an action to be enacted by the system. Proposals are one of the core elements of the governance system because they are the main tool for community members to propose actions/changes, which other token holders then vote on.

### Submitting a preimage of the proposal&#x20;

The first step is to submit a preimage of the proposal. This is because the storage cost of large preimages can be pretty hefty, since they contain all the information about the proposal itself. With this configuration, one account with more funds can submit a preimage, and another account can submit the proposal.

First, navigate to [NeuroWeb's Polkadot.js Apps interface](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fparachain-rpc.origin-trail.network#/preimages). Everything related to governance lives under the **Governance** tab, including preimages:

* From the **Governance** dropdown, you can select **Preimages**.&#x20;
* Once there, click on the **Add preimage** button.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-01 at 17.24.04.png" alt=""><figcaption></figcaption></figure>

Here, you need to provide the following information:

1. **Select the account** from which you want to submit the preimage
2. **Choose the pallet** you want to interact with and the dispatchable function (or action) to propose. The action you choose will determine the fields that need to be filled in the following steps.
3. **Enter any additional fields** required for the extrinsic to be dispatched.&#x20;
4. **Copy the preimage hash.** This represents the proposal. You will use this hash when submitting the actual proposal.
5. Click the **Submit preimage** button and sign the transaction.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-01 at 17.23.52.png" alt=""><figcaption></figcaption></figure>

Note that the storage cost of the preimage can be calculated as the base fee (per network) plus the fee per byte for the proposed preimage.

After the transaction is submitted, you will see confirmations in the top right corner of the Polkadot.js Apps interface, and the preimage will be added to the list of **preimages**.

#### Submitting a proposal <a href="#submitting-a-proposal-v2" id="submitting-a-proposal-v2"></a>

Once you have committed the preimage (check the previous section), the roadmap's next major milestone is to submit the proposal related to it. To do so, select **Referenda** from the **Governance** dropdown, and click on **Submit proposal**.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-01 at 17.24.33.png" alt=""><figcaption></figcaption></figure>

Here, you need to provide the following information:

1. **Select the account** from which you want to submit the proposal
2. **Enter the preimage hash** related to the proposal.
3. Click **Submit proposal** and sign the transaction

<figure><img src="../.gitbook/assets/Screenshot 2024-04-01 at 17.24.27.png" alt=""><figcaption></figcaption></figure>

After the transaction is submitted, you will see confirmations in the top right corner of the Polkadot.js Apps interface. You should also see the proposal listed in the proposals section, displaying the proposed action, proposer, and more.

\
\
\
