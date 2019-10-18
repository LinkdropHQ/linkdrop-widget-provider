# Linkdrop Widget Provider

## Install
```bash
yarn add ssh://git@github.com:LinkdropHQ/linkdrop-widget-provider.git
```

## Usage
```js
import LinkdropWidget from 'linkdrop-widget-provider'
import Web3 from 'web3' // v1.2.1

// init provider
let widget
const initProvider = async () => { 
  widget = new LinkdropWidget({
   network: 'rinkeby'
  })
  
  // will resolve after user registers or logs in
  await widget.provider.enable()
  
  // use web3
  const web3 = new Web3(widget.provider)
  const accounts = await web3.eth.getAccounts()
  console.log({ accounts })
}

// show widget
widget.showWidget()

// hide widget
widget.hideWidget()
```
