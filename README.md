# Nimiq Knowledgebase
<br>
<br>

**Nimiq tutorials**

* [Running a Nimiq Node on a Digital Ocean droplet](https://gist.github.com/rlafranchi/6a1772c07c1eccafe2f21f784632504d)
* [How to send NIM with the Node.js API](https://nimiq.community/blog/sending-nim-with-the-api/)
* [JSON RPC API](https://github.com/nimiq-network/core/wiki/JSON-RPC-API)
<br>
<br>

**How to get private key from 24 recovery words (mnemonic phrase) and vice-versa**

- Get JS script https://github.com/nimiq/mnemonic-phrase
- Include it into an empty index.html
- Open the html localy and use commands provided in the repo
<br>
<br>

**How to get a seed from a keypair of private and public keys**

    privateKey = Buffer.from(MnemonicPhrase.mnemonicToKey( "word1 word2 word3 ..." ), "hex");
    key = new Nimiq.PrivateKey(privateKey);
    keyPair = Nimiq.KeyPair.derive(key);
    seed = keyPair.toHex();
<br>
<br>

**Specify network to which you want to connect**

    Nimiq.GenesisConfig.main(); // mainnet
    Nimiq.GenesisConfig.test(); // testnet
    Nimiq.GenesisConfig.bounty(); // for bounties
    Nimiq.GenesisConfig.dev(); // for development
