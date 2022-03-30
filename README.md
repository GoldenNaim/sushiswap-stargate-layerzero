# Summary

This contract allow everyone to swap on **sushiswap** and to send the result to another chain by using **LayerZero** and **Stargate** in one transaction.


This contract has been deployed on multiple network, listed above :
Network  | Address
------------- | -------------
Ethereum  | 0x000000
Polygon | https://polygonscan.com/address/0x143240ea3bFEA4B214a85cF0Cb7f99434ee6bAEd
BSC | https://bscscan.com/address/0xa6Cd8E46eE700D6DfEAe79e44b5a1493736385Fb
Avalanche | https://snowtrace.io/address/0x4aafce8f89ba11fd555a3d2a910bd2fdb2465282
Fantom | https://ftmscan.com/address/0xa6Cd8E46eE700D6DfEAe79e44b5a1493736385Fb

# Functions 

### swapThenSend

This function must be used if you want to swap **an ERC20 token** against USDC, USDT, BUSD ( on BSC ) or STG.
The parameters are listed above : 

Parameters | Value
------------- | -------------
amount *(uint256)* | The quantity that you want to swap
route  *(address[])* | The route used on sushiswap 
minAmount *(uint256)* | The minimum you want to receive
chainID *(uint16)* | The recipient chainID 
srcPoolID *(uint256)* | The pool ID used on the current network
dstPoolID *(uint256)* | The pool ID used on the recipient network
target *(address)* | The recipient address
slippageStargate *(uint256)* | The maximum slippage in percentage 


**chainID, srcPoolID and dstPoolID** can be found here : https://stargateprotocol.gitbook.io/stargate/developers/contract-addresses/mainnet

### swapNativeThenSend

This function must be used if you want to swap **a native token ( Ethereum, Matic..)** against USDC, USDT, BUSD ( on BSC ) or STG.

The parameters are listed above : 

Parameters | Value
------------- | -------------
amount *(uint256)* | The quantity that you want to swap
route  *(address[])* | The route used on sushiswap 
minAmount *(uint256)* | The minimum you want to receive
chainID *(uint16)* | The recipient chainID 
srcPoolID *(uint256)* | The pool ID used on the current network
dstPoolID *(uint256)* | The pool ID used on the recipient network
target *(address)* | The recipient address
slippageStargate *(uint256)* | The maximum slippage in percentage 


**chainID, srcPoolID and dstPoolID** can be found here : https://stargateprotocol.gitbook.io/stargate/developers/contract-addresses/mainnet

### inCaseIf

Because we are never careful enough, if someone send tokens directly to the contract, the owner has the possibility to send them back by using this function.

Parameters | Value
------------- | -------------
mode *(uint256)* | The mode ( 1: ERC20 token - 2: Native token )
token  *(address[])* | The token to send ( put 0x0000000000000000000000000000000000000001 for native token )
amount *(uint256)* | The quantity to send
recipient *(address)* | Recipient address

# Links

sushiswap : https://app.sushi.com/

layerZero : https://layerzero.network/

stargate : https://stargate.finance/

# Author

https://twitter.com/BrutalTrade
