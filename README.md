# Nimiq Knowledgebase
<br>
<br>

**Nimiq useful docs and tutorials**

* [Running a Nimiq Node on a Digital Ocean droplet](https://gist.github.com/rlafranchi/6a1772c07c1eccafe2f21f784632504d)
* [How to send NIM with the Node.js API](https://nimiq.community/blog/sending-nim-with-the-api/)
* [JSON RPC API](https://github.com/nimiq-network/core/wiki/JSON-RPC-API)
* [JSON-RPC Client](https://github.com/nimiq-network/core/blob/master/doc/json-rpc-client.md)
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
<br>
<br>

**Nimiq wallets public addresses**

The actual address is 36 characters length and has no spaces, like this: `NQ488CKHBA242VR3N249N8MNJ5XX74DB5XJ8`

For better readability, the address can be presented with spaces, like this: `NQ48 8CKH BA24 2VR3 N249 N8MN J5XX 74DB 5XJ8`

Sometimes addresses are presented with "+" or "20%" characters instead of spaces - that's how browsers encode spaces. This can be observed in page URLs, e.g.:
`https://nimiq.mopsus.com/addr/NQ40%20M9RK%20T73M%20CJ68%203LEK%20R319%20KGN1%200FQU%2043L9`
`https://nimiq.watch/#NQ40+M9RK+T73M+CJ68+3LEK+R319+KGN1+0FQU+43L9`

The best practice is to always use the actual address (without spaces) everywhere, but add spaces only on the front end for user-friendly representation.
