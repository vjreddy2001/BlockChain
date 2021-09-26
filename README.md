# Building Blockchain
##  Creating Nodes
## Proof of Authority Development Chain

As a new developer at a small bank, my mission, will be to set up a testnet blockchain for my organization.

To do this, I will create four deliverables:

* Set up my custom testnet blockchain.

* Send a test transaction.

* Create a repository.

* Write instructions on how to use the chain for the rest of my team.

### Background

I have just landed a new job at ZBank, a small, innovative bank that is interested in exploring what
blockchain technology can do for them and their customers.

My first project at the company is to set up a private testnet that I and my team of developers
can use to explore potentials for blockchain at ZBank.

I have decided on setting up a testnet because:

There is no real money involved, which will give my team of developers the freedom to experiment.

Testnets allows for offline development.

In order to set up a testnet, I will use the following skills/tools I learned in class:

* Puppeth, to generate my genesis block.

* Geth, a command-line tool, to create keys, initialize nodes, and connect the nodes together.

* The Clique Proof of Authority algorithm.

Tokens inherently have no value here, so I will provide pre-configured accounts and nodes for easy setup.

After creating the custom development chain, I created documentation for others on how to start it using the pre-configured
nodes and accounts. I named the network as 'fintechnet'


### Instructions

#### Setting up the custom out-of-the-box blockchain

* Created a new project directory for my new network. Call it 'fintechnet' 

* Created a "Screenshots" folder inside of the project directory.

* Created accounts for two (or more) nodes for the network with a separate `datadir` for each using `geth` called it 'node1' and 'node2'.

![Screenshot 4](https://user-images.githubusercontent.com/83671629/134816902-710bd597-b914-4e66-a5c1-f860952f7f48.png)


![Screenshot 5](https://user-images.githubusercontent.com/83671629/134816922-a69273cb-4c88-49e9-aec4-6a28902a0a16.png)


* Ran `puppeth`, named my network as *zbank2*, and selectd the option to configure a new genesis block.
* Choose the `Clique (Proof of Authority)`(option 2) consensus algorithm.

![Screenshot - puppeth](https://user-images.githubusercontent.com/83671629/134817001-25b97333-7401-4592-9d10-f6d8c231a488.png)


* Pasted both account addresses from the first step, one at a time into the list of accounts to seal.
* Pasted them again in the list of accounts to pre-fund. There are no block rewards in PoA, so you'll need to pre-fund.

![Screenshot account seal](https://user-images.githubusercontent.com/83671629/134817307-9763863d-c3dd-4140-b4fd-87beb462fb0c.png)


* Completed the rest of the prompts, and when back at the main menu, choose the "Manage existing genesis" option.

* Export genesis configurations. This will fail to create two of the files, but we only need `fintechnet.json`.

* I deleted the `zbank2-harmony.json` file.

* Screenshot the `puppeth` configuration once complete and saved it to the Screenshots folder.

* Initialized each node with the new `zbank2.json` with `geth`.

![Screenshot initialize with geth](https://user-images.githubusercontent.com/83671629/134817391-534234bd-ea5c-4592-bdb1-bd203b72ce8c.png)

* Ran the first node, unlockd the account, enabled mining, and the RPC flag. Only one node needs RPC enabled.


* Set a different peer port for the second node and used the first node's `enode` address ( as the `bootnode` flag.)

![Screenshot 4](https://user-images.githubusercontent.com/83671629/134817420-38a4054f-1881-4020-a3a5-c961993bc992.png


* unlockd the account and enabled mining on the second node!

![Screenshot 5](https://user-images.githubusercontent.com/83671629/134817455-15f7397b-f2c4-4f98-94e1-1e87196bd5b5.png)


* both nodes will be producing new blocks!

#### Send a test transaction

* Used the MyCrypto GUI wallet to connect to the node with the exposed RPC port.

* I used a custom network (zbank2), and included the chain ID (555), and used ETH as the currency.

* Import the keystore file from the `node1/keystore` directory into MyCrypto. This will import the private key.

![Screenshot 1](https://user-images.githubusercontent.com/83671629/134817630-bc8842ca-c731-496f-89c0-b96c28af4505.png)

* Send a transaction from the `node1` account to the `node2` account.

![Screenshot 2](https://user-images.githubusercontent.com/83671629/134817648-bf9641b6-bebc-44c0-8462-0840c6459697.png)

* Copy the transaction hash and paste it into the "TX Status" section of the app, or click "TX Status" in the popup.
![Screenshot 3](https://user-images.githubusercontent.com/83671629/134817673-b9c4d1e2-32c3-4858-83ff-155eedb883c5.png

* Screenshot the transaction metadata (status, tx hash, block number, etc) and save it to your Screenshots folder.


![Screenshot 8](https://user-images.githubusercontent.com/83671629/134817703-290f7333-2feb-49fd-859f-9cbcb9f5d28d.png)

* Celebrate, you just created a blockchain and sent a transaction!

![Screenshot 9](https://user-images.githubusercontent.com/83671629/134817803-a9ee8572-a517-4f37-afd2-0c8372b86a4a.png)


#### Create a repository, and instructions for launching the chain

* Create a `README.md` in your project directory and create documentation that explains how to start the network.

* Remember to include any environment setup instructions and dependencies.

* Be sure to include all of the `geth` flags required to get both nodes to mine and explain what they mean.

* Explain the configuration of the network, such as it's blocktime, chain ID, account passwords, ports, etc.

* Explain how to connect MyCrypto to your network and demonstrate (via screenshots and steps) and send a transaction.

* Upload the code, including the `networkname.json` and node folders.

#### Remember, *never* share your mainnet private keys! This is a testnet, so coins have no value here!

#### Hints

* If you get stuck - try our step by step PoA Guide located [here](Resources/POA-Blockchain-guide.md).

* If you aren't seeing any movement in the wallet amounts in MyCrypto after sending/receiving transactions, try the following:

    * Terminate both nodes using control+C in the Node1 and Node2 terminal windows.
    * Change networks in MyCrypto to a Testnet such as Kovan.
    * Restart Node1 and Node2 in their terminal windows.
    * Reconnect to your network in MyCrypto.
    * Log into your wallet and refresh the amount.

* If that doesn't help make sure you are sending a large enough sum of ETH to see actual movement in the digits. You may have to click on the amount itself to see the full value down to the WEI.


---
