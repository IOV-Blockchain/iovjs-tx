# SYNOPSIS 


This package is based on ethereumjs-tx v1.3.7 with changes to support transaction manipulating in iov blockchain. 

# INSTALL
`npm install https://github.com/IOV-Blockchain/iovjs-tx.git`


npm package.json can use the dependencies by settting as follows:

```
  "dependencies": {
    ...,
    "iovjs-tx": "git+https://github.com/IOV-Blockchain/iovjs-tx.git",
    ...
  }
```

# USAGE

  - example

```javascript
const EthereumTx = require('iovjs-tx')
const privateKey = Buffer.from('e331b6d69882b4cb4ea581d88e0b604039a3de5967688d3dcffdd2270c0fd109', 'hex')

const txParams = {
  nonce: '0x00',
  gasPrice: '0x09184e72a000', 
  gasLimit: '0x2710',
  to: '0x0000000000000000000000000000000000000000', 
  value: '0x00', 
  data: '0x7f7465737432000000000000000000000000000000000000000000000000000000600057',
  // appId: '' for basechain, appId: '3' for sidechain with appId 3. 
  appId: '',
  // iov chainId - mainnet: , testnet: 
  chainId: 3
}

const tx = new EthereumTx(txParams)
tx.sign(privateKey)
const serializedTx = tx.serialize()
```

**Note:** this package expects ECMAScript 6 (ES6) as a minimum environment. From browsers lacking ES6 support, please use a shim (like [es6-shim](https://github.com/paulmillr/es6-shim)) before including any of the builds from this repo.


# BROWSER  
For a browser build please see https://github.com/ethereumjs/browser-builds.

# API
[./docs/](./docs/index.md)

# LICENSE
[MPL-2.0](https://tldrlegal.com/license/mozilla-public-license-2.0-(mpl-2))
