# Nimiq Knowledgebase
<br>

### What is Nimiq?

Nimiq is a browser-based blockchain which is why It is a payment protocol native to the web. By having payment protocol native to the web we aim to lower barriers of entry to **developers**, **merchants**, and **users**.

**Developers**: There is a massive workforce of web developers that want to build applications for cryptocurrencies but find it hard, complicated and dependent of 3-party applications. With Nimiq web developers can easily build applications without the need of a third party node. Users run their own node and so it becomes extremely easy to start developing on top of Nimiq. This will achieve a big ecosystem of applications and developers that can build/maintain/support these applications.

**Merchants**: Nimiq is designed to scale and is currently fee-less. We plan to continue adding features to Nimiq so is the de-facto blockchain for day to day payments.

**Users**: Nimiq does not require installation. We design the ecosystem of applications with users in mind so is intuitive, fun and extremely safe at the same time.
<br>
<br>
<br>
### How to start working with Nimiq in an easy way

Download files from this repository and launch `index.html` in your browser. Press F12 to open browser console where you will be able to access Nimiq object and execute different commands.

For a more serious development, please see the official Nimiq core repository.
<br>
<br>
<br>
### Connect to a network

Available networks: main, test, bounty, dev

    Nimiq.GenesisConfig.main(); // mainnet
<br>
<br>
<br>
### How to get private key from 24 recovery words (mnemonic phrase) and vice-versa

In `index.html` console use the following commands:

    // The input HEX string must be 16-32 bytes long.
    var key = 'a18532abfb31ba4e26d64a3ac3430969639aeb5f84b1c4124da0f3e323cdaced';

    var mnemonic = MnemonicPhrase.keyToMnemonic(key);
    // Result: 'pave civil priority wait brick check opera sing depart borrow seat spot defy interest lawn normal series mystery habit treat cram traffic recipe risk'

    var key = MnemonicPhrase.mnemonicToKey(mnemonic);
    // Result: 'a18532abfb31ba4e26d64a3ac3430969639aeb5f84b1c4124da0f3e323cdaced' 

Source: https://github.com/nimiq/mnemonic-phrase
<br>
<br>
<br>
### How to get a seed from a keypair of private and public keys

In `index.html` console use the following command.

    var key = 'a18532abfb31ba4e26d64a3ac3430969639aeb5f84b1c4124da0f3e323cdaced';
    var seed = Nimiq.KeyPair.derive(Nimiq.PrivateKey.unserialize(Nimiq.BufferUtils.fromHex(key))).toHex();
<br>
<br>
<br>
### Nimiq wallets public addresses

The actual address is 36 characters length and has no spaces, like this: `NQ488CKHBA242VR3N249N8MNJ5XX74DB5XJ8`

For better readability, the address can be presented with spaces, like this: `NQ48 8CKH BA24 2VR3 N249 N8MN J5XX 74DB 5XJ8`

Sometimes addresses are presented with "+" or "20%" characters instead of spaces - that's how browsers encode spaces.
This can be observed in URLs, e.g.:
`https://nimiq.mopsus.com/addr/NQ40%20M9RK%20T73M%20CJ68%203LEK%20R319%20KGN1%200FQU%2043L9`
`https://nimiq.watch/#NQ40+M9RK+T73M+CJ68+3LEK+R319+KGN1+0FQU+43L9`

The best practice is to always use the actual address (without spaces) everywhere, but add spaces only on the front-end for user-friendly representation.
<br>
<br>
<br>
### Nimiq useful docs and tutorials

* [Running a Nimiq Node on a Digital Ocean droplet](https://gist.github.com/rlafranchi/6a1772c07c1eccafe2f21f784632504d)
* [How to send NIM with the Node.js API](https://nimiq.community/blog/sending-nim-with-the-api/)
* [JSON RPC API](https://github.com/nimiq-network/core/wiki/JSON-RPC-API)
* [JSON-RPC Client](https://github.com/nimiq-network/core/blob/master/doc/json-rpc-client.md)
<br>
