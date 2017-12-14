# Ethereum Solidity Development


- [Awesome blockchain demo](https://anders.com/blockchain/)

<a href="https://www.youtube.com/watch?v=_160oMzblY8&feature=" target="_blank"><img src="img/blockchain.png" 
alt="IMAGE ALT TEXT HERE" width="50%" border="10" /></a>

- [Ethereum Yellow Paper](http://gavwood.com/Paper.pdf)
- [Merkle Patricia Trie Specification (also Merkle Patricia Tree)](https://github.com/ethereum/wiki/wiki/Patricia-Tree)
- [Understanding the ethereum trie](https://easythereentropy.wordpress.com/2014/06/04/understanding-the-ethereum-trie/)


## Install packages (Linux)

- [NodeJs](https://nodejs.org/en/download/package-manager/)
    ```
    sudo dnf install nodejs
    ```
- Ethereum. [Geth](https://github.com/ethereum/go-ethereum)
    + Install Ethereum in fedora (https://copr.fedorainfracloud.org/coprs/jonny/ethereum/)
    ```
    sudo dnf copr enable jonny/ethereum
    sudo dnf install go-ethereum
    /usr/bin/geth
    ```
- testrpc
    + testrpc can emulate Ethereum node for development purposes
    + testrpc is a easy way to test the application (this is just an emulator)
    + testrpc is not a full implementation of the Ethereum node that deployed in the public network
    + Need to test with a full Ethereum node before deploy in to main Ethereum network 
    ```
    npm install -g ethereumjs-testrpc
    ```
- Turffle
    + Install
    ```
    sudo npm install -g truffle
    ```


## Install private Ethereum instance with geth 

- ### create the folder that will host the database and the accounts 
    ```
    mkdir -p ethchain/private
    ```

- ### Choose a network identifier for our private network. 
    + Pricate network identifier must be completely different from the public network identifiers
    + Main chain of Ethereum has the network identifier = 1 and two other networks reserved id 2 and 3
    + Lets use the network identifire **4243**
- ### Create the _Genesis_ block
    + _Genesis_ block is the first block that initialize the block chain (this is like the first node in a link list)
    + _Genesis_ block does not have a parent (previous block)
    + Create the file _genesis.json_ file that contain all the initial value of the _Genesis_ block
    ```
    touch ethchain/private/genesis.json 
    ```
    + add the following to genesis.json file 


    ```json
    {
        "nonce": "0x0000000000000042",
        "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
        "difficulty": "0x300",
        "alloc": {},
        "coinbase": "0x0000000000000000000000000000000000000000",
        "timestamp": "0x0",
        "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
        "extraData": "0x",
        "gasLimit": "0xffffffff",
        "config": {
            "chainId": 4224,
            "homesteadBlock": 0,
            "eip155Block": 0,
            "eip158Block": 0
        }
    }
    ```


    + Explain 
        + **"nonce"** + **"mixhash"** allow proof of work (POW) consensus mechanism to ensure that enough computations has been use to validate the block. 
        + **"difficulty"** average number of times miner will have to run the hashing function to solve a consensus puzzle (difficult level would be used to valicate the block). Bigger this value is longer it takes. In development times you should keep this number low to reduce the computational time. This keep the time between blocks very low.
        + **"alloc"** preallocate some finds to some wallets
        + **"coinbase"** the address of the miner who successfully mine the block
        + **"timestamp"** Manage by the Ethereum vertual machine that adjust the level of difficulty that should applied. If the **"timestamp"** between two blocks is too small then the **"difficulty"** will be increased (and reduced if the other way around). This allow to keep consistant time between blocks. **"timestamp"** is also ensure to keep the order amoung block. 
        + **"parentHash"** this is the hash of the parent (the previous block or the node). In the Genesis block, there is no previous block; hence, its zero.
        + **"extraData"** We can use this to lable out block-chain
        + **""gasLimit""** this define the maxumum amount of gas that allow to spend in this block (this allow to limit the size of the block). This is the gas that smart contract spend when it execute. 
        + **"config"** Config for the network (Network id (chainId), and some other parameters for the minings software read and understand how to mine this block)
        





